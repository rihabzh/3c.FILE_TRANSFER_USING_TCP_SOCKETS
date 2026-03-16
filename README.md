# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
# server :
```
import socket

s = socket.socket()
s.bind(("localhost",8000))
s.listen(1)

print("Waiting for connection...")
c,addr = s.accept()

f = open("received.txt","wb")

data = c.recv(1024)
while data:
    f.write(data)
    data = c.recv(1024)

f.close()
print("File received")
```
# client :
```
import socket

s = socket.socket()
s.connect(("localhost",8000))

f = open("file.txt","rb")

data = f.read(1024)
while data:
    s.send(data)
    data = f.read(1024)

f.close()
print("File sent")
```
## OUPUT
# client:

![alt text](<Screenshot 2026-03-16 230231.png>)
# server :
![alt text](<Screenshot 2026-03-16 230221.png>)

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
