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

![alt text](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper_files/ruswp_diag2.gif)

1. The message would start at the top of the protocol stack on your computer and work it's way downward. If the message to be sent is long, each stack layer that the message passes through may break the message up into smaller chunks of data. This is because data sent over the Internet (and most computer networks) are sent in manageable chunks. On the Internet, these chunks of data are known as [packets](http://computer.howstuffworks.com/question525.htm) 1000-1500 bytes of data.

2. The packets would go through the Application Layer and continue to the TCP layer. Each packet is assigned a port number. Ports will be explained later, but suffice to say that many programs may be using the TCP/IP stack and sending messages. We need to know which program on the destination computer needs to receive the message because it will be listening on a specific port.

3. After going through the TCP layer, the packets proceed to the IP layer. This is where each packet receives it's destination address, 5.6.7.8.

4. Now that our message packets have a port number and an IP address, they are ready to be sent over the Internet. The hardware layer takes care of turning our packets containing the alphabetic text of our message into electronic signals and transmitting them over the phone line.

5. On the other end of the phone line your ISP has a direct connection to the Internet. The ISPs router examines the destination address in each packet and determines where to send it. Often, the packet's next stop is another router. More on routers and Internet infrastructure later.

6. Eventually, the packets reach computer 5.6.7.8. Here, the packets start at the bottom of the destination computer's TCP/IP stack and work upwards.

7. As the packets go upwards through the stack, all routing data that the sending computer's stack added (such as IP address and port number) is stripped from the packets.

8. When the data reaches the top of the stack, the packets have been re-assembled into their original form, "Hello computer 5.6.7.8!"

### Resources
https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm
