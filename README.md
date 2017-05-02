# internet
How Internet works

### Introduction
I have decided to learn about how Internet works since I've been developing applications in web and mobile. I would like to put this as an anology: you drive a car without knowing how the car operates. As a user or person who utilizes benefits of the car, you don't need to do really know about the car. But if you want to fix your car or engineer it, you better know how it works and figure things out. 

That is why I decided to learn **How Internet works** in details.

### 1. Internet Addresses
Because the Internet is a global network of computers each computer connected to the Internet must have a unique address. Internet addresses are in the form nnn.nnn.nnn.nnn where nnn must be a number from 0 - 255. This address is known as an IP address. (IP stands for Internet Protocol; more on this later.)
![alt text](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper_files/ruswp_diag1.gif)

If you connect to the internet through an Internet Service Provider or ISP, you are usually assigned a temporary IP address for the duration of your dial-in session.
If you connect to the Internet from a local area network (LAN) your computer might have a permanent IP address or it might obtain a temporary one from a DHCP (Dynamic Host Configuration Protocol) server. In any case, if you are connected to the Internet, your computer has a unique IP address.

### 2. Protocol Stacks and Packets


Protocal Layer  | Comments
------------- | -------------
Application Protocols Layer  | Protocols specific to applications such as WWW, e-mail, FTP, etc.
TCP Layer  | TCP directs packets to a specific application on a computer using a port number.
Internet Protocol Layer  | IP directs packets to a specific computer using an IP address.
Hardware Layer  | Converts binary packet data to network signals and back. (E.g. ethernet network card, modem for phone lines, etc.)
### Resources
https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm
