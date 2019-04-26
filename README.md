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
If you have the response string, use it in http://www.jsonschema2pojo.org/ to convert to POJO and either
- download the zip and paste it in the project's model package(create model package to place these POJO classes)
- copy and paste the generated POJO class code to the respective class in Android Studio.

Define end point in an interface
------------------------------
Create an ApiInterface file containing the end point.
```java
    @GET("users")
    Call<List<User>> getUsers();
```

If you want to get the response in an Activity, then define a method getUsers() and call it.
```java
private void getUsers() {
        Retrofit retrofit = new Retrofit.Builder()
                .baseUrl("https://jsonplaceholder.typicode.com/")
                .addConverterFactory(GsonConverterFactory.create())
                .build();

        ApiInterface service = retrofit.create(ApiInterface.class);

        Call<List<User>> repos = service.getUsers();
        repos.enqueue(new Callback<List<User>>() {
            @Override
            public void onResponse(Call<List<User>> call, Response<List<User>> response) {
                Toast.makeText(MainActivity.this, "here", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onFailure(Call<List<User>> call, Throwable t) {

            }
        });
    }
```

Place a breakpoint in the line containing the Toast, and view the response variable.
