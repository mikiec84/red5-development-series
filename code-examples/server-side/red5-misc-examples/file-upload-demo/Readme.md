# File Upload Example
---




## About
---



This example demonstrates how to upload a file into Red5 Pro using a file upload servlet. You can upload any kind of file to a location on the Red5 Pro instance.
The servlet logic should take care of providing security and validation of the file upload. The example is intended for uploading flv and mp4 files into the streams directory for later playback.


### Configuration properties

Web application's configurable properties can be found in red5-web.properties file located at `{RED5_HOME}/webapps/file-upload-demo/WEB-INF/red5-web.properties` .


* `webapp.uploadDir` : Path to upload directory. This is relative to the webapp's WEB-INF directory.


## Build & Deploy
---


### Build
---

To build this application : open a shell prompt in the application's project directory (where the pom.xml file resides). run the following maven command in your shell -> 

``` 
mvn clean package 

```

The above command will generate a `war` file in the `target` directory inside the project directory. 


### Deploy
---

To deploy the war to red5 / red5 pro server :

1. Stop server if it is running.

2. Extract the content of the `war file` to directory by war name. 

> The java war file is simply a `archive file` similar to `zip` format. you can extract it using a archive tool such as [7zip](#http://www.7-zip.org/), [Winrar trial](#http://www.rarlab.com/download.htm) etc

3. Copy the folder into `RED5_HOME/webapps/` directory.

4. Start server.


## How To Use Example
---


* Once you have the server application running, access the index page on server from your browser as:

``` 
http://{host}:5080/file-upload-demo/
```

> Where ` {host}`  is where you are running the server. Ex: for local testing it will be `localhost`.


* In the html form rendered on the index page, click on `Choose File` to browse and select a `flv/mp4` for upload.

* Once a file has been selected, click `Upload`.

* After the file is uploaded, it can be seen in the `{webapps}/file-upload-demo/streams directory`.



## Eclipse
---

You can edit the server side code in your eclipse JEE IDE such as Luna, Mars, Neon etc. To import the code into your IDE:

1. Navigate to the repository folder
2. Execute maven command `mvn eclipse:eclipse`. This will generate files necessary for eclipse to read the maven project properly.
3. In eclipse go to `File -> Import -> Existing Maven Projects` and click `Next`.
4. Browse and select `the project root` and Click `Finish` to import the project.



## Additional Notes
---

This simple upload application does not implement security, validation etc for uploads. It is the responsibility of the developer to implement the same in the servlet to prevent the server from misuse.




