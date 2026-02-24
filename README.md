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
## SERVER:
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for client...")
c, addr = s.accept()
print("Connected from", addr)

while True:
    msg = c.recv(1024)
    if not msg:
        break

    print("Client >", msg.decode())
    reply = input("Server > ")
    c.sendall(reply.encode())

c.close()
s.close()
```
## CLIENT :
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    if msg.lower() == "exit":
        break

    s.sendall(msg.encode())

    data = s.recv(1024)
    if not data:
        print("Server disconnected.")
        break

    print("Server >", data.decode())

s.close()
```
## OUTPUT




<img width="1919" height="1101" alt="Screenshot 2026-02-24 145721" src="https://github.com/user-attachments/assets/ca2facba-59bb-457e-bfd7-c015a5024704" />




## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
