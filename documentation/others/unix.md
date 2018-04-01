---
layout: default
---
# Unix

to check used space
du -sh

to check free space
df -h

to check space of all subdirectories
sudo du -h -d 1 ./jobs/DevOps/jobs/Production_Deploy_pre_deploy_validation

java -XX:+PrintFlagsFinal -version | grep -iE 'HeapSize|PermSize|ThreadStackSize'

export _JAVA_OPTIONS="-Xmx2g"
java -XX:+PrintFlagsFinal -version | grep -iE 'HeapSize|PermSize|ThreadStackSize'

//Check memory available in linux
cat /proc/meminfo

-------------
Set timezone

# date
Mon Sep 17 22:59:24 UTC 2010

# cd /etc
# rm localtime

# ls /usr/share/zoneinfo/US/
Alaska          Arizona         Eastern         Hawaii          Michigan        Pacific
Aleutian        Central         East-Indiana    Indiana-Starke  Mountain    

# cd /etc
# ln -s /usr/share/zoneinfo/US/Pacific localtime

# date
Mon Sep 17 23:10:14 PDT 2010

-------------------
set time
date +%T -s "11:14:00"

set date
date +%Y%m%d -s "20120418"
------------------

for i in ; do echo "Final Line: " $i "================================================"; grep $i -ir . ; done > ../Referral.txt 
------------------

===========================================
Enable unidentified apps to run. Enable Anywhere option:

sudo spctl --master-disable
sudo spctl --master-enable
===========================================

Run JD

java --add-opens java.base/jdk.internal.loader=ALL-UNNAMED --add-opens jdk.zipfs/jdk.nio.zipfs=ALL-UNNAMED -jar jd-gui-1.4.0.jar 
============================================

# RegEx

How to remove single line comment from class content: 
    commentedCode = commentedCode.replaceAll('//.*', '');

How to remove multi line comment from class content:
    commentedCode = commentedCode.replaceAll('(?s)/\\*.*\\*/', '');

. = Any character - single 
.* = Any character - Any number of times - Greedy matching - Will get the longest such string
*? = Any character - Any number of times - Non-Greedy matching - Will match the shortest possible length
(?s) = Should consider multi lines. Normally it will search for regex within same line considering that the it will start and end in the same line. To do this in multi line, use this.
\ = To escape any character

Finally to get rid of all single and multi line comments use this:
Greedy:
    (/\*([^*]|[\r\n]|(\*+([^*/]|[\r\n])))*\*+/)|(//.*)
Non-Greedy:
    (/\*(.|[\r\n])*?\*/)|(//.*)

The above still does not consider the comments inside the quotes e.g. the below will cause issue because there is a // inside the quotes.
            String url = 'https://chart.googleapis.com/chart?chs=300x120&cht=lxy:nda&chd=t:';

[dasdasdasdsa] - only one character
(dasdsad) - sub regex
? - one or none of preceding char
* - one or more
. - one

"SOMETHING" = everything except "something"

