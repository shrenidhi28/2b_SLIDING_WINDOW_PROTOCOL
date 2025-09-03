# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name: Shrenidhi C
## Register No: 212223040196
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

```
server.py

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgment recieved from the server".encode())

client.py
import socket 
s=socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input ("Enter Window Size : "))
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
## OUPUT

# client
![WhatsApp Image 2025-09-03 at 11 52 37_bd2f9131](https://github.com/user-attachments/assets/297bb130-6a46-4293-92ac-187922850b3e)

# server


![WhatsApp Image 2025-09-03 at 11 52 59_8eba730a](https://github.com/user-attachments/assets/a1ea3a8a-80ff-4127-8e86-70c1604e0f47)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
