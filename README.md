# Working with Bind and Reverse Shells-Project

## Objective

Learn how to find and take advantage of security flaws in operating systems and apps running on hosts connected to a company's network. Additionally, the ideas and methods included in this series are in line with the Cyber Kill Chain's Weaponization, Delivery, Exploitation, Installation, and C2 stages. You will learn how to conduct a network penetration test firsthand.

### Skills Learned

- Creating and experimenting with bind and reverse shell connections
- Write and test a Python script that loads the reverse shell onto target machine
- writing a reverse shell client and tcp server listener


### Tools Used

- Netcat
- Python

## Steps

**Remote Shells using Netcat**

1. On Kali Linux, use the ip addr command to obtain its IP address on eth0.

![Screenshot 2024-12-04 123151](https://github.com/user-attachments/assets/c6e64102-10ca-4da9-9c74-6c37d0ad5d7c)

2. Next, we need to copy the Windows version of Netcat over to Metasploitable 3 and start a web server using Python3.

![Screenshot 2024-12-04 123222](https://github.com/user-attachments/assets/a10c66e5-3b65-47bd-bd3d-f75016f03ef9)

3. Next, on Metasploitable 3, open the web browser and go to http://<Kali-Linux-IPaddress>:8080. Download the nc.exe file from Kali Linux and copy it to the C:\Windows\System32 directory on Metasploitable 3.


![Screenshot 2024-12-04 123740](https://github.com/user-attachments/assets/e1d9e11a-eabc-4db9-b959-87e0febb9b73)

![Screenshot 2024-12-04 123954](https://github.com/user-attachments/assets/c2a6a18d-712a-4330-b04d-c9217f29bc0d)

4. start a listener (server) on Kali Linux, use the following command:
   
![Screenshot 2024-12-04 124046](https://github.com/user-attachments/assets/0ed0c5bd-d2ef-4330-87d2-62af8fd237cb)

5. on Metasploitable 3, open the Windows Command Prompt and use the following
command to connect to Kali Linux (listener):

![Screenshot 2024-12-04 125014](https://github.com/user-attachments/assets/e789d310-b5d4-494d-a7c7-1c1a50c8b384)

![Screenshot 2024-12-04 125001](https://github.com/user-attachments/assets/f232e455-f98e-4b11-b47d-af519e820c19)


Once the session has been established from Metasploitable 3 (client) to Kali Linux
(listener), you can type messages on the shell (in the Windows Command Prompt) and
see them reflected on the Kali terminal (listener).

---------------------------------------------------------------------------------------------------------------------

**Creating a Bind Shell**

1. On Kali Linux, use the following command to start a listener that binds to the native bash
shell:
![Screenshot 2024-12-04 125718](https://github.com/user-attachments/assets/5715cc71-d981-418a-993f-4011feeef6b0)

---------------------------------------------------------------------------------------------------------------
2. Next, on Metasploitable 3, open the Windows Command Prompt and use the following
command to establish a Netcat connection to Kali Linux (listener):

3. Once the connection has been established, you have successfully established a bind shell.
Used this connection to execute linux commands. 




![Screenshot 2024-12-04 125805](https://github.com/user-attachments/assets/948e36d5-00c1-4ce8-b082-9b7c5b6e9d63)
![Screenshot 2024-12-04 130100](https://github.com/user-attachments/assets/a4edabe2-a7bd-4ed9-a6e7-f40d99bcacb8)

----------------------------------------------------------------------------------------------------------------------

**Creating a Reverse Shell**

1. On Kali Linux, open the Terminal and use the following commands to set up a listener using
Netcat:

![Screenshot 2024-12-04 130100](https://github.com/user-attachments/assets/3df0f052-5ece-4311-b6df-1832ac631792)

2. Next, on Metasploitable 3 (client), open the Windows Command Prompt and use the
following command to create a reverse connection to the listener:

![Screenshot 2024-12-04 130119](https://github.com/user-attachments/assets/c36ac578-1105-47a6-8b1f-d43b5ff02b38)

3.  Established connection to the listener from the Windows
command prompt and on Kali Linux you will now have a reverse shell from the Windows
client machine on your Linux terminal. So, the Windows command prompt shows up on
both machines.

![Screenshot 2024-12-04 130242](https://github.com/user-attachments/assets/d7eecebe-749e-4903-a755-343bd9eb99e0)

![Screenshot 2024-12-04 130227](https://github.com/user-attachments/assets/ef600a42-88c5-4123-8274-2fa8d4b09c8f)
