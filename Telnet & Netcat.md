# Telnet 

Telnet is an old network protocol that is used to connect to remote systems over a TCP/IP network. The telnet command is used to establish 
the connections between different machines.This command allows us to manage the remote devices using the CLI (command-line interface).  
It uses TCP port 23 which is assigned to the telnet protocol.

- Note : Telnet is not a secure protocol and is thus NOT RECOMMENDED!. This is because data sent over the protocol is unencrypted and can be intercepted by hackers.

## Installing of Telnet

    $ yum install telnet -y
    
## Connecting telnet from a server to an application

    $ telnet [configuration endpoint] (port number)
    
## To check the stats of the conneected server and application through telnet (such as max connections, accepting connections etc)

    stats


-------------------------------------------------------------------------------------------------------------------------------------------

# NETCAT

The Netcat (nc) command is a command-line utility for reading and writing data between two computer networks. The communication happens using either TCP or UDP.
It is one of the powerful networking tool, security tool or network monitoring tool. It acts like cat command over a network.

## It is generally used for the following reasons:

- open Remote connections
- Operation related to TCP, UDP or UNIX-domain sockets
- Port Scanning
- Port listening
- Port redirection
- Read/Write data across network
- Network debugging
- Network daemon testing
- Simple TCP proxies
- A Socks or HTTP Proxy Command for ssh

## Installing of netcat

    $ yum install nc -y
    
## Connecting netcat from a server to an application   

    $ nc [configuration endpoint] (port number)
   
- Note : (Establishes a connection between the server and application and displays the stats such as version, max connctions, uptime, etc)          
    
    
    
    
    
    
    
    
    
    
    
