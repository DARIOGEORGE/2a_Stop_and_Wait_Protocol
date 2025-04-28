# ExNo.2a_Stop_and_Wait_Protocol
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
```python
1.Client
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
```python
2.server
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT

1.Client

![image](https://github.com/user-attachments/assets/aa6a1d6c-65bb-4f75-94d3-bea84837c8ed)

2.Server

![image](https://github.com/user-attachments/assets/93f3c52c-e7ee-4a79-9fab-93e070259fd1)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
