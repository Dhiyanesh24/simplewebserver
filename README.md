# Ex01 Developing a Simple Webserver
## Date:20/9/23

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<!DOCTYPE html>
<html>
<head>
<title>Dhiyaneshwar (212222110009) </title>
</head>
<body>
<h1><u>Revenue generating companies</u><h1>
<ul>
<li>apple</li>
<li>amazon</li>
<li>microsoft</li>
<li>youtube</li>
<li>instagram</li>
</body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![websimple1](https://github.com/Dhiyanesh24/simplewebserver/assets/118362288/ad28f5dd-5d49-4fc8-a134-52707a86bdc9)
![websimple](https://github.com/Dhiyanesh24/simplewebserver/assets/118362288/9961bc3f-4a76-49e2-a197-528ca3b9f0a0)


## RESULT:
The program for implementing simple webserver is executed successfully.
