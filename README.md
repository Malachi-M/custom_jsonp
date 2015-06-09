# custom_jsonp

## Goal


To allow the caller to interchangeably call: 

```
request.json("https://vimeo.com/api/v2/video/128510631.json", function(response) {
  // Handle response data
});
```
or
```
request.jsonp(“https://vimeo.com/api/v2/video/128510631.json", function(response) {
  // Handle response data
});
```
The caller could also fire off several requests, like
```
request.jsonp("https://vimeo.com/api/v2/video/128510631.json", function(response) {
  // Handle response data.
});
request.jsonp("https://vimeo.com/api/v2/video/128510632.json", function(response) {
  // Handle response data.
});
request.jsonp("https://vimeo.com/api/v2/video/128510633.json", function(response) {
  // Handle response data.
});
```

It is proposed that callbacks may each do different things with the response.
Request.jsonp will automatically append the ?callback=…to the URL. It could assume that the API used “callback” as the parameter name for the JSONP callback, but would be configurable.

## Example
	
(Codepen Example)[https://codepen.io/bb/pen/xGdjdQ?editors=101]