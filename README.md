# Ex.No:1a  			Study of Socket Programming
## Aim: 
To perform a study on Socket Programming
@@ -53,6 +53,67 @@ Socket programming finds applications in various domains, including web developm
4.	Networked Games: Online multiplayer games rely on socket programming to facilitate communication between game clients and servers.
5.	RPC mechanisms: which allow processes to execute code on a remote server, often use socket programming for communication.

## Program:
1. server.py
```
import socket

# Create socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind socket to IP and port
host = '127.0.0.1'
port = 12345
server_socket.bind((host, port))

# Listen for connections
server_socket.listen(1)
print("Server is waiting for connection...")

# Accept client connection
conn, addr = server_socket.accept()
print("Connected to:", addr)

# Receive data from client
data = conn.recv(1024).decode()
print("Client says:", data)

# Send response to client
message = "Hello Client, message received!"
conn.send(message.encode())

# Close connection
conn.close()
server_socket.close()
```
2. client.py
```
import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
host = '127.0.0.1'
port = 12345
client_socket.connect((host, port))

# Send message to server
message = "Hello Server!"
client_socket.send(message.encode())

# Receive response from server
data = client_socket.recv(1024).decode()
print("Server says:", data)

# Close socket
client_socket.close()
```

## Output:

<img width="989" height="391" alt="Screenshot 2026-11-21 at 8 43 39 AM" src="https://github.com/user-attachments/assets/2a322850-7bac-401d-95e7-7243a7eb12ac" />


## Result:
Thus the study of Socket Programming Completed Successfully
