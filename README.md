# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
       c.send(address[ip].encode())
    except KeyError:
       c.send("Not Found".encode())
```
server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP
CLIENT:
![Screenshot 2024-04-29 132017](https://github.com/Sachin-0305/2c.ARP_RARP_PROTOCOLS/assets/149985717/8fcb787d-261d-4cc8-9fd3-cb51868609e8)
SERVER:
![Screenshot 2024-04-29 132026](https://github.com/Sachin-0305/2c.ARP_RARP_PROTOCOLS/assets/149985717/dbb8c3b3-94dc-46eb-9dde-4f3a4f0dfa12)

## PROGRAM - RARP

CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
       c.send(address[ip].encode())
    except KeyError:
       c.send("Not Found".encode())
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())

```
## OUPUT -RARP
CLIENT:
![Screenshot 2024-04-29 132320](https://github.com/Sachin-0305/2c.ARP_RARP_PROTOCOLS/assets/149985717/2e6eb7db-6a75-468d-a58c-ab9fe473a00c)
SERVER:
![Screenshot 2024-04-29 132332](https://github.com/Sachin-0305/2c.ARP_RARP_PROTOCOLS/assets/149985717/5cd4dc4d-49b5-4838-8024-5c65541cd3bd)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
