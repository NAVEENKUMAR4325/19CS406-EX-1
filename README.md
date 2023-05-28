# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :09-03-2023

AIM : To write a python program to perform stop and wait protocol


ALGORITHM :
           1. Start the program.
           2. Get the frame size from the user
           3. To create the frame based on the user request.
           4. To send frames to server from the client side.
           5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
           6. Stop the program




PROGRAM :

CLIENT:

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

SERVER:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```



OUTPUT:

CLIENT OUTPUT:

![CLIENT OUTPUT](https://github.com/NAVEENKUMAR4325/19CS406-EX-1/assets/119479566/e73791ab-2d46-4bd4-b9f3-01c420219f03)

SERVER OUTPUT:

![SERVER OUTPUT](https://github.com/NAVEENKUMAR4325/19CS406-EX-1/assets/119479566/8c4c9eda-eb7f-4cfc-82c0-11afd2d1627f)





RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

