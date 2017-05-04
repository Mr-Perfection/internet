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
Application Protocols Layer  | Protocols specific to applications such as WWW (world wide web), e-mail, and [FTP](https://en.wikipedia.org/wiki/File_Transfer_Protocol) 
TCP Layer  | TCP directs packets to a specific application on a computer using a port number.
Internet Protocol Layer  | IP directs packets to a specific computer using an IP address.
Hardware Layer  | Converts binary packet data to network signals and back. (E.g. ethernet network card, modem for phone lines, etc.)


![alt text](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper_files/ruswp_diag2.gif)

1. The message would start at the top of the protocol stack on your computer and work it's way downward. If the message to be sent is long, each stack layer that the message passes through may break the message up into smaller chunks of data. This is because data sent over the Internet (and most computer networks) are sent in manageable chunks. On the Internet, these chunks of data are known as [packets](http://computer.howstuffworks.com/question525.htm) 1000-1500 bytes of data.

2. The packets would go through the Application Layer and continue to the TCP layer. Each packet is assigned a port number. [Ports](http://searchnetworking.techtarget.com/definition/well-known-port-numbers) will be explained later, but suffice to say that many programs may be using the TCP/IP stack and sending messages. We need to know which program on the destination computer needs to receive the message because it will be listening on a specific port.

3. After going through the TCP layer, the packets proceed to the IP layer. This is where each packet receives it's destination address, 5.6.7.8.

4. Now that our message packets have a port number and an IP address, they are ready to be sent over the Internet. The hardware layer takes care of turning our packets containing the alphabetic text of our message into electronic signals and transmitting them over the phone line.

5. On the other end of the phone line your ISP has a direct connection to the Internet. The ISPs router examines the destination address in each packet and determines where to send it. Often, the packet's next stop is another router. More on routers and Internet infrastructure later.

6. Eventually, the packets reach computer 5.6.7.8. Here, the packets start at the bottom of the destination computer's TCP/IP stack and work upwards.

7. As the packets go upwards through the stack, all routing data that the sending computer's stack added (such as IP address and port number) is stripped from the packets.

8. When the data reaches the top of the stack, the packets have been re-assembled into their original form, "Hello computer 5.6.7.8!"

### 3. Application Protocols: HTTP and the World Wide Web
#### HTTP Protocol
HTTP (Hypertext Transfer Protocol) is the protocol that web browsers and web servers use to communicate with each other over the Internet. It is an application level protocol because it sits on top of the TCP layer in the protocol stack and is used by specific applications to talk to one another. In this case the applications are web browsers and web servers.

HTTP is a *connectionless text based protocol*. Clients (web browsers) send requests to web servers for web elements such as web pages and images. **After the request is serviced by a server, the connection between client and server across the Internet is disconnected. A new connection must be made for each request.** Most protocols are connection oriented. This means that the two computers communicating with each other keep the connection open over the Internet. HTTP does not however. Before an HTTP request can be made by a client, a new connection must be made to the server.

When you first type a URL into a web browser, this happens:
1. The browser first connects to the domain name server (DNS) and retrieve a corresponding IP address for the web server.
2. The web browser connects to the web server and sends the HTTP request for the desired web page.
3. The web server receives the request and checks for the desired page. If the page exists, the web server sends it. If the server cannot find the requested page, it will send an HTTP 404 error.
4. The web browser receives the page back and the connection is closed.
5. The browser then parses through the page and looks for other page elements it needs to complete the web page. These usually include images, applets, etc.
6. For each element needed, the browser makes additional connections and HTTP requests to the server for each element.
7. When the browser has finished loading all images, applets, etc. the page will be completely loaded in the browser window.

#### SMTP and Electronic Mail Protocol
SMTP (Simple Mail Transfer Protocol) is also ***text based protocol* but unlike HTTP, it is connection oriented.**


### Port Numbers
Protocol  | Port #
------------- | -------------
FTP  | 20/21
Telnet  | 23
SMTP  | 25
HTTP  | 80
MORE on [here](http://www.pearsonitcertification.com/articles/article.aspx?p=1868080)
### Resources
https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm
