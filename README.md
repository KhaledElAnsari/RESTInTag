# RESTInTag
A JavaScript plugin to ease the HTTP requests by making them work directly from the HTML tags.
it was inspired by [RestfulizerJs by Ifnot](https://github.com/Ifnot/RestfulizerJs) but with a different implementation.

# Install

### Simple Download

 - [jQuery version](https://github.com/KhaledElAnsari/RESTInTag/tree/master/src/jquery)
 - [Vanilla Javascript](https://github.com/KhaledElAnsari/RESTInTag/tree/master/src/vanilla)

 after downloading include them in your html file like this

 ```html
<script src="path/to/js/restintag.vanilla.js"></script>
 ```

### NPM
Install via this command
```
npm install --save restintag
```

then in your main javascript file do the following

```javascript
// For vanilla version
var restintag = require("restintag").vanilla;
restintag(".test", {}, function(data) {
    console.log(data);
});

// For jQuery version
var jquery = require("jquery");
window.$ = window.jQuery = jquery;
var restintag = require("restintag").jquery;
jquery.fn.restintag = restintag;

$(".test").restintag({}, function(data) {
    console.log(data);
});
```

# Usage
easy! just add the following attributes to your HTML tag:

1. `data-method`: the request type, GET, POST, PUT, etc.
2. `data-target`: the url to send/get the data
3. `data-disabled`: `true` to disable the tag until the request is done else just put `false`
4. `data-once`: `true` to disable the tag entirely after the first request, default is `false`

example:

```html
<button data-target="http://example.com/post/post-id/" data-method="DELETE" data-disabled="true">Delete Article</button>
```

or you can use the javascript apis, note the data attributes have the priority.

# API

### Options

First you need to set your options, here's the available options (the seen values are the default):
```javascript
{
    async: true, // if set to false calls will be synchronous
    parse: false, // if you have query string, it will add them to the request body
    target: null, // the url
    method: "GET", // the request method
    headers: {}, // the HTTP headers
    timeout: 0, // milliseconds to wait before cancelling the request, 0 means no timeout 
    data: {}, // request body specially for POST and PUT requests
    disable: true, // to disable the clicking event until the request is finished
    once: false // to disable the click event after the first request is processed
}
```

### Vanilla
The zero dependency version, just add it to any project you have and it will work

```javascript
restintag(selector: String, options: Object, successCallback: Function, errorCallback: Function): void
```

### jQuery
after adding jQuery use the `restintag()` function to do the magic

```javascript
$(".selector").restintag(options: Object, successCallback: Function, errorCallback: Function): jQuery
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

# Contributors

List of people who contributed to this project, thank you people:

- [Israel Roldan](https://github.com/israelroldan)
- [Murat Doğan](https://github.com/muratdogan17)

# License

This project is under the MIT license.
