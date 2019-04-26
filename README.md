Retrofit
========

Type-safe HTTP client for Android and Java by Square, Inc.

Download
--------

Add the following line to app level build.gradle file:
```groovy
    implementation 'com.squareup.retrofit2:retrofit:2.5.0'
```
Retrofit requires at minimum Java 7 or Android 2.3.

Among many converters provided, we can use gson converter. 

Add the following line to app level build.gradle file:
```groovy
    implementation 'com.squareup.retrofit2:converter-gson:2.5.0'
```

Permission
----------
Add the following line to AndroidManifest.xml outside the application tag:
```xml
    <uses-permission android:name="android.permission.INTERNET"/>
```

API
------------------------------
If you have an API already, use it. Else you can create a placeholder api from https://jsonplaceholder.typicode.com/
For this example, use /users endpoint.


Convert JSON Response to Java 
------------------------------
If you have the response string, use it in http://www.jsonschema2pojo.org/ to convert to POJO.



 [1]: https://square.github.io/retrofit/
 [2]: https://search.maven.org/remote_content?g=com.squareup.retrofit2&a=retrofit&v=LATEST
 [snap]: https://oss.sonatype.org/content/repositories/snapshots/
