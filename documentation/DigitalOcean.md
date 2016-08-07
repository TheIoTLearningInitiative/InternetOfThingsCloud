# Digital Ocean

> Simple Cloud Computing, Built for Developers [Homepage](https://www.digitalocean.com/)

- [How to setup a Mosquitto MQTT Server and receive data from OwnTracks](https://www.digitalocean.com/community/questions/how-to-setup-a-mosquitto-mqtt-server-and-receive-data-from-owntracks)

# Getting Started

```
xe1gyq@jessie:~$ ssh root@188.179.78.13
The authenticity of host '188.179.78.13 (188.179.78.13)' can't be established.
ECDSA key fingerprint is 53:..:b8.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '188.179.78.13' (ECDSA) to the list of known hosts.
root@188.179.78.13's password: 
You are required to change your password immediately (root enforced)

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Fri Jun 24 01:13:37 2016 from 162.101.37.71
Changing password for root.
(current) UNIX password: 
Enter new UNIX password: 
Retype new UNIX password: 
root@debiando:~# 
```

```sh
root@debiando:~# apt-get update
Get:1 http://security.debian.org jessie/updates InRelease [63.1 kB]
Get:2 http://security.debian.org jessie/updates/main Sources [148 kB]                    
Get:3 http://security.debian.org jessie/updates/main amd64 Packages [282 kB]                          
Get:4 http://security.debian.org jessie/updates/main Translation-en [142 kB]                          
Ign http://mirrors.digitalocean.com jessie InRelease                                  
Get:5 http://mirrors.digitalocean.com jessie-updates InRelease [142 kB]
Hit http://mirrors.digitalocean.com jessie Release.gpg    
Get:6 http://mirrors.digitalocean.com jessie-updates/main Sources [15.4 kB]
Get:7 http://mirrors.digitalocean.com jessie-updates/main amd64 Packages/DiffIndex [4,456 B]
Get:8 http://mirrors.digitalocean.com jessie-updates/main Translation-en/DiffIndex [2,704 B]
Hit http://mirrors.digitalocean.com jessie Release
Get:9 http://mirrors.digitalocean.com jessie-updates/main amd64 2016-06-12-1524.07.pdiff [545 B]
Get:10 http://mirrors.digitalocean.com jessie-updates/main amd64 2016-06-12-1524.07.pdiff [545 B]
Get:11 http://mirrors.digitalocean.com jessie-updates/main 2016-06-12-1524.07.pdiff [381 B]
Get:12 http://mirrors.digitalocean.com jessie-updates/main 2016-06-12-1524.07.pdiff [381 B]
Hit http://mirrors.digitalocean.com jessie/main Sources
Hit http://mirrors.digitalocean.com jessie/main amd64 Packages
Hit http://mirrors.digitalocean.com jessie/main Translation-en
Fetched 801 kB in 6s (124 kB/s)                                                                       
Reading package lists... Done
root@debiando:~# 
```

```
root@debiando:~# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/vda1        20G  1.1G   18G   6% /
udev             10M     0   10M   0% /dev
tmpfs            99M  4.4M   95M   5% /run
tmpfs           248M     0  248M   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           248M     0  248M   0% /sys/fs/cgroup
root@debiando:~# 
```

# TugBoat

> A command line tool for interacting with your DigitalOcean droplets [Homepage](https://github.com/pearkes/tugboat)

```sh
root@debiando:~# gpg2 --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
gpg: keyring `/root/.gnupg/secring.gpg' created
gpg: requesting key D39DC0E3 from hkp server keys.gnupg.net
gpg: /root/.gnupg/trustdb.gpg: trustdb created
gpg: key D39DC0E3: public key "Michal Papis (RVM signing) <mpapis@gmail.com>" imported
gpg: no ultimately trusted keys found
gpg: Total number processed: 1
gpg:               imported: 1  (RSA: 1)
root@debiando:~# 
```

```sh
root@debiando:~# rvm get stable --autolibs=enable
root@debiando:~# rvm install ruby
root@debiando:~# rvm --default use ruby-2.3.1
```

```sh
root@debiando:~# gem -v
2.5.1
root@debiando:~# 
```

```sh
root@debiando:~# gem update --system
Updating rubygems-update
Fetching: rubygems-update-2.6.6.gem (100%)
Successfully installed rubygems-update-2.6.6
Parsing documentation for rubygems-update-2.6.6
Installing ri documentation for rubygems-update-2.6.6
Installing darkfish documentation for rubygems-update-2.6.6
Done installing documentation for rubygems-update after 53 seconds
Parsing documentation for rubygems-update-2.6.6
Done installing documentation for rubygems-update after 0 seconds
Installing RubyGems 2.6.6
root@debiando:~# 
```

```sh
root@debiando:~# gem install tugboat
Fetching: thor-0.18.1.gem (100%)
Successfully installed thor-0.18.1
Fetching: multipart-post-2.0.0.gem (100%)
Successfully installed multipart-post-2.0.0
Fetching: faraday-0.9.2.gem (100%)
Successfully installed faraday-0.9.2
Fetching: faraday_middleware-0.10.0.gem (100%)
Successfully installed faraday_middleware-0.10.0
Fetching: hashie-3.4.4.gem (100%)
Successfully installed hashie-3.4.4
Fetching: barge-0.12.0.gem (100%)
Successfully installed barge-0.12.0
Fetching: middleware-0.1.0.gem (100%)
Successfully installed middleware-0.1.0
Fetching: tugboat-2.2.2.gem (100%)
***************************************
Successfully installed tugboat-2.2.2
Parsing documentation for thor-0.18.1
Installing ri documentation for thor-0.18.1
invalid options: -SHN
(invalid options are ignored)
Parsing documentation for multipart-post-2.0.0
Installing ri documentation for multipart-post-2.0.0
Parsing documentation for faraday-0.9.2
Installing ri documentation for faraday-0.9.2
Parsing documentation for faraday_middleware-0.10.0
Installing ri documentation for faraday_middleware-0.10.0
Parsing documentation for hashie-3.4.4
Installing ri documentation for hashie-3.4.4
Parsing documentation for barge-0.12.0
Installing ri documentation for barge-0.12.0
Parsing documentation for middleware-0.1.0
Installing ri documentation for middleware-0.1.0
Parsing documentation for tugboat-2.2.2
Installing ri documentation for tugboat-2.2.2
Done installing documentation for thor, multipart-post, faraday, faraday_middleware, hashie, barge, middleware, tugboat after 5 seconds
8 gems installed
root@debiando:~# 
```

[Authentication](https://cloud.digitalocean.com/settings/api/tokens)

```sh
root@debiando:~# tugboat authorize
Note: You can get your Access Token from https://cloud.digitalocean.com/settings/tokens/new

Enter your access token: dd155002f6e12f5c5806a0ca9636308f855727ed286fc6e74cf63ca12b4b238e
Enter your SSH key path (optional, defaults to ~/.ssh/id_rsa): 
Enter your SSH user (optional, defaults to root): root
Enter your SSH port number (optional, defaults to 22): 22

To retrieve region, image, size and key ID's, you can use the corresponding tugboat command, such as `tugboat images`.
Defaults can be changed at any time in your ~/.tugboat configuration file.

Enter your default region (optional, defaults to nyc1): 
Enter your default image ID or image slug (optional, defaults to ubuntu-14-04-x64): 
Enter your default size (optional, defaults to 512mb)): 
Enter your default ssh key IDs (optional, defaults to none, array of IDs of ssh keys eg. ['1234']): 
Enter your default for private networking (optional, defaults to false): 
Enter your default for enabling backups (optional, defaults to false): 
Enter your default for IPv6 (optional, defaults to false): 
Authentication with DigitalOcean was successful.
root@debiando:~# 
```