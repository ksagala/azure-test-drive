### KEMP

With over 40,000 worldwide deployments and offices in America, Europe, Asia and South America, KEMP Technologies is the industry leader in advanced Layer 2 – 7 Application Delivery Controllers (ADC) and application-centric load balancing.

Since 2000, KEMP has been a consistent leader in innovation with a number of industry firsts, including high performance ADC appliance virtualization, application-centric SDN and NFV integration, innovative pricing and licensing models and true platform ubiquity that can scale to support enterprises of every size and workload requirement.

### KEMP Edge Security Pack (ESP)

As organizations rely more and more on web-based applications and a mobile workforce, the importance of secure application publishing continues to increase. A solution that provides edge security, SSO application integration and flexible authentication options is critical for optimal user experience and information security policy compliance. 

To address this need, KEMP Technologies continues to expand on the comprehensive features offered by the Edge Security Pack (ESP) which enhances the LoadMaster load balancer’s ability to secure public-facing applications and improve user experience. As more than just a Reverse Proxy, ESP includes some of the most common features that TMG users are familiar with including:

* End Point Authentication for Pre-Auth
* Persistent Logging and Reporting 
* Single Sign On across Virtual Services
* Active Directory Integration
* RADIUS Authentication Support
* Fully Customizable FBA Forms
* Soft Lockout
* Group Membership Validation
* Dual factor auth w/RSA SecurID

![Edge Security Pack](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/esp.png "Edge Security Pack Topology")

## Test Drive: Getting Started

### Licensing and accessing the LoadMaster

Once the Test Drive deployment completes use the provided URL, Username, and Password to access the LoadMaster.

1. Enter the provided URL into your browser. **You must use TCP Port 8443 to access the LoadMaster Web User Interface (WUI).**

*Example: https://vlmhoeeei2eds2boe.eastus.cloudapp.azure.com:8443*

![Accessing the Web UI](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/access.png "Entering the Web UI")
Select "Continue to this website (not recommended)"
Enter the provided username and password:

 * Username: bal
 * Password: Kemp@testdrive1

![Web UI Authorization](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/auth.png "Accessing the Web UI")

1. Scroll down and accept the LoadMaster End User License Agreement
![EULA Agreement](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/eula.png "EULA Agreement")


1. KEMP Loadmasters require a free KEMP ID to function. If you do not have a KEMP ID, you can create one by going to https://kemptechnologies.com/kemp-id-registration. **Use the promo-code "TESTDRIVE" when registering.**


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

## Configuring KEMP Edge Security Pack (ESP)

*Now that the Virtual Service is configured and tested, the Edge Security Pack functionality can be added to secure the backend web application.*

Note: In this Test Drive environment RADIUS Authentication will be used but several other methods are available, such as LDAP (Active Directory), Certificates, and RSA-SecureID. For more information see the [KEMP Edge Security Pack](https://kemptechnologies.com/microsoft-load-balancing/microsoft-forefront-tmg-replacement/) page.

1. In the LoadMaster left hand navigation, select Virtual Services and select Manage SSO
![menu sso](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/menu_sso.png "menu sso")


1. Under Client Side Single Sign on Configurations, enter a name for the SSO domain and click Add
![sso domain](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/sso_domain.png "sso domain")


1. Configure the Single Sign on Domain with the following settings. Select the button to the right of each field to apply each setting.

  * Authentication Protocol = Radius
  * RADIUS Server(s) = 10.0.0.5
  * RADIUS Shared Secret (case sensitive) = testdrivesecret
  * Domain/ Realm (case sensitive) = testdrive.com 
![radius setup](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/radius_setup.png "radius_setup")


1. In the LoadMaster left hand navigation, select View/Modify Services

![vs view modify](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/vs_view_modify.png "vs view modify")


1. Select Modify on the Test Drive Virtual Service
![mod](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/mod.png "mod")


1. Select ESP Options and tick the Enable ESP box
![esp](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/esp2.png "esp2")


1. Configure the ESP Options with the following settings. Click the button to the right of each field to apply each setting.

  * Client Authentication Mode = Forms Based
  * SSO Domain = Select the name of the SSO domain created earlier
  * Allowed Virtual Directories = Enter the unique URL provided by your Test Drive
  * Allow Virtual Directories = /\*
![confesp](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/confesp.png "confesp")


## Test KEMP Edge Security Pack

*Now that the Single Sign On domain has been created and Edge Security Pack has been enabled on the Virtual Service, the pre-authentication functionality can be verified.*


1. Open browser and navigate using the URL provided by your Test Drive.  The authentication form below will be displayed in your browser. *Example: http://vlmhoeeei2eds2boe.eastus.cloudapp.azure.com*
![edge login](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/edge_login.png "edge login")


1. Enter the following credentials to access the web site.
 * Username = tduser1
 * Password = testdrivepass
 
 
 1. Once logged in you will once again be presented with the KEMP Demo Page.
 ![welcome](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/welcome.png "welcome")
 
 
 1. In the LoadMaster left hand navigation, select System Configuration, Logging Options and select Extended Log Files
 ![ext login](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/ext_log.png "ext login")
 
 
 1. Select View for ESP User Log
 ![view](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/view.png "view")


1. Notice the allowed login for tduser1.
 ![ohlook](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/ohlook.png "ohlook")
