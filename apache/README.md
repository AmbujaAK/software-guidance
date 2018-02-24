# Apache-tomcat
> **Requirements before installing Apache tomcat**
- If you have not installed jdk on your syatem then download it from [here](http://www.oracle.com/technetwork/java/javase/downloads/jdk9-downloads-3848520.html)
- set the **JAVA_HOME** *path* in *Environment Variable*
- Follow the steps below for Environment Variable..
	1. Go to *Control Panel*
	2. Then *System and Security*
	3. Then *System*
	4. Then *Advance System Settings*
	5. Then a pop-up window will appear named *System Properties*
	6. In this window , you will see **Environment Variables**
	7. In *System variables* , make a new path with Variable name as **JAVA_HOME** and variable value as **C:\Program Files\Java\jdk1.8.0_131** *(location of jdk)* 
> **How to Install Apache tomcat on Windows**
- Download Apache *.zip* file from [here](https://tomcat.apache.org/download-90.cgi)
- Extract it where you want (*say* **Desktop**)
> **How to start/stop the server**
- Go to **bin** folder  say (*F:\apache\bin*)
- Click on **startup** to start the server and **shutdown** to stop the server.
> How to check if it's working or not
- Type **localhost:8080** in your browser.
- If you see *Congratulations* page , then it's done.
- If you see any error , google it with respective error.
> How to Change Port number
- Go to **conf** folder  say (*F:\apache\conf*)
- You will see a XML file named *server.xml*
- you have to edit default port no (*8080*) in this file and save it.
```xml
<Connector port="8080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
  ```
  - Restart the server for applying the change .