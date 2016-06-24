# Digital Ocean

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