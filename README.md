# HttpRequest Lib for C++



### Class
- HttpRequest

### Methods
- setMethod(int method) set method value HTTP_METHOD_GET, HTTP_METHOD_POST, HTTP_METHOD_DELETE, HTTP_METHOD_PUT
- setHost(string host) set host name
- setPath(string path) set path for request
- setPort(int number) set port number - default: 80
- setHeader(string key, string value) set a header value and/or add header
- setBody(string body) set body value
- commit() sends request to server
- getBody() returns body as string

### Response Status
- HTTP_ERROR error on request
- HTTP_SUCCESS 
- HTTP_HOST_UNKNOWN

### Example
- GET
``` C++
	HttpRequest request;
	request.setHost(argv[1]);
	request.setPath(argv[2]);
	request.setPort(atoi(argv[3]));
	request.setHeader("Content-Type", "application/json");
	request.setMethod(HTTP_REQUEST_GET);
	request.commit();
	std::cout << request.getBody() << std::endl;
```
- POST
``` C++
	HttpRequest request;
	request.setHost(argv[1]);
	request.setPath(argv[2]);
	request.setPort(atoi(argv[3]));
	request.setHeader("Content-Type", "application/json");
	request.setMethod(HTTP_REQUEST_POST);
	request.setHeader("token", "authentication token");
	request.setBody("{test:\"hello world\"}");
	request.commit();
	std::cout << request.getBody();
```

## Build
```	
	make 
```
## Run Example
```	
	make run
```
## Debug (LLDB)
```
	make debug
```	