Cloud Foundry
==

> Cloud Foundry is an open source cloud computing platform as a service (PaaS) originally developed by VMware and now owned by Pivotal Software - a joint venture by EMC, VMware and General Electric. Cloud Foundry was designed and developed by a small team from Google led by Derek Collison and was originally called project B29. Cloud Foundry is primarily written in Ruby and Go. [Wikipedia](https://en.wikipedia.org/wiki/Cloud_Foundry)

> The Cloud Foundry Certified PaaS program gives you the confidence of knowing your applications and skills are portable across certified providers.

> Cloud Foundry gives companies the speed, simplicity and control they need to develop and deploy applications faster and easier.

Companies using the Cloud Foundry platform:

- GE's Predix
- IBM Bluemix
- CenturyLink
- ActiveState
- HP Helion
- anynines
- Swisscom

Cloud Foundry Is Built On An Open Architecture offering the following features:

> __Router__ 
> > Routes incoming traffic to the appropriate component, usually the Cloud Controller or a running application on a DEA node.
> __OAuth2 server authentication__
> > The OAuth2 server and Login Server work together to provide identity management.

> __Cloud Controller__ 
> > The Cloud Controller is responsible for managing the lifecycle of applications.

> __HM9000__ 
> > HM9000 monitors, determines and reconciles applications to determine their state, version and number of instances, and directs Cloud Controller to take action to correct any discrepancies.
Droplet Execution Agent

> __Application Execution (DEA)__ 
> > The Droplet Execution Agent manages application instances, tracks started instances, and broadcasts state messages.

> __Blob Store__ 
> > The blob store holds, application code, buildpacks and droplets.

> __Service Brokers__ 
> > When a developer provisions and binds a service to an application, the service broker for that service is responsible for providing the service instance.

> __Message Bus__ 
> > Cloud Foundry uses NATS, a lightweight publish-subscribe and distributed queueing messaging system, for internal communication between components.
global perception study

> __Logging and Statistics__ 
> > The metrics collector gathers metrics from the components. Operators can use this information to monitor an instance of Cloud Foundry.

### Links

- [Cloud Foundry Foundation Homepage](https://www.cloudfoundry.org/)
- [Cloud Foundry Foundation Documentation](https://docs.cloudfoundry.org/)
- [Cloud Foundry Foundation Keynote](https://www.youtube.com/watch?v=cvIjvbjB7qo)
- [Cloud Foundry Foundation Incubator](https://github.com/cloudfoundry-incubator)
- [Cloud Foundry Foundation Active Projects](https://github.com/cloudfoundry)
- [Cloud Foundry Foundation Python Libraries](https://pypi.python.org/pypi?%3Aaction=search&term=cloud+foundry&submit=search)
