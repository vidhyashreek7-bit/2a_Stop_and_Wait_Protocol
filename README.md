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
### Developed By: VIDHYA SHREE K
### Register No: 212225230296
### Client:
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
### Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
### Client:
<img width="960" height="600" alt="Screenshot 2026-05-21 101317" src="https://github.com/user-attachments/assets/b28a97f1-1a6e-445f-b870-38050b457f9a" />

### Server:
<img width="960" height="600" alt="Screenshot 2026-05-21 101328" src="https://github.com/user-attachments/assets/acfa8a03-3f20-46bb-bd84-92c0d358f475" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
