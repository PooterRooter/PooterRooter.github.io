---
layout: post
title:  "TCP/UDP Send/Recv"
date:   2018-05-22 20:33:11

---
                                                                                                                                           
TCP Send/Recv Client

{% highlight ruby %}
import socket
             target_host = "www.google.com"
             target_port = 80
# create a socket object
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# connect the client
client.connect((target_host,target_port))
# send some data
client.send("GET / HTTP/1.1\r\nHost: google.com\r\n\r\n")
# receive some data 
response = client.recv(4096)
print response
{% endhighlight %}



UDP Send/Recv Client

{% highlight ruby %}
import socket
             target_host = "127.0.0.1"
             target_port = 80
# create a socket object
client = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
# send some data
client.sendto("AAABBBCCC",(target_host,target_port))
# receive some data
data, addr = client.recvfrom(4096)
print data
{% endhighlight %}

