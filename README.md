# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
### Server:
```
import socket

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(5)

print("Server Waiting...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    print("Client >", ClientMessage)

    if ClientMessage.lower() == "exit":
        break

    msg = input("Server > ")

    c.send(msg.encode())

c.close()
s.close()
```
### Client:
```
import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    reply = s.recv(1024).decode()

    print("Server >", reply)

    if msg.lower() == "exit":
        break

s.close()
```
## OUPUT
### Server:

<img width="392" height="117" alt="image" src="https://github.com/user-attachments/assets/74bfc14b-f554-4308-b357-4f341d5194b6" />

### Client:

<img width="652" height="102" alt="image" src="https://github.com/user-attachments/assets/336ed2af-ba5e-499c-b059-b63b8d28fc04" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
