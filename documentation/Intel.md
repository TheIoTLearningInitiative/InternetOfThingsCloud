Intel
==

## Cloud

[Cloud Based Solutions](https://www-ssl.intel.com/content/www/us/en/cloud-computing/intel-cloud-based-solutions.html)
[Cloud Foundry & Open Stack](http://www.slideshare.net/animeshsingh2011/intel-cloud-foundry-and-openstack)

## Intel® IoT Developer Kit Cloud-based Analytics

> Intel provides a cloud-based analytics system for the Internet-of-Things (IoT) that includes resources for the collection and analysis of sensor data that the Intel® IoT Developer Kit provides. Using this service, Intel Galileo/Edison device developers can jump-start data acquisition and analysis without having to invest in large-scale storage and processing capacity.

    # Create an account
      https://dashboard.us.enableiot.com/
    # In Edison / Galileo
    root@galileo:~# iotkit-admin initialize  
    root@galileo:~# iotkit-admin reset-components  
    root@galileo:~# iotkit-admin test
    root@galileo:~# iotkit-admin device-id
    # From https://dashboard.us.enableiot.com/ui/dashboard#/devices, add a New Device
    # From https://dashboard.us.enableiot.com/ui/dashboard#/account, get Activation Code
    root@galileo:~# iotkit-admin activate <Activation Code from Webpage>
    root@galileo:~# iotkit-admin catalog
    root@galileo:~# iotkit-admin register temp temperature.v1.0
    root@galileo:~# iotkit-admin observation temp 35
    root@galileo:~# iotkit-admin observation temp 30

* [Intel® IoT Developer Kit Cloud-based Analytics Homepage](www.enableiot.com)
* [Intel® IoT Developer Kit Cloud-based Analytics User Guide](https://software.intel.com/en-us/intel-iot-developer-kit-cloud-based-analytics-user-guide)

## Intel® Trusted Analytics Platform

* [Simplify Big Data Analytics with Open Source Software](http://download.intel.com/newsroom/kits/iot/pdfs/TAP_FactSheet.pdf)

## Intel® Mashery

> Provides infrastructure that helps media companies develop, publish, and manage application programming interfaces, or APIs, which allow outside developers to incorporate another company’s content into their products.

- [Mashery Homepage](http://www.mashery.com/)
- [Mashery Rex St John Interview](http://hackathon.posthaven.com/rex-st-john-reps-a-stable-of-apis-for-intel-mashery)

## Intel® Discovery Peak

> A Platform-as-a-Service cloud stack for data scientists and application developers to build and operate domain-specific applications driven by data analysis at scale.

- [Building More Valuable Solutions as App Deployment, Data and Analytics Come Together](https://software.intel.com/en-us/blogs/2015/08/14/building-more-valuable-solutions-as-app-deployment-data-and-analytics-come-together)
- [Discovery Peak Wiki](https://github.com/trustedanalytics/platform-wiki/wiki)
- [Discovery Peak Getting Started Guide](https://github.com/trustedanalytics/platform-wiki/wiki/Getting%20Started%20Guide)

