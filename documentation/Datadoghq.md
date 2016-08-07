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

```

[Authentication](https://cloud.digitalocean.com/settings/api/tokens)

