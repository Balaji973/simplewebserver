# EX01 Developing a Simple Webserver
## Date: 26.10.2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
content = '''

 <!DOCTYPE html>

 <html>

<title>web server</title>

<body>

<table border="2" cellspacing="10" cellpadding="6">

<caption> personal information </caption>

<tr>

<th>s.no</th>

<th></th>

<th></th>

</tr>

<tr>

<th>1</th>
<th> device name</th>

<th>balaji</th>

</tr>

<tr>

<th>2</th>

<th>RAM</th>

<th>16.0 GB</th>

</tr>

<tr>

<th>3</th>

<th>system type</th>

<th>64-bit os</th>

</tr>

<tr>

<th>4</th>
<th>processor</th>

<th>13th Gen Intel</th>




</tr>

<tr>

<th>5</th>

<th>device id</th>

<th>00342-42709-13302-AAOEM</th>

</body>

</html>
'''

class myhandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response (200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('',8000)

httpd = HTTPServer(server_address, myhandler)

print("my webserver is running...")

httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot 2024-10-26 105825.png>)

![alt text](<Screenshot 2024-10-26 105911.png>)




## RESULT:
The program for implementing simple webserver is executed successfully.
