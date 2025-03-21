# EX01 Developing a Simple Webserver
## Name:Naresh Kumar R
## Ref no:212224040213
## Date:21.03.2025

## AIM:
To develop a simple webserver to serve html pages and displays a basic webpage with a heading, a paragraph, and a button


## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Simple Web Page</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is a simple HTML page.</p>
    <button onclick="alert('You clicked the button!')">Click Me</button>
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
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```



## OUTPUT:

![Screenshot 2025-03-21 083903](https://github.com/user-attachments/assets/2700a03d-f0b0-4891-846a-0814d8aba2e8)



## RESULT:
The program for implementing simple webserver is executed successfully.
