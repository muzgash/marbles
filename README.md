marbles
=======

**M**arvellous **A**DC and **R**aspberryPi **B**ioreactor **L**ight **E**lectronic **S**ystem

Note about configuration on server side:
Must enable proxy_http module on apache with the command

a2enmod proxy_http

and add the following lines to /etc/apache2/mods-enabled/proxy.conf

ProxyRequests On

ProxyVia On

ProxyPass /marbles-server http://localhost:31416/marbles

ProxyPassMatch /marbles-server http://localhost:31416/marbles

ProxyPassReverse /marbles-server http://localhost:31416/marbles

Restart apache with the command:

service apache2 restart

This is for your JavaScript code to see the route to the server including the port
Client must point to the server route, in this case, http://server-ip/marbles-server
and server must point to the client direction, i.e. uriPath(/marbles)


