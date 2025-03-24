# EX01 Developing a Simple Webserver

# Date:24.03.2025
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
```from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<html lang="en">
<head>
    <title>lap specs.</title>
</head>
<body>
       <table border="3" cellpadding="10">
        <caption style="font-size: x-large;">LAPTOP SPECIFICATTION</caption>
        <TR>
            <TD>BRAND</TD>
            <TD>LENOVO</TD>
        </TR>
        <TR>
            <TD>SERIES</TD>
            <TD>THINKPAD E16 GEN1</TD>
        </TR>
        <TR>
            <TD>PROCESSOR BRAND</TD>
            <TD>INTEL</TD>
        </TR>
        <TR>
            <TD>PROCESSOR TYPE</TD>
            <TD>CORE I5</TD>
        </TR>
        <TR>
            <TD>GRAPHICS CARD INTERFACE</TD>
            <TD>INTEGRATED</TD>
        </TR>
        <TR>
            <TD>OPERATING SYSTEM</TD>
            <TD>WINDOWS 11 HOME</TD>
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
httpd.serve_forever()
```

# OUTPUT:
![alt text](<Screenshot 2025-03-24 152914.png>)
![alt text](<Screenshot 2025-03-24 175232.png>)
# RESULT:
The program for implementing simple webserver is executed successfully.

