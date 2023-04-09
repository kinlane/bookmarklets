# Exploring Bookmarklets
Exploration with a variety of bookmarklets that can be used to manipulate web pages.

## Make API Call and Display Results as Alert
I wanted a simple way to call an API URL to retrieve some JSON data and display via URL.
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

## Make API Call and Pass in URL Then Display Results as Alert
I wanted a simple way to call an API URL, pass in the URL of the page I am on, and then retrieve some JSON data and display via URL.
```
javascript: (function() {

    var url = "https://raw.githubusercontent.com/kinlane/bookmarklets/main/hello.json?url=" + encodeURIComponent(location.href);

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
