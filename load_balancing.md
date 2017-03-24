### KEMP

With over 40,000 worldwide deployments and offices in America, Europe, Asia and South America, KEMP Technologies is the industry leader in advanced Layer 2 – 7 Application Delivery Controllers (ADC) and application-centric load balancing.

Since 2000, KEMP has been a consistent leader in innovation with a number of industry firsts, including high performance ADC appliance virtualization, application-centric SDN and NFV integration, innovative pricing and licensing models and true platform ubiquity that can scale to support enterprises of every size and workload requirement.

### Test Drive Description

The KEMP Azure Test Drive will walk you through the initial setup of a KEMP Virtual LoadMaster. You will configure a LoadMaster to send traffic to two web-server replicas.

## Test Drive: Getting Started

### Licensing and accessing the LoadMaster

Once the Test Drive deployment completes use the provided URL Username and Password to access the LoadMaster.

Enter the provided URL into your browser. **You must use TCP Port 8443 to access the LoadMaster Web User Interface (WUI).**

*Example: https://vlmhoeeei2eds2boe.eastus.cloudapp.azure.com:8443*

![Accessing the Web UI](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/access.png "Entering the Web UI")
Select "Continue to this website (not recommended)"
Enter the provided username and password:

 * Username: bal
 * Password: Kemp@testdrive1

![Web UI Authorization](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/auth.png "Accessing the Web UI")

1. Scroll down and accept the LoadMaster End User License Agreement
![EULA Agreement](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/eula.png "EULA Agreement")


1. KEMP LoadMasters require a free KEMP ID to function. If you do not have a KEMP ID, you can create one by going to https://kemptechnologies.com/kemp-id-registration. **Use the promo-code "TESTDRIVE" when registering.**


1. Enter your KEMP ID to license the Free LoadMaster and click "License Now"
![Logging in](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/login.png "Logging in")


1. Select VLM-BYOL-FREE-Azure and click "Continue"
![licensing](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/license.png "licensing")

1. On the Allow Call Home page select "Allow"
![call home](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/call_home.png "call home")

## LoadMaster Configuration

### Setting up a Virtual Service and Real Server

*Note: Configuration is only accessible after licensing.*

The Virtual Services on the LoadMaster defines the Virtual IP (VIP) address, port, protocol and Name.

1. In the left-hand navigation select Virtual Services and click Add New

![virtual service](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/vs.png "Virutal Service")


1. Enter a Name for the Virtual Service and click Add this Virtual Service. Leave the Virtual Address, Port, and Protocol as the defaults.
![adding a virtual service](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/adding_vs.png "adding a virtual service")
*For this step of the Test Drive all options and properties will remain unchanged.  Feel free to navigate through the Virtual Service options to familiarize yourself with the features and functions KEMP provides on the LoadMaster.*


1. Select Real Servers
![adding a real server](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/rs.png "adding a real server")


1. Select add new
![adding a new real server](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/add_new.png "adding a new real server")


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


### Next Steps

Hopefully this Azure Test Drive demonstrated how easy the KEMP LoadMaster is to setup and operate.  Additional features can be explored through our Free LoadMaster in the Azure Marketplace or one of our full featured offerings provided with either hourly or bring your own license (BYOL) options. If you'd like to speak with a KEMP representative contact us at http://kemptechnologies.com/contact

## Additional Links
 
[KEMP LoadMaster in Azure](https://kemptechnologies.com/azure/) 

[Documentation](https://kemptechnologies.com/loadMaster-documentation)

[KEMP 360](https://kemptechnologies.com/kemp360/application-network-optimization-performance-management/)
