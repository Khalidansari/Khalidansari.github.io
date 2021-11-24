
## Excerpts from the amazing book
# The Art of Readable Code
# by Dustin Boswell and Trevor Foucher

## tips on writing good code:

1. left side should be variable and right side should be more constant
e.g.
while (bytes_received < bytes_expected)
while (bytes_received < 10)

2. https://mcusoft.files.wordpress.com/2015/04/the-art-of-readable-code.pdf
line 79

3. Add “explaining variable”

4. Summary variable

final boolean user_owns_document = (request.user.id == document.owner_id);
if (user_owns_document) {
 // user can edit this document...
}

5. Each boolean if else has two ways to be written in. Use De Morgan’s Laws and judge which one is easier.

6. Use guard code (return / throw early) to avoid nested if else. Removing Nesting by Returning Early. Inside a loop, the analogous technique to returning early is to continue.

7. Comment the why and code the what

8. Example

Not readable - trying to find overlap

return (begin >= other.begin && begin < other.end) ||
 (end > other.begin && end <= other.end) ||
 (begin <= other.begin && end >= other.end);


Readable - trying to find if they don't overlap first.

bool Range::OverlapsWith(Range other) {
 if (other.end <= begin) return false; // They end before we begin
 if (other.begin >= end) return false; // They begin after we end
 return true; // Only possibility left: they overlap
}

9. Making names shorter or capturing a long expression in a single variable makes sense. The main code should look readable.

10. Issues with lines which are very similar but with small changes. Might not be easy to make out just by glancing at it. May be create a method to capture similar changes.

11. Is now a variable worth keeping? No, and here are the reasons:

now = datetime.datetime.now()
root_message.last_view_time = now

• It isn’t breaking down a complex expression.
• It doesn’t add clarification—the expression datetime.datetime.now() is clear enough.
• It’s used only once, so it doesn’t compress any redundant code.

12. No issue with breaking early. This will sometimes help avoid intermediate variables which do not help improve readability.

13. For loops in a loop, rather than breaking twice, push both loops in a separate funciton and return from there.

14. Shrink the scope of variables as much as possible

15. Breaking function / class into smaller also helps in creating variables with lesser scope.

16. try to decrease the number of changes to a variable. Best is immutable / constant and then next best is write once vars.

17. Shorter Names Are Okay for Shorter Scope. Longer name for bigger scope.

18. Remove extra words

e.g.  ConvertToString() > ToString()

19. To remove arrow code (nested if else, for, while, etc) use break, continue, return.

## Sorting

1. Merge sort - O(nlogn) / /stable
2. Quick sort - O(nlogn) for best case (pivot is median). Worst case O(n*n) for list already sorted. Best strategy is to chose pivot randomly. Choosing middle element also works most of the time. Algorithm uses partitioning based on pivot.
3. Insertion sort - O(n*n)/inplace/stable
4. Heap sort - O(nlogn) /
5. Bucket sort -
6. Selection sort - In this list the only online Algorithm
7. Bubble sort
8. Radix sort


Pending Topics
--------------
Used for range queries - Segment Tree and Binary Indexed Tree (Fenwick Tree)

Java methods
------------
1. Hashmap's getordefault method. Example below.

HashMap<Integer, Integer> m = new HashMap<>();
for (int n : nums1) {
    m.put(n, m.getOrDefault(n, 0) + 1);
}

2. Sort array

Arrays.sort(nums1);

3. Get sub array

Arrays.copyOfRange(result, start, end);

4. How to reverse list in java? Following does not return but reverses the original list.   
Collections.reverse(list);

5. Java LinkedList

addFirst()
addLast()
removeFirst()
removeLast()
getFirst()
getLast()


Linux Commands
-------------

1. /bin - all Commands
2. /sbin - like super bin - commands for sys admin
3. /usr - there are also bin and sbin there. /bin is symlink to /usr/symlink and same for sbin. They are there for historical reasons. Initially they were kept on fast and slow disc but now it is not needed. But still linux distros keep these two because of other softwares which might expect it at those places.
4. /boot - files needed to boot the system.
5. /log - log files
6. /tmp - files which are temporary and goes away after system reboot
7. /dev - devicess
8. /etc - (pronounced etsy) - network configuration files lives
9. /media - mounted drive e.g. usb
10. /mnt - drives you mount manually
11. $ is for user and # is for root on terminal
12. man uname - gives manual for uname
13. uname --help - gives how to use it and looks more direct than man.
14. apropos sometext - searches for all commands with sometext in them.
15. /etc/passwd - where users are stored. X there means the passwords are saved in a different place called Shadow
16. /etc/shadow - hashed passwords stored here.
17. Add user - sudo adduser kansari
18. passwd - to change the password
19. su - kansari > this will switch user to kansari
20. exit or logout to logout of shell. May be from root back to your user.
21. sudo visudo - to edit the sudoers list
22. userdel - delete users
23. usermod - modify exisitng user.
24.


Bash
----
e.g.

echo "Enter your name: \c"
read name
echo "Hello, $name"

echo "hello" - will print hello and add a new line. If you don't want a new line then add a -c switch as below
echo -n "hello"
