# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# DATE: 16/03/23

# AIM : 
To write a python program to perform stop and wait protocol

# ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program
```
# PROGRAM :
# CLIENT PROGRAM:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
# SERVER PROGRAM:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
 ```
# OUTPUT :
# CLIENT OUTPUT :

![1](https://github.com/Praveenanagaraji22/EX-2/assets/119393514/cd135b0d-d42b-45ff-bf1b-8ff6596081b6)


# SERVER OUTPUT :
![2](https://github.com/Praveenanagaraji22/EX-2/assets/119393514/539f24b1-e545-4b43-95ae-61f128a9b19d)


# RESULT : 

Thus, python program to perform stop and wait protocol was successfully executed.




