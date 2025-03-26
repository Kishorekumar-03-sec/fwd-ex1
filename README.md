# EX01 Developing a Simple Webserver
## Date:22/03/2025
## Name: Kishorekumar S
## Reg no:212224040162

## AIM:
To develop a simple webserver to serve html pages and display the background colour using html code.

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

    from http.server import HTTPServer, BaseHTTPRequestHandler
    content = """
    <!DOCTYPE html>
    <html>
    <body style="background-color:powderblue;">

    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>

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

## OUTPUT:

![Screenshot 2025-03-26 182413](https://github.com/user-attachments/assets/6f1a785a-f10b-4067-a59c-bab3cd276d3a)
![Screenshot 2025-03-26 182505](https://github.com/user-attachments/assets/4f68bf1b-00ef-450e-92ed-c49ea3e21445)
![Screenshot 2025-03-26 182533](https://github.com/user-attachments/assets/379e3910-8939-4071-8ddd-1cf6806bbd71)

## RESULT:
The program for implementing simple webserver is executed successfully.

