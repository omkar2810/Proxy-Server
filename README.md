# Proxy-Server
HTTP proxy server written in Python Language using socket programming

Proxy server capable of handling HTTP GET/POST requests

## Client
- client.py contains the code for the client
- run the command python client.py <remote ip port> <username> <password>
  
## Server
- server.py contains the code for the server.
- run the command python server.py <port name> to start the server

## Proxy Server
- proxy.py contains the code for the proxy server.
- run the command python proxy.py to start the proxy server
- The proxy server when recieves a request does some necessary checks and sends the request to the destination ip.

## Black Listing
- proxy/blacklist.txt contains a list of blcklisted destinations in CIDR format
- If the proxy server recieves a request for one of these IPs, then the credentials of the client are checked before forwarding the request to the destination.

## Basic Access Authentication
 - The credentials entered by the client are sent to the proxy server in the HTTP request itself in an encoded manner.
 - The proxy server decodes these credentials and checks if its is one the admin credentials stored in credentials.txt 
 
## Caching
- When a request is made for more than 3 times in 5 minutes then, a dictionary entry is made for the response for that request.
- The last modification timestamp is also stored in the cache dictionary
- While retreiving a response from the dictionary this timestamp is used to check if the entry needs to be updated
