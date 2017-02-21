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


## Testing the configuration

### Testing the Virtual Service

*To test the functionality of the Virtual Service, use the same URL that was used to access the LoadMaster. This time the HTTP protocol will be used on port 80. Example: http://vlmhoeeei2eds2boe.eastus.cloudapp.azure.com*


1. Open your browser and navigate using the URL provided by your Test Drive.  The page below will be displayed in your browser.
![it worked](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/itworked.png "it worked")


1. On the KEMP LoadMaster left hand navigation select Statistics and Real Time Statistics
![real time statistics](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/rts.png "real time statistics")


1. Click through the Global, Real Servers, Virtual Services, Connections, Bytes, Bits, and Packets to see the statistical information provided by the KEMP LoadMaster.
![stats](https://github.com/KEMPtechnologies/azure-test-drive/raw/master/images/stats.png "your stats")


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
