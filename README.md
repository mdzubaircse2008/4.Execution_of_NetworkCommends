# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.

## PROGRAM
### Server.py
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    ip = input("Enter the website you want to ping: ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
### Client.py
```
import socket
from pythonping  import ping
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Waiting for connection...")
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    try:
        result = ping(hostname, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Not Found".encode())
```

## Output
### Server Side:
<img width="1466" height="1009" alt="image" src="https://github.com/user-attachments/assets/8e27a218-2569-4c4e-ae03-007209d20a50" />

### Client Side:
<img width="1488" height="932" alt="image" src="https://github.com/user-attachments/assets/aa1aebb3-08ef-48c8-bcdc-ded8435bc6ad" />


## Result
Thus Execution of Network commands Performed 
