## About

### KEMP

With over 40,000 worldwide deployments and offices in America, Europe, Asia and South America, KEMP Technologies is the industry leader in advanced Layer 2 – 7 Application Delivery Controllers (ADC) and application-centric load balancing.

Since 2000, KEMP has been a consistent leader in innovation with a number of industry firsts, including high performance ADC appliance virtualization, application-centric SDN and NFV integration, innovative pricing and licensing models and true platform ubiquity that can scale to support enterprises of every size and workload requirement.

### Test Drive Description

The KEMP Azure Test Drive will walk you through the initial setup of a KEMP Virtual LoadMaster. You will configure a the LoadMaster to send traffic to two web-server replicas as well as KEMP’s Edge Security Pack (ESP) which provides security and pre-authentication access to the backend web services.

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

![Edge Security Pack](images/esp.png "Edge Security Pack Topology")

## Test Drive: Getting Started

### Licensing and accessing the LoadMaster

Once the Test Drive deployment completes use the provided URL, Username, and Password to access the LoadMaster.

Enter the provided URL into your browser. **You must use TCP Port 8443 to access the LoadMaster Web User Interface (WUI).**
![Accessing the Web UI](images/access.png "Entering the Web UI")
Select "Continue to this website (not recommended)"
Enter the provided username and password:

* Username: bal
* Password: Kemp@testdrive1

![Web UI Authorization](images/auth.png "Accessing the Web UI")

Scroll down and accept the LoadMaster End User License Agreement
![EULA Agreement](images/eula.png "EULA Agreement")

KEMP Loadmasters require a free KEMP ID to function. If you do not have a KEMP ID, you can create one by going to https://kemptechnologies.com/kemp-id-registration. **Use the promo-code "TESTDRIVE" when registering.**

Enter your KEMP ID to license the Free LoadMaster and click "License Now"
![Logging in](images/login.png "Logging in")

Select VLM-BYOL-FREE-Azure and click "Continue"
![licensing](images/license.png "licensing")

On the Allow Call Home page select "Allow"
![call home](images/call_home.png "call home")

### Configuration

*Note: Configuration is only accessible after licensing.*

The Virtual Services on the LoadMaster defines the Virtual IP (VIP) address, port, protocol and Name.

