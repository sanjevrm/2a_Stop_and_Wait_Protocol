# 2a_Stop_and_Wait_Protocol
## Name:Sanjev R M
## REG NO:212223040186
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
# CLIENT:
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

## SERVER
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())  
```
# OUTPUT
## CLIENT:

![image](https://github.com/sanjevrm/2a_Stop_and_Wait_Protocol/assets/155142423/96ca0d6a-abd7-430a-8461-4525ea03db9c)


## SERVER:

![image](https://github.com/sanjevrm/2a_Stop_and_Wait_Protocol/assets/155142423/7a14d9fe-b5b8-4509-8dec-b551ce26c920)



# Result:
Thus python program to perform stop and wait protocol was successfully executed.
