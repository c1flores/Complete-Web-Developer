<!-- omit in toc -->
# How the Internet Works

<!-- omit in toc -->
## Table of Contents
- [Browsing the Web](#browsing-the-web)
- [Breaking Google](#breaking-google)
- [The Internet Backbone](#the-internet-backbone)
- [Traceroute](#traceroute)
- [Developer Fundamentals](#developer-fundamentals)
- [What does a Developer Do?](#what-does-a-developer-do)

<br />

## Browsing the Web
1. Browser Requests the URL

    When the URL is entered and the user hits enter, the browser needs to find out the IP address (Internet Protocol address) associated with the URL. This is because while URLs are designed for human readability, computers and networks use numerical IP addresses to communicate.

<br />

1. Query Sent to ISP

    The browser sends a request to the user's Internet Service Provider (ISP) to find the IP address associated with the URL. The ISP has access to a network of DNS (Domain Name System) servers.

<br />

3. ISP Contacts DNS Server

    The ISP forwards the request to a DNS server. If the DNS server doesn't have the IP address cached from previous queries, it will perform a DNS lookup to find the IP address. This process may involve querying multiple DNS servers on the internet.

<br />

4. DNS Server Responds

   Once the DNS server finds the IP address associated with the URL, it sends this information back to the browser through the ISP.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/72abc555-5428-4bf4-b8ba-1addcf354491)

<br />

5. Browser Sends Request to Web Server

   With the IP address now known, the browser sends a request to the web server at that IP address. This request is usually made using the HTTP (Hypertext Transfer Protocol) or HTTPS (HTTP Secure) protocol.

<br />

6. Web Server Processes Request

   The web server, upon receiving the request, processes it and sends back the requested web page or file. This could include HTML files, CSS for styling, and JavaScript for interactivity, along with any media content.

<br />

7. Data Travels Back to the Browser

   The data from the web server is sent back across the internet to the user's ISP and then to the user's device.

<br />

8. Browser Renders the Web Page

   Once the browser receives the data, it renders the web page for the user to view. This involves interpreting the HTML, CSS, and JavaScript to display the content as intended by the web page designers.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/31e0c487-c839-49ec-8f83-2207ca74e33a)

## Breaking Google
When a user types a URL into their browser and initiates a request for a web page, the browser goes through the steps of querying the DNS to find the corresponding IP address, contacting the web server, and then retrieving the HTML, CSS, and JavaScript necessary to display that page. This is where the initial connection between the user's actions and the internet's infrastructure is established.

<br />

Once the browser has downloaded the assets and rendered the web page, this is typically where a user's direct interaction with the process would end. However, for a web developer, the rendering of the web page is often just the beginning of a deeper interaction.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/74952959-d1a6-4243-8a27-6a512f671bdd)

<br />

## The Internet Backbone 
1. Home Local Area Network (LAN): This is where the internet usage begins. Devices within a home, such as computers, smartphones, and tablets, connect to a wireless modem or router. This creates a local area network, allowing devices to communicate with each other and with the router wirelessly.

   Wireless Modem on Home: The wireless modem or router connects to the Internet Service Provider's (ISP) network. In a wireless internet link setup, this usually involves a wireless transmission to a nearby tower or antenna.

   <br />

2. Line of Sight Transmission: Wireless internet often relies on line-of-sight transmission, meaning there must be a clear path with no obstructions between the antenna on your home and the ISP's transmitter. This is because certain types of wireless signals (like those used in fixed wireless networks) can be disrupted by physical obstructions such as buildings or trees.

   Wireless Transmitter: The signal from the home's antenna reaches a wireless transmitter tower. This tower is part of the ISP's network infrastructure and is responsible for receiving and sending data to and from the user's home network.

   <br />

3. Line of Sight Backhaul: From the wireless transmitter tower, the data is sent to another part of the ISP's network infrastructure. This could be a higher-capacity tower or a direct link to the ISP's data center. "Backhaul" refers to the part of the network that connects the edge of the network (in this case, the user's home) to the core.

   ISP Network: The data travels through the ISP's network, which is a series of interconnected routers and servers that manage the data traffic.

   <br />

4. Internet Backbone: The ISP network is connected to the internet backbone, which is a large collection of interconnected high-speed data routes that interconnect different networks worldwide. The backbone is maintained by multiple organizations and is the core of the internet, handling long-distance data transport.

   Accessing Web Content: When a user in the home network requests a web page or any other online service, the request goes through the local network to the home's wireless modem, then wirelessly to the ISP's tower. From there, it travels through the ISP's network to the internet backbone, which routes the data to the server where the requested content is hosted.

   <br />

5. Returning Data: The server hosting the content sends the requested data back through the internet backbone, to the ISP's network, and then wirelessly through the line of sight backhaul and transmitter to the user's home modem. Finally, the modem delivers the data to the appropriate device on the home network.

   Continuous Communication: As long as the connection remains open, data can continue to flow back and forth between the user's devices and the servers on the internet, allowing for web browsing, video streaming, online gaming, and other internet activities.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/0b8b568d-5948-44cd-945d-1cc50c766a5b)

## Traceroute
The image below shows a simplified version of the packet's journey across the internet. It does not necessarily show the exact path (since routes can dynamically change), but it provides a representative look at the path through the various networks and devices that the packets traverse to reach the destination.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/0c6bb6a0-f791-47c7-ac83-36b98bdb5d2d)


## Developer Fundamentals
The diagram you've shared seems to highlight the interaction between a user's browser and web servers, emphasizing the role of the IP address and listing three factors that can affect the performance of a web application: the location of the server, the number of trips (requests and responses), and the size of the files (HTML, CSS, JavaScript). A web developer can influence the efficiency and speed of a web application by managing these factors as follows:

<br />

1. Location of Server: A web developer can choose to host the web application on a server that is geographically closer to the majority of the user base, or use a Content Delivery Network (CDN) to distribute the content across multiple locations globally. This reduces latency, which is the time it takes for a packet of data to travel from the server to the user's browser.

<br />

2. Number of Trips: The developer can minimize the number of trips between the client and the server by implementing techniques such as bundling, where multiple CSS or JavaScript files are combined into one; and caching, where data is stored in the user's browser temporarily to prevent repeated requests for the same resources. This reduces the overall number of HTTP requests needed to load a page, thereby decreasing load times.

<br />

3. Size of Files: By optimizing the size of the files (minifying HTML, CSS, and JavaScript; compressing images; using modern image formats; etc.), a developer can significantly decrease the amount of data that needs to be transferred over the network. This results in faster page load times and reduced bandwidth consumption.

<br />

By managing these three factors, a web developer can create a more performant web application that offers a better user experience by reducing load times and improving the responsiveness of the application.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/311734bb-8e34-4455-8e51-162e221f20e6)

<br />

## What does a Developer Do?
A Full Stack Developer is proficient in both front-end and back-end technologies, leveraging HTML, CSS, and JavaScript to construct and style interactive user interfaces, while utilizing server-side technologies like Node.js and Express.js to create robust server logic that handles HTTP requests, processes data, and interacts with a PostgreSQL database for data persistence. By combining these skills, the developer is able to build performant, secure, and scalable web applications that offer seamless user experiences from the point of entry in the browser to the data management on the server.

<br />

![](https://github.com/c1flores/Complete-Web-Developer/assets/81927296/a728bb30-c5c1-481d-bcfb-308932d97a9e)      

<br />