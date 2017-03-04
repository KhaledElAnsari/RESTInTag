# RESTInTag
An upcoming plugin to ease the REST requests by making them work directly from the HTML tags
it was inspired by [RestfulizerJs by Ifnot](https://github.com/Ifnot/RestfulizerJs) but with a different implementation

# Install

## Simple Download

 - [jQuery version](https://raw.githubusercontent.com/KhaledElAnsari/RESTInTag/master/src/restintag.jquery.js)
 - [Vanilla Javascript](https://raw.githubusercontent.com/KhaledElAnsari/RESTInTag/master/src/restintag.vanilla.js)

 after downloading include them in your html file like this

 ```html
<script src="path/to/js/restintag.vanilla.js"></script>
 ```

## NPM
Install via this command
```
npm install --save restintag
```

# Usage
easy! just add the following attributes to your HTML tag:

1. `data-method`: the request type, GET, POST, PUT, etc.
2. `data-target`: the url to send/get the data
3. `data-disabled`: `true` to disable the tag until the request is done else just put `false`

example:

```html
<button data-target="http://example.com/post/post-id/" data-method="DELETE" data-disabled="true">Delete Article</button>
```

or you can use the javascript apis, note the data attributes have the priority.

# API

## Vanilla
The zero dependency version, just add it to any project you have and it will work

```javascript
restintag(selector: String, options: Object, successCallback: Function, errorCallback: Function): void
```

options are the following (the seen values are the default):
```javascript
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

## jQuery
after adding jQuery use the `restintag()` function to do the magic

```javascript
$(".selector").restintag(options: Object, successCallback: Function, errorCallback: Function): jQuery
```
options are the following (the seen values are the default):
```javascript
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

# Browser Support

Both jQuery version and Vanilla version support the following browsers:

- Chrome (Latest)
- FireFox (Latest)
- Edge (Latest)
- IE (9+)
- Opera (Latest)
- Safari (Latest)
- Vivaldi (Latest)
- Epiphany (Latest)

# License

This project is under the MIT license.