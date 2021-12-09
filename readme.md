[comment]: # "Auto-generated SOAR connector documentation"
# Blue Coat

Publisher: Blackstone  
Connector Version: 1\.1\.4  
Product Vendor: Blue Coat Systems, Inc\.  
Product Name: Blue Coat  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 1\.2\.265  

Query Blue Coat cloud services and configure appliance\.

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Blue Coat asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**source\_ip** |  required  | string | IP of host making the REST calls \(or "any"\)
**proxy\_host** |  required  | string | Proxy hostname or IP
**proxy\_mgmt\_port** |  required  | numeric | Management interface port
**username** |  required  | string | Username to use for URL reputation action
**password** |  required  | password | Password to use for URL reputation action
**verify\_server\_cert** |  required  | boolean | Verify server certificate

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity\. This action logs into the device to check the connection and credentials\.  
[block url](#action-block-url) - Block an URL  
[unblock url](#action-unblock-url) - Unblock an URL  
[allow url](#action-allow-url) - Allow an URL  
[disallow url](#action-disallow-url) - Disallow an URL  
[url reputation](#action-url-reputation) - Queries WebPulse Site Review for URL info\.  

## action: 'test connectivity'
Validate the asset configuration for connectivity\. This action logs into the device to check the connection and credentials\.

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'block url'
Block an URL

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to block | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.blacklist\. | string | 
action\_result\.status | string | 
action\_result\.summary | string | 
action\_result\.parameter\.url | string |  `url`   

## action: 'unblock url'
Unblock an URL

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to unblock | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.blacklist\. | string | 
action\_result\.status | string | 
action\_result\.summary | string | 
action\_result\.parameter\.url | string |  `url`   

## action: 'allow url'
Allow an URL

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to allow | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.whitelist\. | string | 
action\_result\.status | string | 
action\_result\.summary | string | 
action\_result\.parameter\.url | string |  `url`   

## action: 'disallow url'
Disallow an URL

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to disallow | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.whitelist\. | string | 
action\_result\.status | string | 
action\_result\.summary | string | 
action\_result\.parameter\.url | string |  `url`   

## action: 'url reputation'
Queries WebPulse Site Review for URL info\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to query | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.url | string |  `url` 
action\_result\.data\.\*\.BlueCoat | string | 
action\_result\.status | string | 
action\_result\.summary | string | 
action\_result\.parameter\.url | string |  `url` 