# Code-stimulating-RARP-ARP-Protocol

WRITE A CODE SIMULATING ARP /RARP PROTOCOLS

EXP: 4

DATE:27.03.23

AIM:

To write a python program for simulating ARP protocols using TCP.

ALGORITHM:

Client:

1.Start the program
2.Using socket connection is established between client and server.
3.Get the IP address to be converted into MAC address.
4.Send this IP address to server.
5.Server returns the MAC address to client.

Server:

1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.

PROGRAM:

CLIENT:

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

SERVER:

import socket

s=socket.socket()

s.connect(('localhost',8000))

while True:

ip=input("Enter logical Address : ")

s.send(ip.encode())

print("MAC Address",s.recv(1024).decode())

OUTPUT:
CLIENT:
![Screenshot from 2023-05-12 20-56-12](https://github.com/Harsayazheni/Code-stimulating-RARP-ARP-Protocol/assets/118708467/1b89cc6b-8c47-41b7-a946-e21e7bb9ec63)

SERVER:
![Screenshot from 2023-05-12 20-56-20](https://github.com/Harsayazheni/Code-stimulating-RARP-ARP-Protocol/assets/118708467/edb77c7b-2efc-4fab-bfd1-a4ec1271a0e1)

RESULT:

Thus, the python program for simulating ARP protocols using TCP was successfully
executed.
