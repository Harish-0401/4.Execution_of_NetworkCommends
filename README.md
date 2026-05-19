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
Server 
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
## Client :
~~~
import socket

# Create socket
s = socket.socket()

host = socket.gethostname()
port = 60000

# Connect to server
s.connect((host, port))

# Receive file
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
## Output
## Server
<img width="359" height="70" alt="image" src="https://github.com/user-attachments/assets/858f2fcb-cf74-4f98-bcae-88eabf518666" />
## Client 
<img width="664" height="103" alt="image" src="https://github.com/user-attachments/assets/afd88e44-fdf2-4207-ab26-38825f8ab39d" />


## Result
Thus Execution of Network commands Performed 
