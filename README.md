# Exploring Bookmarklets
Exploration with a variety of bookmarklets that can be used to manipulate web pages.

## Make API Call and Display Results as Alert
I wanted a simple way to call an API URL to retrieve some JSON data and display via URL - [Drag and Drop This](javascript%3A%21function%28%29%7Bvar%20e%3Dnew%20XMLHttpRequest%3Be.onreadystatechange%3Dfunction%28%29%7B4%3D%3De.readyState%26%26200%3D%3De.status%26%26alert%28JSON.parse%28e.responseText%29%29%7D%2Ce.open%28%22GET%22%2C%22https%3A%2F%2Fraw.githubusercontent.com%2Fkinlane%2Fbookmarklets%2Fmain%2Fhello.json%22%2C%210%29%2Ce.send%28%29%7D%28%29%3B)
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

