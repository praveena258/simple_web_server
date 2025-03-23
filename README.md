# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
'''from django.shortcuts import render
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<html lang="en">
<head>
    <title>Top Software Industries</title>
</head>
<body>

     <table border="2" cellpadding="6">
        <caption style="font-size: x-large;">LAPTOP SPECIFICATTION</caption>
        <TR>
            <th>S.NO</th>
            <th>COMPANIES</th>
            <th>REVENUE</th>
        </TR>
        <TR>
            <th>1</th>
            <th>Microsoft</th>
            <th>65 billion</th>
        </TR>
        <TR>
            <th>2</th>
            <th>oracle</th>
            <th>29.6 billion</th>
        </TR>
        <TR>
            <th>3</th>
            <th>IBM</th>
            <th>29.1 billion</th>
        </TR>
        <TR>
            <th>4</th>
            <th>SAP</th>
            <th>6.4 billion</th>
        </TR>
        <TR>
            <th>5</th>
            <th>symentee</th>
            <th>5.6 billion</th>
        </TR>
     </table> 
</body>
</html>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()'''
# OUTPUT:
# RESULT:
The program for implementing simple webserver is executed successfully.
