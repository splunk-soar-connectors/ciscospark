[comment]: # "Auto-generated SOAR connector documentation"
# Cisco Spark

Publisher: Phantom  
Connector Version: 1\.0\.9  
Product Vendor: Cisco  
Product Name: Cisco Spark  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.284  

Integrate with Cisco Spark to implement investigative actions

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Cisco Spark asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**authorization\_key** |  required  | password | API Key

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[list rooms](#action-list-rooms) - List Spark rooms  
[get user](#action-get-user) - Get user\_ID from e\-mail address  
[send message](#action-send-message) - Send Message to user or room  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'list rooms'
List Spark rooms

Type: **investigate**  
Read only: **False**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.data\.\*\.created | string | 
action\_result\.data\.\*\.creatorId | string |  `creater id` 
action\_result\.data\.\*\.id | string |  `spark room id` 
action\_result\.data\.\*\.isLocked | boolean | 
action\_result\.data\.\*\.lastActivity | string | 
action\_result\.data\.\*\.title | string | 
action\_result\.data\.\*\.type | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get user'
Get user\_ID from e\-mail address

Type: **investigate**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**email\_address** |  required  | user spark e\-mail address | string |  `email` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.email\_address | string |  `email` 
action\_result\.data\.\*\.\*\.displayName | string | 
action\_result\.data\.\*\.\*\.id | string |  `spark user id` 
action\_result\.data\.\*\.created | string | 
action\_result\.data\.\*\.emails | string |  `email` 
action\_result\.data\.\*\.lastActivity | string | 
action\_result\.data\.\*\.nickName | string | 
action\_result\.data\.\*\.orgId | string | 
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.type | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'send message'
Send Message to user or room

Type: **investigate**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**endpoint\_id** |  required  | User or Room ID | string |  `spark user id`  `spark room id` 
**destination\_type** |  required  | Destination Type | string | 
**message** |  required  | message | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.destination\_type | string | 
action\_result\.parameter\.endpoint\_id | string | 
action\_result\.parameter\.message | string | 
action\_result\.data\.\*\.created | string | 
action\_result\.data\.\*\.id | string | 
action\_result\.data\.\*\.personEmail | string |  `email` 
action\_result\.data\.\*\.personId | string | 
action\_result\.data\.\*\.roomId | string | 
action\_result\.data\.\*\.roomType | string | 
action\_result\.data\.\*\.text | string | 
action\_result\.data\.\*\.toPersonId | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 