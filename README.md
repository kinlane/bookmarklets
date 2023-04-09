# Exploring Bookmarklets
Exploration with a variety of bookmarklets that can be used to manipulate web pages.

## Make API Call and Display Results as Alert
I wanted a simple way to call an API URL to retrieve some JSON data and display via URL - [Drag and Drop This](javascript:!function%28%29{var e=new XMLHttpRequest;e.onreadystatechange=function%28%29{4==e.readyState&&200==e.status&&alert%28JSON.parse%28e.responseText%29%29},e.open%28'GET','https://raw.githubusercontent.com/kinlane/bookmarklets/main/hello.json',!0%29,e.send%28%29}%28%29;)
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

