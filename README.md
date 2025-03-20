# EX01 Developing a Simple Webserver
## Date:20.03.2025
# NAME: K DHANUSRI POOJA
# REGISTER NUMBER: 212224040068


## AIM:
To develop a simple webserver to serve html pages and display the table of students.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
 <html lang="en">
 <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>11th table</title>
 </head>
 <body>
     <h1>Webserver</h1>
     <table border="1">
         <tr>
             <th>Name</th>
             <th>Register no.</th>
             <th>Department</th>
         </tr>
         <tr>
             <td>DHANUSRI POOJA K</td>
             <td>212224040068</td>
             <td>CSE</td>
         </tr>
         <tr>
             <td>CLARISSA K</td>
             <td>212224230047</td>
             <td>AIDS</td>
         </tr>
         <tr>             
             <td>ASHIKA TR</td>
             <td>212224220011</td>
             <td>IT</td>
             
          </tr>
         <tr>
             <td>RESIKA M</td>
             <td>212224220079</td>
             <td>IT</td>
         
         </table>

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
~~~


## OUTPUT:
![alt text](<../Screenshot 2025-03-20 093556.png>)

![alt text](<../Screenshot 2025-03-20 093637.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

