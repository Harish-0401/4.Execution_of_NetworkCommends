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
~~~
Server :
~~~
import socket

s = socket.socket()

host = socket.gethostname()
port = 60000


s.bind((host, port))
s.listen(1)

print("Server listening...")

conn, addr = s.accept()
print("Got connection from", addr)

filename = "sample.txt"  # Make sure this file exists
with open(filename, "rb") as f:
    data = f.read(1024)
    while data:
        conn.send(data)
        data = f.read(1024)

print("File sent successfully")

conn.close()
s.close()
~~~
~~~
Client :
~~~
~~~

import socket

s = socket.socket()

host = socket.gethostname()
port = 60000


s.connect((host, port))


with open("received_file.txt", "wb") as f:
    while True:
        print("Receiving data...")
        
data = s.recv(1024)
    print("Data =", data)

  if not data:
     break
  f.write(data)

print("Successfully received the file")

s.close()
print("Connection closed")
~~~
~~~
## Output
## Server
<img width="616" height="483" alt="WhatsApp Image 2026-05-20 at 3 42 56 PM" src="https://github.com/user-attachments/assets/cfde1c4a-65c5-495d-934e-6bb5518025b3" />

## Client 
<img width="616" height="483" alt="WhatsApp Image 2026-05-20 at 3 42 56 PM" src="https://github.com/user-attachments/assets/fa8da9e1-c2e0-4dd6-9b6e-172174553c1e" />



## Result
Thus Execution of Network commands Performed 
