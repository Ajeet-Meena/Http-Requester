# Http-Requester
Easy to use Http Requester | Based on HttpUrlConnection for Android | Instead of writing 100 line of code use HttpRequester.

# Instruction


1. Create HashMap of key and value pair of request parameter:  
  ```java
  HashMap<String, String> hashMap = new HashMap<>();
  hashMap.put("key1", "param1");
  hashMap.put("key2", "param2");
  ```
  
2. Initialize HttpRequester with context, Requesting URL, Request Code, i.e POST_REQUEST, GET_REQUEST, Hash Map of key value pair, If progress Dialog then true :
    ``` java
    ApiURLConnection.HttpRequester httpRequester = new ApiURLConnection.HttpRequester(context, requestCode, URL, hashMap,        hasProgressDialog);
    ```
    
    
3. Register on request complete callback which calls when http request is completed.
   ``` java
     ApiURLConnection.HttpRequester httpRequester = new ApiURLConnection.HttpRequester(context,                                   ApiURLConnection.POST_REQUEST, "http://54.65.180.229/sync-notifications-initial/", hashMap, false);
        httpRequester.registerOnRequestCompleteListener(new ApiURLConnection.OnRequestCompleteListener() {
            @Override
            public void onComplete(Boolean success, int requestCode, String URL, String result) {
                if( success ) {
                        // Handle response in result
                    } 
                }
        });
   ```
   
4. Finally, execute httpRequester as required.

  ``` java
  httpRequester.execute();
  ```


  
