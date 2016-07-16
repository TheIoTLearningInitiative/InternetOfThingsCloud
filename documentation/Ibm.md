# IBM

## Cloud Foundry Hands-On

### Hello Cloud Application Javascript

> __cf__ - A command line tool to interact with Cloud Foundry

1. Get an IBM Bluemix Account
2. Follow instructions from [Cloud Foundry Command Line Interface Project](https://github.com/cloudfoundry/cli) to have cf application installed
3. Download [Hello Cloud Application](http://www.cloudworkshop.org/cloudfoundry/hellocloud_20150408.zip)
4. Push Hello Cloud Application to IBM Bluemix

```sh
    user@host:~$ cd
    user@host:~$ cf login -a https://api.ng.bluemix.net
    API endpoint: https://api.ng.bluemix.net
    
    Email> theiotlearninginitiative@gmail.com
    
    Password> 
    Authenticating...
    OK
    Targeted org theiotlearninginitiative@gmail.com
    Targeted space dev
    
    API endpoint:   https://api.ng.bluemix.net (API version: 2.40.0)   
    User:           theiotlearninginitiative@gmail.com   
    Org:            theiotlearninginitiative@gmail.com   
    Space:          dev   
    user@host:~$ 
    user@host:~$ cf apps
    Getting apps in org theiotlearninginitiative@gmail.com / space dev as theiotlearninginitiative@gmail.com...
    OK
    
    No apps found
    user@host:~$ 
    user@host:~$ cf orgs
    Getting orgs as theiotlearninginitiative@gmail.com...
    
    name
    theiotlearninginitiative@gmail.com
    user@host:~$ cf spaces
    Getting spaces in org theiotlearninginitiative@gmail.com as theiotlearninginitiative@gmail.com...
    
    name
    dev
    user@host:~$ mkdir hellocloud
    user@host:~$ cd hellocloud
    user@host:~$ wget http://www.cloudworkshop.org/cloudfoundry/hellocloud_20150408.zip
    user@host:~$ unzip hellocloud_20150408.zip
    user@host:~$ nano manifest.yml
    
    #--------------------------------------
    # change the `host` property to a
    # unique hostname on the domain you
    # are deploying to.
    #--------------------------------------
    
    applications:
    - name:    cf-node-hellocloud
      host:    cf-node-hellocloud-tili
      memory:  128M
      build: nodejs_buildpack-cached-v1.2.0.zip
    
    
    user@host:~$ cf push
    Using manifest file /home/user/hellocloud/manifest.yml
    
    Updating app cf-node-hellocloud in org theiotlearninginitiative@gmail.com / space dev as theiotlearninginitiative@gmail.com...
    OK
    
    Creating route cf-node-hellocloud-tili.mybluemix.net...
    OK    
    
    Binding cf-node-hellocloud-tili.mybluemix.net to cf-node-hellocloud...
    OK
    
    Uploading cf-node-hellocloud...
    Uploading app files from: /home/abraham/hellocloud
    Uploading 10.5K, 11 files
    Done uploading               
    OK
    
    Starting app cf-node-hellocloud in org theiotlearninginitiative@gmail.com / space dev as theiotlearninginitiative@gmail.com...
    -----> Downloaded app package (12K)
    
    -----> IBM SDK for Node.js Buildpack v2.8-20151209-1403
           Based on Cloud Foundry Node.js Buildpack v1.5.0
    -----> Creating runtime environment
           NPM_CONFIG_LOGLEVEL=error
           NPM_CONFIG_PRODUCTION=true
           NODE_MODULES_CACHE=true
    -----> Installing binaries
           engines.node (package.json):  unspecified
           engines.npm (package.json):   unspecified (use default)
           Resolving node version (latest stable) via 'node-version-resolver'
           Installing IBM SDK for Node.js (0.12.9) from cache
           Using default npm version: 2.14.9
    -----> Restoring cache
           Loading 1 from cacheDirectories (default):
           - node_modules (not cached - skipping)
    -----> Building dependencies
           Pruning any extraneous modules
           Installing node modules (package.json)
           cfenv@1.0.3 node_modules/cfenv
           ├── ports@1.1.0
           ├── underscore@1.8.3
           └── js-yaml@3.4.6 (inherit@2.2.2, esprima@2.7.1, argparse@1.0.3)
    -----> Installing App Management
    -----> Caching build
           Clearing previous node cache
           Saving 1 cacheDirectories (default):
           - node_modules
    -----> Build succeeded!
           └── cfenv@1.0.3
    
    -----> Uploading droplet (14M)
    
    0 of 1 instances running, 1 starting
    1 of 1 instances running
    
    App started
    
    OK
    
    App cf-node-hellocloud was started using this command `./vendor/initial_startup.rb`
    
    Showing health and status for app cf-node-hellocloud in org theiotlearninginitiative@gmail.com / space dev as theiotlearninginitiative@gmail.com...
    
    OK
    
    requested state: started
    instances: 1/1
    usage: 128M x 1 instances
    urls: cf-node-hellocloud-tili.mybluemix.net
    last uploaded: Sun Dec 27 16:27:01 UTC 2015
    stack: cflinuxfs2
    buildpack: SDK for Node.js(TM) (ibm-node.js-0.12.9)
    
         state     since                    cpu    memory        disk          details   
    #0   running   2015-12-27 10:27:45 AM   0.0%   29M of 128M   52.6M of 1G  
    user@host:~$ 
```

Credit to [Cloud Foundry Workshops](http://www.cloudworkshop.org/cloudfoundry/)

### Hello World Flask Python


Deploy [Python Hello World Flask](https://github.com/IBM-Bluemix/python-hello-world-flask) to IBM Bluemix, Full recipe [Here](https://developer.ibm.com/bluemix/2015/03/30/simple-hello-world-python-app-using-flask/)

    user@host:~$ cd
    user@host:~$ git clone https://github.com/IBM-Bluemix/python-hello-world-flask.git
    user@host:~$ cd python-hello-world-flask
    user@host:~$ cf push hellocloudpython

