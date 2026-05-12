# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Received ".encode())
```
## CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("Enter a data: ")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
    print(ack)
    continue
   else:
    c.close()
    break
```
## OUTPUT
## SERVER
<img width="961" height="405" alt="S 2a" src="https://github.com/user-attachments/assets/356a1a5b-bc98-44d3-ab75-c2296ce5095c" />

## CLIENT
<img width="960" height="405" alt="C 2a" src="https://github.com/user-attachments/assets/7476cc05-4b66-41e4-a6b3-fe7c4a3b7b29" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
