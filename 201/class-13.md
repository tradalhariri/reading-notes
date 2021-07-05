# The Past ,Present and Future Of Local Storage For Web Applications.

* DIVING IN : native applications has an advantage over web applications according to the persistant local storage . in the native application you can save the preferences for example and don't care about the available storage. the cookies appeared  early in the history of the web as a solution for local storage but it has three disadvantages
  
------
  
  1. cookiew are sent with every http request which make your website slow.
  2. maximum size of cookies is up to 4kB which in not enough to be useful .
  3. sending uncrypted cookies with every http request which makes your web application unsecure unless you use ssl.

------

* INTRODUCING HTML5 STORAGE : HTML5 storage is a way for storing named key/value pair in the web page. if you close the browser or navigate to another page or if you shuttdown your device the data will remain stored. 
  
* USING HTML5 STORAGE : html5 storage is key/value data the key is a string and the value is any data type javascript supports.but the value is stored as string so when you retrieve it you should use a proper way to convert the string to the desired type.
  

* TRACKING CHANGES TO THE HTML5 STORAGE AREA : we can track any changes in the local storage using addEventListener and the event in this case is storage and if we setItem() or clear() the event will triggered. if for example we called clear() method and there are nothing to clear in the local storage the event will not triggered.
  
  ```js

    if (window.addEventListener) {
    window.addEventListener("storage", handle_storage, false);
    } else {
    window.attachEvent("onstorage", handle_storage);
    };


    function handle_storage(e) {
    if (!e) { e = window.event; }
            }
    ``` 

    [References](http://diveinto.html5doctor.com/storage.html)





 