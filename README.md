## Bell Toronto workshop materials Jan 30 - Feb 3 2017



#### Preparation
   - [Preparation on Windows](00-01-setup-machine/Setup_Windows.md)
   - [Preparation on MAC](00-01-setup-machine/Set_up_the_Mac_Environment.md)
   - [Preparation on Linux](00-01-setup-machine/Set_up_Linux_VM.md)

#### [Designing microservices](Microservices-Design.md) - Design steps to help you understand the design decisions before getting into deploying the actual application.

   
a. Setup [cloudant NoSQL database](02-01-03-cloud-data-services/using-cloudant.md)

b. Setup [mysql container](https://github.com/ibm-cloud-architecture/refarch-cloudnative-mysql)
	
* If you can't install Docker locally then use these hints   [Docker on Blumix w/o docker local](02-02-hybrid-cloud/docker-bmx-build.md)
   
c. Deploy [Social review microservice](https://github.com/ibm-cloud-architecture/refarch-cloudnative-micro-socialreview)

d. Deploy [Inventory microservice](https://github.com/ibm-cloud-architecture/refarch-cloudnative-micro-inventory)

e. Deploy the fabric [eureka](https://github.com/ibm-cloud-architecture/refarch-cloudnative-netflix-eureka) 

f. Deploy the fabric [zuul](https://github.com/ibm-cloud-architecture/refarch-cloudnative-netflix-zuul) 

g. Deploy the [Inventory BFF (backend for frontend](https://github.com/ibm-cloud-architecture/refarch-cloudnative-bff-inventory)

h. Deploy the [Social review BFF (backend for frontend)](https://github.com/ibm-cloud-architecture/refarch-cloudnative-bff-socialreview)

i. Set up [API Connect environment](https://github.com/ibm-cloud-architecture/refarch-cloudnative-api)

j. Deploy the [Web application](https://github.com/ibm-cloud-architecture/refarch-cloudnative-bluecompute-web)

k. Deploying the [Mobile application](https://github.com/ibm-cloud-architecture/refarch-cloudnative-bluecompute-mobile)

##### These exercises are based on reference implementation for building an [OmniChannel Application using a microservices architecture.](https://github.com/ibm-cloud-architecture/refarch-cloudnative)