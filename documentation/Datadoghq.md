# DataDogHq

- [Install OpenStack in two commands for dev and test](https://www.datadoghq.com/blog/install-openstack-in-two-commands/)

@ Digital Ocean Ubuntu 8.1

```
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

```sh
root@debiando:~# wget https://raw.githubusercontent.com/DataDog/the-monitor/master/openstack/devstack/deploy_droplet.py
--2016-08-06 23:30:00--  https://raw.githubusercontent.com/DataDog/the-monitor/master/openstack/devstack/deploy_droplet.py
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.40.133
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|151.101.40.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1410 (1.4K) [text/plain]
Saving to: ‘deploy_droplet.py’

deploy_droplet.py         100%[======================================>]   1.38K  --.-KB/s   in 0s     

2016-08-06 23:30:01 (12.6 MB/s) - ‘deploy_droplet.py’ saved [1410/1410]

root@debiando:~# 
```

```sh
root@debiando:~# ./deploy_droplet.py openstackiando
Queueing creation of droplet 'openstackiando'...Failed to create Droplet: You specified an invalid image for Droplet creation.
Droplet fuzzy name provided. Finding droplet ID...done, 21792922 (openstackiando)
Waiting for droplet to become active........done (14s)
IP: 138.68.52.41
Run the following (in order): 
ssh root@138.68.52.41 'bash -s' < stack_setup.sh
ssh root@138.68.52.41
sudo -iu stack /usr/local/src/devstack/stack.sh
root@debiando:~# 
```

```sh
root@debiando:~# ssh root@138.68.52.41 'bash -s' < stack_setup.sh
...
Setting up git (1:1.9.1-1ubuntu0.3) ...
Cloning into 'devstack'...
Creating a group called stack
Creating a user called stack
Giving stack user passwordless sudo privileges
root@debiando:~# 
```

```sh
root@debiando:~# ssh root@138.68.60.67
root@138.68.60.67's password: 
Welcome to Ubuntu 16.04.1 LTS (GNU/Linux 4.4.0-31-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

5 packages can be updated.
0 updates are security updates.


Last login: Sun Aug  7 04:14:42 2016 from 187.201.32.249
root@openstackiando:~# 
```

```sh
root@openstackiando:~# sudo -iu stack bash /usr/local/src/devstack/stack.sh
```

Error!

```sh
root@openstackiando:~# cd /usr/local/src/devstack
```

```sh
root@openstackiando:~/usr/local/src/devstack# ./stack
root@openstackiando:~/usr/local/src/devstack# 
```

```sh
```

```sh
```