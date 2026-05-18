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
~~~
Server.py

import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())

clinent.py

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
~~~
## OUTPUT

## clinent
<img width="1767" height="341" alt="image" src="https://github.com/user-attachments/assets/9f9ca7be-5eea-40d9-bedf-14385d5fa57d" />
## server
<img width="1854" height="227" alt="image" src="https://github.com/user-attachments/assets/b491fea5-e459-4bab-b0b7-0e9e6608ad0e" />





## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
