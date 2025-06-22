---
layout: default
title: Cram
---

<style>
  .page-content > .wrapper {
    width: 50%;
    max-width: none;
    overflow:visible;
  }

  #gif-table td {
    border: 0px;
    padding: 0px;
  }

  #gif-table {
    max-width: 90%;
    display: block;
    margin: auto;
    margin-bottom: 12px;
    border: 0px;
  }

  .excerpt {
    background: #ffffff;
    background-color: #ffffff;
    font-style:italic;
  }
  .ext-source {
    font: 400 10px/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
    text-align: left;
    font-style: italic;
  }
</style>

| A+ | Routers, Switches, Hosts, Servers, LAN/WAN
| Network+ | OSI model, Subnetting, DNS, DHCP, SMTP, FTP
| Security+ | Attack, Vulnerabilities, Cyber Kill Chain
| Domain Controllers (AD) | Basic roles and services, Kerberos
| Firewalls | IDS/IPS, SIEM
| Crypto | Hashing vs Encoding vs Encrypting, ROT13, MD5, SHA-2, Base64
| Python | If statements, While, For, Functions, Classes
| Linux Bash | Common tool usage, piping
| Pcap Analysis | Identify devices and services, understanding traffic, extracting data 

# A+
## Parts of the Computer
A network is just a group of computers, but every computer must play a role. A computer can either be a host or a server, sometimes both. A server provides services to the network while a host connects to services available inside or outside the local network.

<div class="excerpt">
A modern computer consists of three major components:<br>
&nbsp;&nbsp;&nbsp;- Hardware<br>
&nbsp;&nbsp;&nbsp;- Operating system<br>
&nbsp;&nbsp;&nbsp;- Applications<br>
<p class="ext-source">CompTIA A+ All-In-One 11th Ed. Pg 32</p>
</div>

Focus on a few hardware parts:
&nbsp;&nbsp;&nbsp;CPU (Central Processing Unit)  
&nbsp;&nbsp;&nbsp;RAM (Random Access Memory)  
&nbsp;&nbsp;&nbsp;Firmware  
At least know what each does.

### **CPU**
Interprets and executes instructions. It acts as the brain of the computer, performing billions of calculations per second.

### **RAM**
The working memory of the computer. When the CPU processes calculations, the results and data are stored in *Random Access Memory*. A game that's running, a YT video playing, or even the OS are all stored in RAM as data that is currently being processed by the CPU.

### **Firmware**
Is actually software, but is embedded into hardware devices and controls the operation of hardware. This can range from a keyboard or mouse with its firmware defining which keys or buttons are pressed to a PC's firmware that defines how processes or operating systems should be booted up.

BIOS/UEFI are firmware standards that modern computers use.

### **The Operarting System**
The OS is the middleman in between the program and the hardware, it allows programs to interact and receive processing power from the hardware. Also note that the OS itself is also software and a process.

The most common operating systems are Windows, Linux, and Mac.

### **Applications**
An application is the web browser, the steam game, and the YT video. The difference between an application and a software is that software is more broader and defines other background processes like the OS, a firewall, or DNS resolution. An application is a program meant for human-to-computer interaction.

## Groups of computers
More known as a network. A network is a group of computers that talk to each other. But due to security reasons or for efficiency's sake, there are computers solely dedicated to help other computers talk to each other (a switch) and there are computers solely dedicated to helping other networks talk to other networks (a router).

### **Network Switch**
A Layer 2 device in the OSI model. It involves MAC addresses to forward data at the data link layer. Some switches can also operate in Layer 3 with Inter-VLAN routing. A switch works with MAC addresses which is assigned to each device's network interface(s).

### **Router**
Layer 3 device that allows network to network communication. A router works with IP addresses and subnets. It acts as the "gateway" in which all ingoing and outgoing traffic must go through the network's router. Modern routers also have expanded functionality such as blocking certain traffic, port forwarding/NAT, assigning automatic IP addresses (DHCP), and more.

### **LAN**
The simplest local area network consists of 1 router, 1 switch, and several PCs. A local area network is connected through Ethernet cabling or wi-fi. All devices with an internet connection must share the same subnet and possess an IP address belonging to that subnet. Devices in the same LAN are ideally in the same building or within the general vicinity of each other.

### **WAN**
A wide area network is typically a network of networks/network of LANs. It may span an entire region or continent where connected devices talk between great distances. Where individual PCs talk to each other inside a LAN, individual routers and their respective LANs are talking to each other inside a WAN.

The Internet/World Wide Web is considered to be just one giant globe-spanning WAN.

# Network+
## 7 layers of network communication
Networking is a process that's categorised into 7 steps or "layers". Modern computers that want to send a message must follow IT standards that every computer connected to the Internet must follow.

Understanding how a message must follow "Internet standards" can refer to the 7 layers of the OSI model (some prefer the 4 layers of the TCP/IP model)

| ![](/src/decap.gif){:#gif-table} | ![](/src/encap.gif){:#gif-table} |
{:#gif-table}
  
  
### **Wait. There's 2 OSI models?**
The OSI model with 7 layers was literally made in 1984. However the Internet was not a thing at the time. The more modern network model is the TCP/IP model that's only 4 layers. The TCP/IP model talks about how communication operate within the Internet and the OSI model with the 2 extra layers (Presentation and Session) is outdated and describes mainly LAN traffic.

<table>
  <tr style='text-align:center;'>
    <td style='background-color:rgb(117 202 211);'>TCP/IP (Internet)</td>
    <td style='background-color:rgb(137 211 117);'>OSI</td>
  </tr>
  <tr>
    <td rowspan=3>Application</td>
    <td>Application</td>
  </tr>
  <tr>
    <td>Presentation</td>
  </tr>
  <tr>
    <td>Session</td>
  </tr>
  <tr>
    <td>Transport</td>
    <td>Transport</td>
  </tr>
  <tr>
    <td>Internet</td>
    <td>Network</td>
  </tr>
  <tr>
    <td rowspan=2>Network Access</td>
    <td>Data Link</td>
  </tr>
  <tr>
    <td>Physical</td>
  </tr>
</table>

(It's still good to know all 7 layers though for an exam question. Presentation and Session are "merged" with the Application layer and still describes things like encrypting traffic.)

### **Subnetting**
Something you have to do to assign a valid (layer 3) IP address to a computer. It's a skill that's worth practicing. You can't learn subnetting in a single paragraph, please use external resources like this:

<iframe width="560" height="315" src="https://www.youtube.com/embed/wuIdYxaV46Y?si=fyWCsKZfdIKzJjBo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" style="margin:auto;display:block;" allowfullscreen></iframe><br>
⬇️⬇️ And use this website (super cool)  
[subnetting.net](https://www.subnetting.net/Subnetting.aspx)

## Some common networking protocols
### **DNS**
<div class="excerpt">
Domain Name System (port 53).
</div>
Invented to turn an IP address like 8.8.8.8 into [https://dns.google](https://dns.google). Don't believe me? Visit 8.8.8.8 on your browser. The purpose of DNS is to turn the gibberish-looking numbers of IP addresses into human-readable urls.  

This is achieved by having DNS servers inside a network to store IP-to-URL records and "serve" these DNS records to connected computers. Note that DNS has more purposes beyond website urls!

### **DHCP**
<div class="excerpt">
Dynamic Host Configuration Protocol (port 67/68).
</div>
A valid IP address doesn't just appear out of thin air everytime your device connects to the wifi. Back before people invented DHCP, an IT guy needed to manually configure a device's IP address and he/she (most likely he) needed to make sure that he didn't assign the IP address twice. Imagine having to keep track of an office with 200 computers of IP addresses.  

Therefore people delegated the management of IP addresses to a computer. This is DHCP. Almost every network on the face of the earth has a "DHCP server" that automatically assigns new IP addresses. Modern routers today have built-in DHCP functionality.  

### **SMTP**
<div class="excerpt">
Simple Mail Transfer Protocol (port 25/465/587).
</div>
In real life, what's the difference between a message and a mail? A message needs 2 people, one to say the message and the other to listen. In mail, one needs to write mail, a post office to store it, and a receiver that receives at a later date.

HTTP/web traffic is like a message, 2 computers must be turned on to receive messages. That is why SMTP is a different protocol for network communication because a mail/SMTP server stores the mail until the recipient computer is turned on and the user has logged in.

### **FTP**
<div class="excerpt">
File Transfer Protocol (port 20/21).
</div>
Today, the internet uses HTTPS to download files. When you download a file through a web browser, it will use HTTP/HTTPS. However, before the Internet became mainstream, people used FTP to download files from other people's networks.  

The reason why FTP didn't became the standard is that FTP is less secure and it needed a <ins>network user</ins> login before a download. In the Internet, websites want a way to serve downloads to everyone without people logging into their network.

# Security+
## Attacks
### **Malware**
<div class="excerpt">
Software that has been designed for some nefarious purpose.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 3</p>

### **Polymorphic Malware**
Malware that dynamically changes its digital signature to bypass anti-malware software.

### **Viruses**
<div class="excerpt">
A piece of malicious code that replicates by attaching itself to another piece of executable code.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 4</p>

### **Ransomware**
<div class="excerpt">
A form of malware that performs some action and extracts ransom from a user.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 5</p>
Common ransomware encrypts files and then demands a ransom in a digital currency like bitcoin to unencrypt the files.

### **Worm**
<div class="excerpt">
Pieces of code that attempt to penetrate networks. Once a penetration occurs, the worm will create a new copy of itself on the penetrated system.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 5</p>

### **Trojan**
A piece of software that seems non-malicious at first glance and performs a normal function but is actually hiding a malicious functionality.

### **Rootkit**
<div class="excerpt">
A form of malware that is specifically designed to modify the operation of the OS in some fashion to facilitate nonstandard functionality.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 6</p>
Modern anti-cheat software for online games like League of Legends are basically rootkits.

### **Keylogger**
<div class="excerpt">
Sofware that logs all of the keystrokes that a user enters.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 7</p>
Malicious keyloggers obtain passwords and other sensitive information.

### **Adware**
Software that creates pop-ups and ads. Not very malicious but it targets elders who are too inexperienced to uninstall adware.

### **Spyware**
<div class="excerpt">
Software that spies on users, recording, and reporting on their activities without user knowledge.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 9</p>

### **RAT**
A remote-access trojan is a type of backdoor. It penetrates a victim's system and gain admin-level privileges and is then awaiting further actions from a remote attacker.

### **Logic Bomb**
Malicious software like a virus or trojan but waits for a period of time until some event or date invokes its malicious payload.

An example is a logic bomb that periodically checks an organisation's payroll for a specific employee. If the employee is not found, the malicious payload executes.

### **Backdoor**
<div class="excerpt">
Programs that attackers install after gaining unauthorised access to a system to ensure that they can caontinue to have unrestricted access to the system.
</div>
<p class="ext-source">CompTIA Security+ All-In-One 5th Ed. Pg 10</p>

### **IOC**
*Indicators of Compromise*. IOCs are pieces of forensic data or results of cyberattacks. Cybersec companies catalogue cyberattacks into IOCs for antivirus and detection software to prevent future attacks.

[threatfox.abuse.ch](https://threatfox.abuse.ch/browse/) is an example of an IOC database.

### **Social Engineering**
An attack against a human user involving a social interaction. You can have the perfect security against malware but humans are still fallible.

Some well-known social engineering attacks are: phising, impersonation, and blackmail.

### **Application/Service Attacks**
Viruses and malware attack a computer system, however these attacks target an application. Typically these are publicly visible like a website or an online service. 

Well-known attacks are: DoS (Denial of Service), Man-In-The-Middle, SQL Injection, and Cross-Site Scripting.

### **Cryptographic Attacks**
This involves cracking passwords in order to gain access to online accounts or organisation credentials.

Some examples are: Rainbow Tables, Dictionary Attack, Brute Force, etc.  

Note: Google or use websites like [attack.mitre.org](https://attack.mitre.org) to read more about [DoS](https://attack.mitre.org/techniques/T0814/), [Brute Force](https://attack.mitre.org/techniques/T1110/), [SQL Injection](https://attack.mitre.org/techniques/T1190/), etc.

### **Threat Actors**
Describes the groups of attackers and their possible motives.
- Script Kiddies: Individuals with little technical expertise and runs random scripts made by experienced attackers in order to gain learning experience.
- Hacktivists: Individuals who are competent-ish and attack for an ideological/political cause.
- Organised Crime: Professional for-profit cybercriminals that mainly act on financial self-interests. May also have foreign, political, or corporate backers.
- NationStates/APT: Government/military funded attackers who have access to national resources to attack based on the nation's (geopolitical) interests.
- Insiders: Compromised workers/employees within an organisation that attack from the inside with valid credentials. Varies between sleeper cells, spies, and disgruntled employees.
- Competitors: Business/corporate attackers that attempt to disrupt business, steal company secrets, and target corporate leaders of business competitors.

## Cyber Kill Chain
Cyber Kill Chain is a 7 step guideline for performing cyber attacks by Lockheed Martin.  

1. Reconnaissance - identify targets, points of entry, security vulnerabilities.
2. Weaponisation - find or construct tools/payloads to attack.
3. Delivery - deliver the attack through methods like phishing.
4. Exploitation - the malicious program is bypassing security measures via vulnerabilities.
5. Installation - the malicious payload executes.
6. Command and Control - a backdoor and/or connection to a C2 server is established.
7. Actions on Objectives - the attacker now has enough access/capability to act on objectives.

# Domain Controllers (AD)
### **Network Domain**
A LAN(s) belonging to a specific organisation may start having computer accounts with usernames for its employees. It may start becoming more advanced by having its own web server hosting a website and incorporating bigger network architecture.

A domain controller is then installed to keep track of the organisation's networks. The network may also be assigned a name, something like google.com.

### **Active Directory**
Not every organisation or company has the resources to create their own software to manage their computer network. Windows' Active Directory is the industry standard for domain management.

In AD, the server that manages the network domain is called a domain controller.

There are alternatives for AD, some in Linux, but even if a network has majority of Mac or Linux machines, Active Directory is still ideal for sheer amount of features.

### **AD DS**
*Active Directory Domain Services*. The core module of AD. It handles account logins, password storage, and account privileges.

There are also other functions that can be toggled on such as the DNS service, Microsoft Exchange service, Windows Group Policy.

By having AD DS, this makes the network more sophisticated. It gives the network DNS, mail, usernames and passwords, etc.

### **AD CS**
*Active Directory Certificate Services*. This is another key AD feature, official term is "on-premise public key infastructure". Digital certificates are private keys which are used for data encryption. This gives a very important layer of security to the network by encrypting network traffic.

Websites that handle online payments or services such as banking websites will always have domain controllers that handle the generation and exchange of digital certificates in order to encrypt people's sensitive network traffic.

A digital certificate makes a domain's URL an "https" (instead of an http).

### **Kerberos**.
*UDP port 88*. A sophisticated authentication protocol, it involves multiple servers to allow users into a network domain's services. You can't know Kerberos in a single paragraph, please google!

# Firewalls
### **Firewall**
Can be hardware, software, or both whose purpose is to enforce network security policies by inspecting network traffic and blocking malicious packets/connections (based on the security policies).

### **ACLs**
*Access Control Lists*. Firewalls can have ACLs that defines allowed or banned users, IPs, or MAC addresses.

### **Application vs Network**
An application-based firewall looks at the application data of network traffic, for example, banning a connection based on the website data (ex. cornhub). However network-based firewalls only look at layer 3 and 4 packet headers.

### **IDS**
*Intrusion Detection System*. An application or device that detects and monitors network traffic. It uses more advanced detection methods like signature-based detection, anomaly-based detection, and stateful protocol analysis.

### **IPS**
*Intrustion Prevention System*. Acts upon network threats and blocks traffic. That's why it's combined with an IDS so it's called IDS/IPS.

### **SIEM**
*Security Information and Event Management*. Professional/company-level security software and hardware. SIEMs do the same functions as IDS/IPS on a larger scale but it also alerts on-site network admins for event/incident response on organisation-level cyber attacks.

# Encryption
### **Hashing vs Encoding vs Encryption**
Don't confuse these 3 terms. 

Hashing is generating a alphanumeric string based on the data. It's irreversible and one use is for checksum (to check for data tampering).

Encoding turns data into a different format but is reversible. Compressing files is an example.

Encryption makes data unreadable and hide its contents. It is reversible but requires a symmetric or public key to decrypt the data and get the original message. Passwords, bank credentials, and the enigma machine are examples.

### **ROT13**
*Rotate 13* encoding. Refers to the Caesar Cipher where it shifts the alphabets by a number of letters to encode messages during Caesar's rule of Rome.

ROT13 means that the alphabet is shifted by 13 letters, where A is N, B is O, C is P, etc.
Example: `Naan unf nvobucubovn` which translates to "Anna has aibohphobia".

Common indicators of ROT13 are repeating letters, the fixed length, and spaces.

### **MD5**
*Message Digest 5*. A hashing algorithm for checksums. It is obsolete and is proven to be insecure by modern security standards but is still used in some situations for its speed and simplicity.

It produces a 128-bit alphanumeric hash (every MD5 hash will always be 32 characters long).  
For example `7d0a54ae855d8e0728b03904d88e62e1` translates to: 
<div class="excerpt">
She a baddie, she showin' her panty (she showin' her panty)<br>
She shake it like jelly (she shake it like jelly, damn, damn)<br>
Hunnit bands in Chanely (hunnit bands in Chanely)<br>
But I'm still shakin' ass in the deli (grrah, grrah)<br>
</div>
<p class="ext-source">"Deli" by Ice Spice ‧ 2024</p>

Biggest indicator of MD5 is the 32 character length.

### **SHA-2**
*Secure Hashing Algorithm 2*. Another hashing algorithm that is much stronger than MD5. There are 6 variations but the most used are SHA-256 and SHA-512.  

SHA-256 will always produce a 64 character long hash, SHA-512 will always produce 128 characters.
A SHA-256 example: `8f434346648f6b96df89dda901c5176b10a6d83961dd3c1ac88b59b2dc327aa4`  which translates to "hi".
 
### **Base64**
Binary-to-text encoding. It encodes and decodes binary into human-readable text. This is used in virtually everywhere that binary is used (note: binary is a computer's first language, english is 2nd).

Example: `5o6I5Lq65Lul6a2a77yM5LiN5aaC5o6I5Lq65Lul5ryB` translates to "授人以魚，不如授人以漁".

Base64 character length will always be a multple of 4.

2nd example: `YQ==` translate to "a". 

Base64 will add one or two `=` in order to force the length to be a multiple of 4.

# Python
### **Brief Python refresher**
If you don't know python please learn it <ins>thoroughly</ins>. Don't try rushing to learn python for the sake of checking a box. Programming should be fun and satisfying to learn to have longevity in the field.

### **If statements**
In:
```
if 2 + 2 == 5:
  print('false')
elif 2 + 2 == 4:
  print(True)
else:
  print("also True")
```
Out:  
```
True
```
### **While**
In:
```
a = 0
b = 5
while a <= 5:
  print(a)
  a += 1
```
Out:
```
0
1
2
3
4
5
```
### **For**
In:
```
numbers = [1, 2, 3, 4, 5, 6]
for number in numbers:
  print(number - 1)
```
Out:
```
0
1
2
3
4
5
```
### **Functions**
In:
```
def myfunc(number):
  return 20 * 4 / 2

print(myfunc(10))
```
Out:
```
40.0
```
### **Classes**
In:
```
class Car:
  def __init__(self, name):
    self.name = name
  def vroom(self):
    print('vroom vroom!')
  def kachow(self):
    print(f'{self.name} says: kachow!')

car1 = Car('McQueen')
car1.vroom()
car1.kachow()
```
Out:
```
vroom vroom!
McQueen says: kachow!
```
# Linux Bash
### **Bash**
*Bourne Again Shell*. This is the standard shell for linux commands. It's a scripting language too but all you gotta know is that this is the "command terminal" for most linux machines.

### **Linux commands**
I can't teach all the basic linux commands (there's at least 50 basic ones) in one paragraph. But at least know a few tricks:

`2> /dev/null` Send error output to null
`$SHELL` begin $ to get environment variables. $SHELL gets file location of the shell.
`man <command name>` Invoke the manual pages for a given command name.

At least know a few commands:
`man`, `cat`, `grep`, `find`, `ip`, `ifconfig`, `ls`, `awk`.

Please DON'T learn linux commands from a textbook or from chatgpt, please run the commands yourself and practice!

### **Piping**
Combine commands.

`command1 | command2`

# Pcap Analysis
## **Identifying devices and services**
### **DNS, Hostnames, Domain Names**
Port 53.
