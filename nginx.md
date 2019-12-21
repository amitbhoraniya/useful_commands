# Nginx Commands

## Install Nginx Server

```shell
$ sudo yum install epel-release && yum install nginx   [On CentOS/RHEL]
$ sudo dnf install nginx                               [On Debian/Ubuntu]
$ sudo apt install nginx                               [On Fedora]
$ brew install nginx                                   [On Mac]
```

## Check Nginx Version

```console
bash-3.2:~$ nginx -v
nginx version: nginx/1.17.6
```

To view version and configure options then use the -V flag as shown.

```console
bash-3.2:~$ nginx -V
nginx version: nginx/1.17.6
built by clang 11.0.0 (clang-1100.0.33.12)
built with OpenSSL 1.1.1d  10 Sep 2019
TLS SNI support enabled
configure arguments: --prefix ......
```


## Check Nginx Configuration Syntax

```console
bash-3.2:~$ nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
```

## Start Nginx Service

```shell
$ sudo systemctl start nginx                     [systemd]
$ sudo service nginx start                       [sysvinit]
```

## Enable Nginx Service

```shell
$ sudo systemctl enable nginx                     [systemd]
$ sudo service nginx enable                       [sysvinit]
```

## Restart Nginx Service

```shell
$ sudo systemctl restart nginx                     [systemd]
$ sudo service nginx restart                       [sysvinit]
```

## View Service Status

```shell
$ sudo systemctl status nginx                     [systemd]
$ sudo service nginx status                       [sysvinit]
```

## Reload Nginx Service

```shell
$ sudo systemctl reload nginx                     [systemd]
$ sudo service nginx reload                       [sysvinit]
```

## Stop Nginx Service

```shell
$ sudo systemctl stop nginx                     [systemd]
$ sudo service nginx stop                       [sysvinit]
```

## Controlling NGINX

```shell
nginx -s <SIGNAL>
```

Where <SIGNAL> can be one of the following:

+ quit – Shut down gracefully
+ reload – Reload the configuration file
+ reopen – Reopen log files
+ stop – Shut down immediately (fast shutdown)

##  Uninstall Nginx on CentOS 7 / RHEL 7 / Oracle Linux 7

1. Stop Nginx service and remove Nginx auto start script
    ```shell
    sudo systemctl stop nginx.service
    sudo systemctl disable nginx.service
    ```
2. Remove Nginx user and it related directory
    ```shell
    sudo userdel -r nginx
    ```
3. Delete and related Nginx installation directory
    ```shell
    sudo rm -rf /etc/nginx
    sudo rm -rf /var/log/nginx
    sudo rm -rf /var/cache/nginx/
    ```
4. Remove the created nginx.service script under systemd
    ```shell
    sudo rm -rf /usr/lib/systemd/system/nginx.service
    ```
5. Uninstall Nginx
    ```shell
    yum remove nginx
    ```

## Troubleshoot

#### Nginx (13: Permission denied) while connecting to upstream

It may be cause of SELinux, below solution may workout for you.

```shell
setsebool httpd_can_network_connect on
```

To make the change persist use the -P flag.
```shell
setsebool httpd_can_network_connect on -P
```

You can see a list of all available SELinux booleans for httpd using
```shell
getsebool -a | grep httpd
```
