# Exploring Bookmarklets
Exploration with a variety of bookmarklets that can be used to manipulate web pages.

## Make API Call and Display Results as Alert
I wanted a simple way to call an API URL to retrieve some JSON data and display via URL - <a href="javascript:!function(){var e=new XMLHttpRequest;e.onreadystatechange=function(){4==e.readyState&&200==e.status&&alert(JSON.parse(e.responseText))},e.open(%22GET%22,%22https://raw.githubusercontent.com/kinlane/bookmarklets/main/hello.json%22,!0),e.send()}();">Drag</a>
```
javascript: (function() {

    var url = "https://raw.githubusercontent.com/kinlane/bookmarklets/main/hello.json";

    var xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
        if (xhttp.readyState == 4 && xhttp.status == 200) {
            var response = JSON.parse(xhttp.responseText);
            alert(response);
        }
    };
    xhttp.open("GET", url, true);
    xhttp.send();

})()
```

