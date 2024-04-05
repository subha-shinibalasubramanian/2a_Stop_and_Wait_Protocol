# 2a_Stop_and_Wait_Protocol
**NAME :SUBHASHINI.B**  
**REGISTER NUMBER :212223040211** 
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

**CLIENT**

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
**SERVER**

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Received ".encode())
```

## OUTPUT

**CLIENT**
![image](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/164154478/e1489cb1-4631-4cad-8e6f-41375c99562c)

**SERVER**
![Screenshot 2024-04-05 105330](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/164154478/f70f3840-52b7-408f-8cfb-e395b3e90aee)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
