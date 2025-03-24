# EX01 Developing a Simple Webserver
## Date: 24-03-2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content="""
<!DOCTYPE html>

<html>
<head>
    <title>TCP/IP Protocol Suite</title>
    <style>
        table {
            width: 80%;
            border-collapse: collapse;
            margin: 20px auto;
            font-family: Arial, sans-serif;
            font-style:normal;
            color: #ffffff;
        }
        th, td {
            border: 1px solid #ffffff;
            padding: 20px;
            font-size: 22px;
            text-align: center;
        }
        th {
            background-color: #4CAF50;
            color: rgb(0, 0, 0);
            font-size: 30px;
        }
        
        h1{
            color :#4CAF50;
            text-align: center;
            font-size: 60px;
        }
        body{
            background: #181717;
        }
    </style>
</head>
<body>

    <h1>TCP/IP Protocol Suite</h1>

    <table>
        <tr>
            <th>LAYER</th>
            <th>PROTOCOLS (EXAMPLES)</th>
            <th>FUNCTION</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>HTTP, HTTPS, FTP, SMTP, DNS, DHCP</td>
            <td>Provides network services to applications</td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>TCP, UDP</td>
            <td>Manages end-to-end communication</td>
        </tr>
        <tr>
            <td>Internet Layer</td>
            <td>IP (IPv4, IPv6), ICMP, ARP, IGMP</td>
            <td>Handles addressing and routing</td>
        </tr>
        <tr>
            <td>Network Access Layer</td>
            <td>Ethernet, Wi-Fi, PPP, SLIP</td>
            <td>Manages physical data transmission</td>
        </tr>
    </table>

</body>
</html>
```
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:

![alt text](<Screenshot 2025-03-24 143719.png>)
![alt text](<Screenshot 2025-03-24 143739.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
