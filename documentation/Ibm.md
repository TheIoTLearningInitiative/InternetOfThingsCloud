IBM
==

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

## Embedded C Client Library - Introduction

> Embedded C client for interacting with the IBM Watson Internet of Things Platform.

```sh
    root@board:~# git clone https://github.com/ibm-messaging/iotf-embeddedc.git
    Cloning into 'iotf-embeddedc'...
    remote: Counting objects: 124, done.
    remote: Total 124 (delta 0), reused 0 (delta 0), pack-reused 124
    Receiving objects: 100% (124/124), 71.47 KiB | 0 bytes/s, done.
    Resolving deltas: 100% (59/59), done.
    Checking connectivity... done.
    root@board:~# cd iotf-embeddedc/
    root@board:~/iotf-embeddedc# ls
    LICENSE          gatewayclient.c  iotfclient.h
    README.md        gatewayclient.h  lib
    buildlib.sh      iotfclient.c     samples
    root@edison:~/iotf-embeddedc# ./buildlib.sh
    Compiling source files ...
    Linking libiotf.so libwiotdevice.so
    Removing temporary files...
    Build complete
    root@edison:~/iotf-embeddedc# cd samples/
    root@edison:~/iotf-embeddedc/samples# ls
    Makefile         build.sh         gateway.cfg      sampleDevice.c
    README.md        device.cfg       helloWorld.c     sampleGateway.c
    root@board:~/iotf-embeddedc/samples# make          
    cc sampleDevice.c -I ./../ -I ./../lib ./../iotfclient.c ./../lib/MQTTClient.c ./../lib/MQTTLinux.c ./../libe
    strip sampleDevice            
    cc helloWorld.c -I ./../ -I ./../lib ./../iotfclient.c ./../lib/MQTTClient.c ./../lib/MQTTLinux.c ./../lib/Md
    strip helloWorld
    cc sampleGateway.c -I ./../ -I ./../lib ./../gatewayclient.c ./../lib/MQTTClient.c ./../lib/MQTTLinux.c ./..y
    strip sampleGateway
    root@board:~/iotf-embeddedc/samples# ./helloWorld 
    Usage: helloWorld deviceId
    where,                                                                           deviceId is a 12 digit hex                                                       root@board:~/iotf-embeddedc/samples# ./helloWorld 123456789123                   Connection Successful. Press Ctrl+C to quit                                       View the visualization at https://quickstart.internetofthings.ibmcloud.com/#/device/123456789123                 Publishing the event stat with rc  0                                             Publishing the event stat with rc  0
      ...
      [Open your web browser and go the address specified above]
      ...
      Publishing the event stat with rc  0
      Publishing the event stat with rc  0
    ^ CSigINT received.
    Quitting!!                                                                       root@board:~/iotf-embeddedc/samples# 
```

## IBM Internet of Things Foundation for Python

```sh
    root@board:~# pip install ibmiotf
    root@board:~# git clone https://github.com/ibm-messaging/iot-python.git
    Cloning into 'iot-python'...
    remote: Counting objects: 1501, done.
    remote: Total 1501 (delta 0), reused 0 (delta 0), pack-reused 1501
    Receiving objects: 100% (1501/1501), 574.55 KiB | 212.00 KiB/s, done.
    Resolving deltas: 100% (882/882), done.
    Checking connectivity... done.
    root@board:~# cd iot-python/
    root@board:~/iot-python# ls
    CHANGES.txt  LICENSE      README.rst   setup.py
    CLA.md       MANIFEST.in  samples      src
    root@board:~/iot-python# python setup.py install
    running install
    running bdist_egg
    running egg_info
    Using /usr/lib/python2.7/site-packages
    Finished processing dependencies for ibmiotf==0.1.9
    root@board:~/iot-python# cd samples
    root@board:~/iot-python/samples# ls
    apiExamples          helloWorld           psutil
    cli                  httpsSupport         simpleApp
    customMessageFormat  managedDevice
    gatewayExamples      managedGateway
    root@board:~/iot-python/samples# cd helloWorld/
    root@board:~/iot-python/samples/helloWorld# ls
    README.md      helloworld.py
    root@board:~/iot-python/samples/helloWorld# python helloworld.py
    2016-03-05 18:46:48,839   ibmiotf.application.Client  INFO    Connected successfully: a:quickstart:6788e5b2-r
    2016-03-05 18:46:49,069   ibmiotf.device.Client      INFO    Connected successfully: d:quickstart:helloWorld6
    ...
    ^CTraceback (most recent call last):
    File "helloworld.py", line 81, in <module>
    time.sleep(1)                       
    KeyboardInterrupt
    root@board:~/iot-python/samples/helloWorld#
    root@board:~/iot-python/samples/helloWorld# cd ../psutil
    root@edison:~/iot-python/samples/psutil# python iotpsutil.py
    2016-03-05 18:51:44,770   ibmiotf.device.Client      INFO    Connected successfully: d:quickstart:sample-iotL
    (Press Ctrl+C to disconnect)
    root@edison:~/iot-python/samples/psutil# 
```
