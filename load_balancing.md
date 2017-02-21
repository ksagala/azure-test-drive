### KEMP

With over 40,000 worldwide deployments and offices in America, Europe, Asia and South America, KEMP Technologies is the industry leader in advanced Layer 2 – 7 Application Delivery Controllers (ADC) and application-centric load balancing.

Since 2000, KEMP has been a consistent leader in innovation with a number of industry firsts, including high performance ADC appliance virtualization, application-centric SDN and NFV integration, innovative pricing and licensing models and true platform ubiquity that can scale to support enterprises of every size and workload requirement.

### Test Drive Description

The KEMP Azure Test Drive will walk you through the initial setup of a KEMP Virtual LoadMaster. You will configure a the LoadMaster to send traffic to two web-server replicas as well as KEMP’s Edge Security Pack (ESP) which provides security and pre-authentication access to the backend web services.

1. Under Real Server Address enter 10.0.0.10 and click Add This Real Server, then click OK
![adding a new real server 2](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/adding_real_server_step2.png "adding a new real server 2")


1. Under Real Server Address enter 10.0.0.11 and click Add this Real Server, then click OK
![adding a new real server 3](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/adding_real_server_step3.png "adding a new real server 3")


1. In the left-hand navigation, under Virtual Services click View/Modify Services
![view modify](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/view_modify.png "view modify virtual services")


1. It will take a few seconds for validation of the Virtual Service to complete.  Once complete the Virtual Service Status will display UP with two healthy Real Servers.
![everythings up](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/everythings_up.png "everythings up")


## Testing the configuration

### Testing the Virtual Service

*To test the functionality of the Virtual Service, use the same URL that was used to access the LoadMaster. This time the HTTP protocol will be used on port 80. Example: http://vlmhoeeei2eds2boe.eastus.cloudapp.azure.com*


1. Open your browser and navigate using the URL provided by your Test Drive.  The page below will be displayed in your browser.
![it worked](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/itworked.png "it worked")


1. On the KEMP LoadMaster left hand navigation select Statistics and Real Time Statistics
![real time statistics](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/rts.png "real time statistics")


1. Click through the Global, Real Servers, Virtual Services, Connections, Bytes, Bits, and Packets to see the statistical information provided by the KEMP LoadMaster.
![stats](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/stats.png "your stats")
