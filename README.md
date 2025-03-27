# EX01 Developing a Simple Webserver

# Date:27.03.2025
# AIM:
To develop a simple webserver to serve html pages and display the Details of My college

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

from http.server import BaseHTTPRequestHandler, HTTPServer

class My(BaseHTTPRequestHandler):
    html_content = '''
<!doctype html>
<html>
<head>
<title> Web Server</title>
</head>
<body>
<h1><center>About my college</center></h1>
   <table border="1" cellpadding="10" align="center">
        <tr>
            <th bgcolor="blue">Specification</th>
            <th bgcolor="green">Details</th>
        </tr>
        <tr>
            <td>Name</td>
            <td>Saveetha Engineering college</td>
        </tr>
        <tr>
            <td>Courses</td>
            <td>CSE,AI&DS,AI&ML,IT,ECE,etc.</td>
        </tr>
        <tr>
            <td>Fees Structure</td>
            <td>Based on your 12th marks</td>
        </tr>
        <tr>
            <td>Placement</td>
            <td>97%</td>
        </tr>
        <tr>
            <td>Counselling code</td>
            <td>1216</td>
        </tr>
        <tr>
            <td>Infrastructure</td>
            <td>Not Bad at all(but a little bad)</td>
        </tr>
    </table>
</body>
</html>

'''    
    def do_GET(self):
        content = self.html_content
        print("Request received")
        self.send_response(200)
        self.send_header('Content-Type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

# Define server address and port
server_address = ('', 8000)  # Host on all available IPs, port 8000
httpd = HTTPServer(server_address, My)

print("My webserver is running...")
httpd.serve_forever()
# OUTPUT:

![alt text](<Screenshot 2025-03-27 215056.png>)
![alt text](<Screenshot 2025-03-27 215201.png>)
# RESULT:
The program for implementing simple webserver is executed successfully.
