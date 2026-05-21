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

```
Name:ASHFAK N
Reg no:212225230022
```

client.py
```python
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

Server.py
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
client

<img width="946" height="341" alt="image" src="https://github.com/user-attachments/assets/dfe32f27-b68f-4476-8458-1234c0a75ac6" />

server

<img width="940" height="259" alt="image" src="https://github.com/user-attachments/assets/1b5bc432-d98b-4982-95c3-2842f3a5410e" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
