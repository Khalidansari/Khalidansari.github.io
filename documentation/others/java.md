---
layout: default
---
# Java

Is a class based - meaning it enables inheritence through classes instead of objects alone

Java is compiled from source > bytecode and then the bytecode is interpreted (though some portions are native compiled by JIT)

Compiler already does most of the work so JVM has to do the least. Byte code is mostly like machine code except that there are some mapping from bytecode opcode to machine opcode based on which platform it is on. So JVM is in the layer just to provide cross compatibility.

## Pass by Value/Reference

Java passes everything by value - including references. What this means is that if you pass an object, you can modify properties of that object, and they will persist after you return, but you can't replace the object in its entirety with a completely new object, because you can't actually modify the reference - only what the reference points to. This is different in C/C++



If you want to run eclipse using different java version:
------------------------------------------------------------------
Add below line to eclipse.ini

-vm
C:\Program Files (x86)\Java\jre6\bin\javaw.exe

Eclipse does not use JAVA_HOME. Without the above line it uses the JRE which appears when you execute java in cmd.
--------------------------------------------------------------------
Upgrading eclipse from Java developer to Jave EE developer - Go to install new software and click on galelio/europa/Helios and select the last on - Java EE Developer - and click install.

JVM Space Management:
1. Stack - Methods and local variables
2. Heap - All others. But it is divided in to generations - young gen (keeps things which stays shorter) and old gen (stays longer). besides this there is Permanent Gen ( Class definitions are kept here) which is used to keep things which are residing permanently in JVM. PermGen is seperate from heap. To set its space we can use the below line:
    -XX:MaxPermSize=256m

Inner class - non static
Nested class - static
Note: Inner classes can not have static members or blocks

Anonymous classes which are created are named as - MainClass$NumberStartingFromOne.class

Final variables are thread safe because they can't be changed once initialized.
Static blocks are executed using a single thread.

Nimbus is a cross platform look and feel in java which uses Java 2D to draw elements instead of bitmap.

While creating jar: The manifest file must have a single blank line at the end or under some circumstances it will not be correctly processed


Create jar: Structure - com/ui/
                                    Manifest/Manifest.mf - com.ui.MainScreen.

 jar cfe tcpmon.jar com.codegoogle.tcpmon.MainWindow com/codegoogle/tcpmon/*.class

For the full hierarchy - use *
------------------------------------
jar -cvfm AwtExample.jar MANIFEST.MF *

----------------------------------------------------------------
Java Stack / Frame - Keeps seperate memory for each thread. Each thread will have its own stack and a PC (Program Counter)

Memory generation - Used by JVM's garbage collector called generational garbage collector

    a) Young generation -
            1) Eden space - First time the objects go to this.
            2) Survivor space - When GC runs, all the above objects if still alive then they are moved to Survivor space.

SwingWorker: new SwingWorker(T,V) { doInBackground() done()} - doInBackground() is run on a background thread while done() is called on EDT.
Event Dispatching thread: Takes care of Swing UI, example - repainting. If it is stuck then the UI will freeze.
Background threads are worker threads.

Java IO

Connection Stream: Connect to either source or target
Chain Streams: Connect to other streams

FileReader(path) > BufferedReader > readLine()
FileWriter(path) > BufferedWriter > write()
FileWriter(path, true) > BufferedWriter > write()

FileInputStream(File).read() - returns integer. It can be converted to char using (char).
FileOutputStream(path).write()    
FileReader(path).read()
FileWriter(path).write()

Internally FileReader uses FileInputStream

File - Takes path in string format and returns a file
Create file - FIle.createNewFile()

delete file - file.delete()

File permissions
--------------------
file.canExecute() & setExecutable
file.canWrite()     & setReadable
file.canRead()     & setWritable

Run cmd command from Java
-------------------------------------
Runtime.getRuntime().exec("chmod 777 file");

Above will run only when the supplied word is a separate part and not a part of windows. Else it will throw file not found exception because it won't be able to find chmod.exe. To resolve this use the below:

String[] cmd = new String[3];
cmd[0] = "cmd.exe" ;
cmd[1] = "/C" ;
cmd[2] = "dir *.java";

Runtime.getRuntime().exec(cmd);

How to get the operating system name
------------------------------------------------
String osName = System.getProperty("os.name" );


How to play with XML
--------------------------
Document doc = DocumentBuilderFactory.newInstance().newDocumentBuilder().parse(inputStream);
Element element = doc.getDocumentElement();
NodeList nodeList = element.getElementsByTagName("POPULARITY");
Element elementAttribute = (Element) nodeList.item(0);
String attribute = elementAttribute.getAttribute("TEXT");

How to get URL page content
-------------------------------------
URLConnection conn = new URL("www.juby.com").openConnection();
InputStream is = conn.getInputStream();


Types of streams
----------------------
Byte Stream - subclasses of InputStream/OutputStream - 8bit at a time (1byte = 8 bits)
Char Stream - subclasses of Reader/Writer - 16 bit at a time (Unicode character takes 2 bytes each)
Object Stream - subclasses of ObjectInputStream/ObjectOutputStream

In using above classes there is a overhead because we are reading one char at a time. To make it more efficient we use buffered classes to get lines instead of chars.

Convert to buffered by pass the stream to buffered constructor.

BufferedInputStream/BufferedOutputStream - byte stream
BufferedReader/BufferedWriter - Char stream (readLine method)

PrintWriter
-------------
Char stream - and is helpful in formatting the output.

RandomAccessFile
------------------------
Use the seek() method in this class to randomly find any data in the file. Its efficient in such cases.
