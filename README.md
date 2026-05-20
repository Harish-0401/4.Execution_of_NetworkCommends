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
<BR>
## Programe
## Service 
~~~
~~~
import socket
from pythonping import ping

s = socket.socket()

s.bind(('localhost', 8000))
s.listen(5)

print("Server waiting for connection...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    hostname = c.recv(1024).decode()

if not hostname:
        break

  try:
        result = ping(hostname, verbose=False)
        c.send(str(result).encode())
    except Exception:
        c.send("Not Found".encode())

c.close()
s.close()

## Client 

import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping: ")

s.send(ip.encode())

response = s.recv(1024).decode()

 print(response)
~~~
~~~
## Output
## Server
<img width="616" height="483" alt="WhatsApp Image 2026-05-20 at 3 42 56 PM" src="https://github.com/user-attachments/assets/7739f415-d9b6-492b-9418-0786e01c7039" />


## Client 
<img width="652" height="113" alt="WhatsApp Image 2026-05-20 at 3 43 05 PM" src="https://github.com/user-attachments/assets/6158cf3a-61a0-4e76-a2d2-60b857578460" />




## Result
Thus Execution of Network commands Performed 
