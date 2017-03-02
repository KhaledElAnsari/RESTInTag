# RESTInTag
An upcoming plugin to ease the REST requests by making them work directly from the HTML tags
it was inspired by [RestfulizerJs by Ifnot](https://github.com/Ifnot/RestfulizerJs) but with a different implementation

# Usage
easy! just add the following attributes to your HTML tag:
1. `data-method`: the request type, GET, POST, PUT, etc.
2. `data-target`: the url to send/get the data
3. `data-disabled`: `true` to disable the tag until the request is done else just put `false`

# API
## jQuery
after adding jQuery use the `restintag()` function to do the magic
```
restintag(options: Object, successCallback: Function, errorCallback: Function)
```
options are the following (the seen values are the default):
```
{
    parse: false, // if you have query string, it will add them to the request body
    target: null, // the url
    method: "GET", // the request method
    headers: {}, // the HTTP headers
    timeout: 0, // milliseconds to wait before cancelling the request, 0 means no timeout 
    data: {}, // request body specially for POST and PUT requests
    disable: true // to disable the clicking event until the request is finished
}
```