# Nginx Resources

Installation
------------

There are several ways to install nginx onto your machine. One of them just by using package repositories. Follow [www.nginx.com](https://www.nginx.com/resources/wiki/start/topics/tutorials/install/) to explore this approach.

Second approach imply using initial code of nginx. Type following commands:

```sh
$ sudo apt-get update
$ sudo apt-get install build-essential #include some compilation tools like 'make'
```

Then download initial code of nginx from site above, note you have access to stable and mainline version. Unzip file and go inside. And now with help of `configure` you are able to install nginx with configuration on your demand. All options for configs can be found [here](https://www.nginx.com/resources/wiki/start/topics/tutorials/installoptions/).

Example,

```sh
$ ./configure --sbin-path=/usr/bin/nginx --conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --with-debug --with-pcre --with-http_ssl_module
$ make
$ sudo make install
```

So, now you have your nginx installed.

Start nginx
-----------

To start nginx, run the executable file. Once nginx is started, it can be controlled by invoking the executable with the -s parameter. Use the following syntax:

```nginx -s signal```

Where signal may be one of the following:

```
stop — fast shutdown
quit — graceful shutdown
reload — reloading the configuration file
reopen — reopening the log files
```

But if you have your nginx installed with package manager, you can simply use syntax like:

```sh
/etc/init.d/nginx {start|stop|status|restart|reload|force-reload|upgrade|configtest|check-reload}
```

Issues
------

Note, sometimes nginx has problems with re-reading conf. To handle this head [here](http://nginx.org/en/docs/control.html)
