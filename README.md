# Develop By:NaveenKumar.T
# Reg No  : 212223220067
# 2a_Stop_and_Wait_Protocol
## AIM:
To write a python program to perform stop and wait protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
## Client:
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

# OUTPUT:
## Client:
![306664559-5e7536db-fd1a-4b3f-9358-211a771e8100](https://github.com/820NaveenKumar208/2a_Stop_and_Wait_Protocol/assets/154746066/b748497b-f9a0-4850-8edd-0209f601fceb)

## Server:
![306664797-08351b08-bc67-42a0-975a-88d1f145a355](https://github.com/820NaveenKumar208/2a_Stop_and_Wait_Protocol/assets/154746066/b8ba37b4-69f2-4b15-8af0-4c3f7b4858ef)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
