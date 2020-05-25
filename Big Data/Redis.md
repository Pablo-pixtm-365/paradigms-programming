<h1>Using Redis</h1>

![Redis](https://wikihosting.es/wp-content/uploads/2019/11/Redis-980x551.png)

<h2>How can we install it in ubuntu? <h3>

Install Redis-server
````Bash
$ sudo apt install redis-server
````
Open this file to make changes

````Bash
$ sudo nano /etc/redis/redis.conf
````
now we must found the part where we see supervised inside of the file, this part, allow us declare a syste, init to manage Redis
like a server, which give us a control over its functions. by default the value the supervised value is 'no', then as we are in ubuntu,
we will change this for systemd.

````Bash
supervised systemd
//lets go to restard the service
$ sudo systemctl restart redis.service

//then we will see if it works
Comprobar el servicio
$ sudo systemctl status redis
````
This would be the output:
**Note:** we can see that it says running

````Bash
redis-server.service - Advanced key-value store
     Loaded: loaded (/lib/systemd/system/redis-server.service; enabled; vendor >
     Active: active (running) since Sun 2020-05-24 11:46:46 CDT; 8h ago
       Docs: http://redis.io/documentation,
             man:redis-server(1)
    Process: 967 ExecStart=/usr/bin/redis-server /etc/redis/redis.conf (code=ex>
   Main PID: 1028 (redis-server)
      Tasks: 4 (limit: 9230)
     Memory: 4.4M
     CGroup: /system.slice/redis-server.service
             └─1028 /usr/bin/redis-server 127.0.0.1:6379

may 24 11:46:42 adrian-HP-Laptop-15-da0xxx systemd[1]: Starting Advanced key-va>
may 24 11:46:45 adrian-HP-Laptop-15-da0xxx systemd[1]: redis-server.service: Ca>
may 24 11:46:46 adrian-HP-Laptop-15-da0xxx systemd[1]: Started Advanced key-val>
````