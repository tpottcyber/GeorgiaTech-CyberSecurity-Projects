## Network Analysis
**Time Thieves**

At least two users on the network have been wasting time on YouTube. Usually, IT wouldn't pay much mind to this behavior, but it seems these people have created their own web server on the corporate network. So far, Security knows the following about these time thieves:

-	Configured an Active Directory network.
-	The users are constantly watching videos on YouTube.
- Their IP addresses are somewhere in the range 10.6.12.0/24.

1.	What is the domain name of the users' custom site?
- frank-n-ted.com

2.	What is the IP address of the Domain Controller (DC) of the AD network?
- 10.6.12.203 / 205.185.125.104
- Frank-n-Ted-DC.frank-n-ted.com

3.	What is the name of the malware downloaded to the 10.6.12.203 machine? Once you have found the file, export it to your Kali machine's desktop.
- File -> Export Objects – > Search/Filter for dll ->  save and download the dll 
- june11.dll

![image](https://user-images.githubusercontent.com/79764720/131799995-2dafb347-51cf-4cd9-b008-a005a8c1208b.png)


1.	Upload the file to VirusTotal.com. What kind of malware is this classified as?
- Trojan.Mint.Zamg.O 

![image](https://user-images.githubusercontent.com/79764720/131800132-db599ebc-405b-48f3-b4dc-547c371a4e9e.png)



Vulnerable Windows Machines
The Security team received reports of an infected Windows host on the network. The following is known:
- Machines in the network live in the range 172.16.4.0/24.
- The domain mind-hammer.net is associated with the infected computer.
- The DC for this network lives at 172.16.4.4 and is named Mind-Hammer-DC.
- The network has standard gateway and broadcast addresses.


Inspect your traffic to answer the following questions:
1.	Find the following information about the infected Windows machine:
- Host name: Rotterdam-PC.mind-hammer.net 
- IP address: (172.16.4.205)
- MAC address:  00:59:07:b0:63:a4

![image](https://user-images.githubusercontent.com/79764720/131802560-9bb8d760-ada1-4e05-bc05-da3d611e885f.png)



![image](https://user-images.githubusercontent.com/79764720/131800379-126a99c1-5ecb-4e1f-b957-2b34fc877c1f.png)



1.	What is the username of the Windows user whose computer is infected?
- matthijs.devries


![image](https://user-images.githubusercontent.com/79764720/131802140-63ed8561-1ffc-42f0-93f8-a55c6e5af076.png)



1.	What are the IP addresses used in the actual infection traffic?
- 185.243.115.84

![image](https://user-images.githubusercontent.com/79764720/131800709-8f4091cb-a9f7-4182-952a-652fa61bc018.png)



1.	As a bonus, retrieve the desktop background of the Windows host
- It’s a bird exported object 
- 

![image](https://user-images.githubusercontent.com/79764720/131800874-0646b385-41e4-49f6-80da-546b5665497d.png)



Illegal Downloads
IT was informed that some users are torrenting on the network. The Security team does not forbid the use of torrents for legitimate purposes, such as downloading operating systems. However, they have a strict policy against copyright infringement.

IT shared the following about the torrent activity:

- The machines using torrents live in the range 10.0.0.0/24 and are clients of an AD domain.
- The DC of this domain lives at 10.0.0.2 and is named DogOfTheYear-DC.
- The DC is associated with the domain dogoftheyear.net.

Your task is to isolate torrent traffic and answer the following questions:

Find the following information about the machine with IP address 10.0.0.201:
- MAC address:  00:16:17:18:66:c8
- Windows username:  elmer.blanco
- OS version:  Windows NT

![image](https://user-images.githubusercontent.com/79764720/131802390-3039cc4d-0492-4b3a-acf4-5d79724ed9bb.png)


2.	Which torrent file did the user download?
- Betty_Boop_Rhythm_on_the_Reservation

