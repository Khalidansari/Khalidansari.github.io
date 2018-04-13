---
layout: default
---
# Basic Unix Commands

No matter which OS you are on, these commands will come handy to you if you are interested in quick scanning of code/docs. For those are on Windows system can install cygwin to get a command prompt where they can execute the following commands.

<br/>

## grep

> search for a text in file/directory

```sh
grep 'TEXT_TO_BE_SEARCHED' -OPTIONS DIRECTORY_TO_BE_SEARCHED_IN
```

<br/>
    
## du/df

> to check total used space

```sh
du -sh
```

> to check total free space

```sh
df -h
```

> to check space usage of all subdirectories within current directory. If you want to see the space usage of subdirectories within subdirectories then change "-d 1" to "-d 2" (-d stands for depth)

```sh
sudo du -h -d 1 .
```
<br/>

## Java variables

> check value of variables related to java heapsize, permsize & thread stack size

```sh
java -XX:+PrintFlagsFinal -version | grep -iE 'HeapSize|PermSize|ThreadStackSize'
```

> change java variables

```sh
export _JAVA_OPTIONS="-Xmx2g"
java -XX:+PrintFlagsFinal -version | grep -iE 'HeapSize|PermSize|ThreadStackSize'
```

<br/>

## ram size

> check total size of ram

```sh
cat /proc/meminfo
```

<br/>

## timezone

> see date time with timezone

```sh
date
```

> remove localtime

```sh
rm /etc/localtime
```

> check available timezones

```sh
ls /usr/share/zoneinfo/US/
Alaska          Arizona         Eastern         Hawaii          Michigan        Pacific
Aleutian        Central         East-Indiana    Indiana-Starke  Mountain    
```

> change local timezone to another timezone. Here we have set the local timezone as US Pacific

```sh
ln -s /usr/share/zoneinfo/US/Pacific localtime
```

> set/change time

```sh
set time
date +%T -s "11:14:00"
```
> set/change date

```sh
set date
date +%Y%m%d -s "20120418"
```

<br/>

## loop

> you can either loop in through a result set of another command e.g. $ls or through a fixed set of numbers e.g. `seq 1 10`. 

```sh
for i in $(ls); do 
    echo "Final Line: " $i "================================================"; 
    grep $i -ir . ; 
done
```

<br/>

## RegEx

Explained through an excercise of removing comments from java code using regex.

> Basic options

```
. = Any character. One instance.
.* = Any character. Any number of times. Greedy matching (will get the longest such string)
*? = Any character. Any number of times. Non-Greedy matching (will match the shortest possible length)
(?s) = Should consider multi lines. Normally it will search for regex within same line considering that
       it will start and end in the same line. To do this in multi line, use this.
\ = To escape any character
```


> remove single line comment from class content

```sh
commentedCode = commentedCode.replaceAll('//.*', '');
```

> remove multi line comment from class content

```sh
commentedCode = commentedCode.replaceAll('(?s)/\\*.*\\*/', '');
```


> final solution to get rid of all single and multi line comments

```sh
Greedy: (/\*([^*]|[\r\n]|(\*+([^*/]|[\r\n])))*\*+/)|(//.*)
Non-Greedy: (/\*(.|[\r\n])*?\*/)|(//.*)
```

The above still does not consider the comments inside the quotes e.g. the below will cause issue because there is a // inside the quotes.
            String url = 'https://chart.googleapis.com/chart?chs=300x120&cht=lxy:nda&chd=t:';

[dasdasdasdsa] - only one character
(dasdsad) - sub regex
? - one or none of preceding char
* - one or more
. - one

"SOMETHING" = everything except "something"