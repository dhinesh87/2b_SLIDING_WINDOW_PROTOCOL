# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME : DHINESH.M
## REGISTER NUMBER : 212223040040
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### CLIENT
```py
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr=s. accept()
size=int(input ("Enter number of frames to send"))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
  while(i<len(l)):
   st+=s
   c.send(str(l[i:st]).encode())
   ack=c.recv(1024).decode()
   if ack:
    print(ack)
    i+=s

```
### SERVER
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
## OUTPUT
### CLIENT OUTPUT:

![CLIENT](https://github.com/dhinesh87/2b_SLIDING_WINDOW_PROTOCOL/assets/146917182/c0b39418-09a1-4fcb-9a6d-a1bcafb88e69)

### SERVER OUTPUT:
![SERVER](https://github.com/dhinesh87/2b_SLIDING_WINDOW_PROTOCOL/assets/146917182/19704f64-dd66-4dea-b558-3f67121f966a)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
