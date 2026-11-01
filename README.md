# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
ECHO_SERVER.PY
```
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

server.bind(('localhost', 12345))

server.listen(1)

print("Echo Server is waiting for connection...")

client, address = server.accept()

print("Client connected:", address)

while True:
    message = client.recv(1024).decode()

    if message.lower() == "exit":
        print("Client disconnected")
        break

    print("Received from client:", message)

    client.send(message.encode())

client.close()
server.close()

```
ECHO_CLIENT.PY
```
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

client.connect(('localhost', 12345))

print("Connected to Echo Server")

while True:
    message = input("Enter message: ")

    client.send(message.encode())

    if message.lower() == "exit":
        break

    response = client.recv(1024).decode()

    print("Echo from server:", response)

client.close()

```




## OUPUT
<img width="1920" height="1020" alt="3a cn" src="https://github.com/user-attachments/assets/30144db8-c46d-4d12-9f25-92dffc53d424" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
