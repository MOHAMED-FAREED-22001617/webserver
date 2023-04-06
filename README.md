# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
<h2>4.Angular </h2>
<h2>5. Ruby on rails </h2>
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
httpd.serve_forever()\
```
## OUTPUT :
![Screenshot from 2023-04-06 09-09-24](https://user-images.githubusercontent.com/121412904/230266497-1f41afee-9370-49e5-abb1-6e6464fb5bfe.png)


![Screenshot from 2023-04-06 09-09-10](https://user-images.githubusercontent.com/121412904/230266551-20deda84-3a1b-4a4f-893c-639c41922bf2.png)


## RESULT:
The program is executed succesfully
