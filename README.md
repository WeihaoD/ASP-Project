# ASP-Project
 advanced system programming-socket  
 
 This project is to be done either by one student or by pairs (two students) 

 Write two programs (in C or in Java), a client and a server, to implement a simple remote shell connection. The server process and the client process will run on two different machines and the communication between the two processes is achieved using Sockets. The server task can be summarized as follows :

- The server must start running before any client, and wait for connections.

- When the server gets a client, it forks and let the child process take care of the client in a separate function, called serviceClient, while the parent process goes back to wait for the next client.

- Then, the server’s child process  
 1. uses " dup2()" to make the screen descriptor designate the client socket
 2. gets in an infinite loop then :
 - reads a shell command from the client’s socket,  
 - if the client sends "quit", then the server’s child, closes socket and quits.
 - otherwise, it excutes command, using the " system()" library function,

 The client process connects to the server, then

- gets into an infinite loops  
 1. reads a command from keyboard,
 2. write the command to the server,
 3. if command is "quit", closes socket and quits
 4. otherwise, reads command output from socket and displays them on the screen
 
# Demo
- Found out the ip address of server
    - use "ip a" command to see the ipv4 address
- Start the server first  
![image](https://user-images.githubusercontent.com/79630970/129448084-185ddb7a-4101-4bf9-9e1b-18f8f4c2717f.png)
![image](https://user-images.githubusercontent.com/79630970/129448106-1b982d23-3f3d-48bf-9301-4f7f8df7b7ee.png)
ps: format is: ./server.exe 5000  
    5000 is the port



- Then start the client  
![image](https://user-images.githubusercontent.com/79630970/129448178-6c7d43d1-3432-4a53-89eb-18f35a9e1c32.png)
![image](https://user-images.githubusercontent.com/79630970/129448137-c1cc9df1-5d69-45e0-b806-42cb7ca098e9.png)
ps: format is: ./client.exe [ip address] [port]

**STEPs**
- Input a shell command in the client.  
- The command will be sent to the server.  
- Server will read the shell command from the client.  
- Server will excute the command, and show the result in the client.  
![image](https://user-images.githubusercontent.com/79630970/129448396-ba0bae79-c00a-4ab4-872a-70f99150afbc.png)


**CLOSE THE PROJECT**
- Close the client first, otherwise it will become the zombie  
    - input "quit" 
    - ![image](https://user-images.githubusercontent.com/79630970/129448410-5a67532b-cac0-4270-aa5f-05b9733fa643.png)
 

- Then close the server  
    - Input "quit"
    - ctrl c
    - ![image](https://user-images.githubusercontent.com/79630970/129448426-10d5c92f-175d-4bda-b262-a09f5bbb2c32.png)

