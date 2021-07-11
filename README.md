# NiFi
Apache NiFi Repo for my ELT jobs

## Installing NiFi on CentOS8

Open the terminal and switch the root user:

```su root ```

The first prerequisity is the Java. To install java keep the following steps:

---------------------------------------------------------------
### STEP 1: 
Go to the wrb site https://www.oracle.com/tr/java/technologies/javase-jdk11-downloads.html
------
### STEP 2: 
Then select **Linux x64 Compressed Archive** ***jdk-11.0.11_linux-x64_bin.tar.gz*** then the download process will be started.

![image](https://user-images.githubusercontent.com/28653377/125196129-4a3aba80-e261-11eb-96af-b3564bfec05a.png)
------
### STEP 3: 
A message box will be appeared, click te check box then press ***Download jdk-11.0.11_linux-x64_bin.tar.gz***

![image](https://user-images.githubusercontent.com/28653377/125196182-85d58480-e261-11eb-9b7e-2052a7f9a4ff.png)
------
### STEP 4: 
After signing in Oracle the file will be started to dowload. Then go to Downloads and copy the download link

https://download.oracle.com/otn/java/jdk/11.0.11+9/ab2da78f32ed489abb3ff52fd0a02b1c/jdk-11.0.11_linux-x64_bin.tar.gz?AuthParam=1626008797_7e1284827d6b6089c21edba29c923c6a
------
### STEP 5: 
Turn back to the terminal and paste the link after typing **wget -O** <br/>
```wget -O jdk-11.0.11_linux-x64_bin.tar.gz https://download.oracle.com/otn/java/jdk/11.0.11+9/ab2da78f32ed489abb3ff52fd0a02b1c/jdk-11.0.11_linux-x64_bin.tar.gz?AuthParam=1626008797_7e1284827d6b6089c21edba29c923c6a```

It stats to download the zip file. 
------
### STEP 6: 
Then it is time to download NiFi same as Java. Go to https://nifi.apache.org/download.html and under the Binaries select the latest version, **nifi-1.13.2-bin.tar.gz ( asc, sha256, sha512 )** is the latest the time this readme is written. 
------
### STEP 7: 
Copy the link of the mirror under this statement "We suggest the following mirror site for your download:" 
https://ftp.itu.edu.tr/Mirror/Apache/nifi/1.13.2/nifi-1.13.2-bin.tar.gz

![image](https://user-images.githubusercontent.com/28653377/125196527-fe891080-e262-11eb-9124-d7842bcd03b7.png)

------
### STEP 8: 
Turn back to the terminal and once again do the same thing like in Java install. 
```wget -O nifi-1.13.2-bin.tar.gz https://ftp.itu.edu.tr/Mirror/Apache/nifi/1.13.2/nifi-1.13.2-bin.tar.gz```
------
### STEP 9: 
After downloading we need to exract these tar.gz files. First check whether downloaded zip files in /home directory
type ```ls -lt```
Then you will see these two zip file is appeared. Then start to extract them. 

#### First the Java extraction will be like that:
type ```tar -xvf jdk-11.0.11_linux-x64_bin.tar.gz``` <br/>
It will automatically unzip java file. <br/>

After the java unzip file is finished again type ```ls -lt``` then the new unzipped java file **jdk-11.0.11** will be appeared with the same name.<br/> 

#### Second the NiFi extraction will be like that:
type ```tar -xvf nifi-1.13.2-bin.tar.gz``` <br/>
After the NiFi unzip file is finished again type ```ls -lt``` then the new unzipped NiFi file **nifi-1.13.2** will be appeared with the same name. <br/>

------
### STEP 10: 
After that we will have something to do in java file. Type ```cd jdk-11.0.11``` then go to the file. <br/>

------
Type ```pwd``` and copy the path, we will use it to set JAVA_HOME.<br/>
Type ```export JAVA_HOME=/home/user/jdk-11.0.11``` click enter and <br/>
Type ```export PATH=$PATH:$JAVA_HOME/bin``` click enter<br/>
So Java is set.<br/>

------
### STEP 11: 
Type ```java``` the let's get started.<br/>

------

### STEP 12: 
Let's discover NiFi file. <br/>

------

Type ```cd ~``` you are on /home directory now.<br/>
Type ```cd nifi-1.13.2```<br/>
Type ```ls -lrt```<br/>
Type ```cd bin```<br/>
Type ```ls -lrt```<br/>
Type ```./nifi.sh start``` it will start the NiFi.<br/>

------

To see whether the NiFi get started let's look at the logs.<br/>
Type ```cd ../logs``` it will bring you the NiFi logs file.<br/>

-------

Type ```pwd``` to see where you are <br/>
The output will be like that **/home/user/nifi-1.13.2/logs**<br/>
Type ```ls -lrt```

------

Then you will see three different NiFi log files <br/>
nifi-user.log <br/>
nifi-bootstrap.log <br/>
nifi-app.log <br/>

------

Let's monitor the app logs:
Type ```tail -f nifi-app.log```
This will continuing list of operations that are automatically started with the Nifi service. <br/>
If you wnt to exit this monitoring press ```Ctrl+C``` to stop something streaming in your terminal.<br/>
For checking the server start health some repo files must be created by NiFi.<br/>

------

Type ```cd ..```
Type ```ls -lrt```
You will see that four default repository have been created.
 - database_repository
 - provenance_repository
 - content_repository
 - flowfile_repository

------

### STEP 13: 
Check how the NiFi works!
Go to your browser and <br/> 
Type "localhost:8080" if you encountered a message lik "this site can't be reached" that means that your NiFi server is still trying to wake up. Within a few minutes the process will has been finished.

------ 

After typing "localhost:8080" a web browser will direct you to the NiFi UI. 














