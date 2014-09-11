 #ifndef __SOCK_H__  
 #define __SOCK_H__  
   
 #include <iostream>  
 #include <sys/socket.h>  
 #include <sys/epoll.h>  
 #include <stdio.h>  
 #include <netinet/in.h>  
   
class Sock  
{  
public:  
    Sock();  
     bool Connect(const char *host_id, constint &port);  
     void send_socket(const char *s);  
     int recv_socket();  
     constchar * get_recvbuf();  
     ~Sock();  
      private:  
     char recvbuf[BUFSIZ];  
     int sock;  
     int num;  
     struct sockaddr_in server;  
     struct hostent *hp;  
  };  
 
