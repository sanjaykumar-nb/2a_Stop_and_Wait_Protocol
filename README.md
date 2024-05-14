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
client
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
  i=input("Enter the data: ")
  c.send(i.encode())
  ack=c.recv(1024).decode()
  if ack:
      print(ack)
      continue
  else:
      c.close
      break

server
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Received".encode())

```
## OUTPUT
client
![image](https://github.com/sanjaykumar-nb/2a_Stop_and_Wait_Protocol/assets/154039979/a8593787-46c8-4339-948a-e1b1e329190a)
server
![image](https://github.com/sanjaykumar-nb/2a_Stop_and_Wait_Protocol/assets/154039979/137b2a1f-4af1-4659-b521-eb03f6e0f11e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
