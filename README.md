# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
server side:



import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)


PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    
    s.bind((HOST, PORT))
    
    s.listen()
    
    conn, addr = s.accept()
    
    with conn:
       
        print(f"Connected by {addr}")
        
        while True:
            
            data = conn.recv(1024)
            
            if not data:
               
                break
            
            conn.sendall(data)

 
Client side:


import socket


HOST = "127.0.0.1"  # The server's hostname or IP address

PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    
    s.connect((HOST, PORT))
    
    s.sendall(b"Hello, world")
    
    data = s.recv(1024)


print(f"Received {data!r}")

## OUTPUT:
Server Output:
 ![image](https://github.com/22003197/Echoserver/assets/124332243/36fd9fac-b570-42b1-878b-fff161f9fc99)

Client Output:
 ![image](https://github.com/22003197/Echoserver/assets/124332243/b9ae3911-7787-4b7b-a6d1-065efa84e62d)

## RESULT:
The program is executed successfully
