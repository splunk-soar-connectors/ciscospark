[comment]: # "Auto-generated SOAR connector documentation"
# Cisco Spark

Publisher: Phantom  
Connector Version: 1.0.11  
Product Vendor: Cisco  
Product Name: Cisco Spark  
Product Version Supported (regex): ".\*"  
Minimum Product Version: 3.0.284  

Integrate with Cisco Spark to implement investigative actions

### Configuration variables
This table lists the configuration variables required to operate Cisco Spark. These variables are specified when configuring a Cisco Spark asset in Splunk SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**authorization_key** |  required  | password | API Key

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[list rooms](#action-list-rooms) - List Spark rooms  
[get user](#action-get-user) - Get user_ID from e-mail address  
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
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.status | string |  |   success 
action_result.data.\*.created | string |  |   2018-01-05T02:43:33.032Z 
action_result.data.\*.creatorId | string |  `creater id`  |   Y2lzY29zcGFyazovL3VzL1BFT1BMRS9iMmMwZjIwMS03NGQyLTRkYTEtYWM0Yi1mNzc3ZmEwMDg2YmM 
action_result.data.\*.id | string |  `spark room id`  |   Y2lzY29zcGFyazovL3VzL1JPT00vMzg2NzFhODAtZjFjMi0xMWU3LTg1OWUtNDMzYWY3YWQ5YmJi 
action_result.data.\*.isLocked | boolean |  |   True  False 
action_result.data.\*.lastActivity | string |  |   2018-01-08T21:26:38.851Z  2018-01-16T18:37:12.037Z 
action_result.data.\*.title | string |  |   Test Alert Space 
action_result.data.\*.type | string |  |   group 
action_result.summary | string |  |  
action_result.message | string |  |    
summary.total_objects | numeric |  |   1 
summary.total_objects_successful | numeric |  |   1   

## action: 'get user'
Get user_ID from e-mail address

Type: **investigate**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**email_address** |  required  | user spark e-mail address | string |  `email` 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.status | string |  |   success 
action_result.parameter.email_address | string |  `email`  |   monielynn@theharlanfamily.org 
action_result.data.\*.\*.displayName | string |  |   Monika Harlan 
action_result.data.\*.\*.id | string |  `spark user id`  |   Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hMzllMGQ4Mi01ZWE0LTQ3OTktOWM3Zi00M2E0MTI4MjUzYjU 
action_result.data.\*.created | string |  |   2018-01-04T20:46:30.734Z 
action_result.data.\*.emails | string |  `email`  |   monielynn@theharlanfamily.org 
action_result.data.\*.lastActivity | string |  |   2018-01-05T21:04:53.424Z 
action_result.data.\*.nickName | string |  |   Monika 
action_result.data.\*.orgId | string |  |   Y2lzY29zcGFyazovL3VzL09SR0FOSVpBVElPTi9jb25zdW1lcg 
action_result.data.\*.status | string |  |   inactive 
action_result.data.\*.type | string |  |   person 
action_result.summary | string |  |  
action_result.message | string |  |    
summary.total_objects | numeric |  |   1 
summary.total_objects_successful | numeric |  |   1   

## action: 'send message'
Send Message to user or room

Type: **investigate**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**endpoint_id** |  required  | User or Room ID | string |  `spark user id`  `spark room id` 
**destination_type** |  required  | Destination Type | string | 
**message** |  required  | message | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.status | string |  |   success 
action_result.parameter.destination_type | string |  |   room 
action_result.parameter.endpoint_id | string |  |   Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hMzllMGQ4Mi01ZWE0LTQ3OTktOWM3Zi00M2E0MTI4MjUzYjU  Y2lzY29zcGFyazovL3VzL1JPT00vMzg2NzFhODAtZjFjMi0xMWU3LTg1OWUtNDMzYWY3YWQ5YmJi 
action_result.parameter.message | string |  |   Compile Test  hello room 
action_result.data.\*.created | string |  |   2018-01-08T21:27:31.755Z  2018-03-30T18:36:01.210Z 
action_result.data.\*.id | string |  |   Y2lzY29zcGFyazovL3VzL01FU1NBR0UvYmM0MGQ3YjAtZjRiYS0xMWU3LWI5NGEtMzMxMmE4MmI4ZmVl  Y2lzY29zcGFyazovL3VzL01FU1NBR0UvMzIxMjA5YTAtMzQ0OS0xMWU4LWJjNmUtMWJkNzlhODNjMTY3 
action_result.data.\*.personEmail | string |  `email`  |   herman@contoso.com 
action_result.data.\*.personId | string |  |   Y2lzY29zcGFyazovL3VzL1BFT1BMRS9iMmMwZjIwMS03NGQyLTRkYTEtYWM0Yi1mNzc3ZmEwMDg2YmM 
action_result.data.\*.roomId | string |  |   Y2lzY29zcGFyazovL3VzL1JPT00vODliODk1ZWYtYjk2YS0zMTk0LTlhNDQtNDAxZTk4MzBiNGY5  Y2lzY29zcGFyazovL3VzL1JPT00vMzg2NzFhODAtZjFjMi0xMWU3LTg1OWUtNDMzYWY3YWQ5YmJi 
action_result.data.\*.roomType | string |  |   direct  group 
action_result.data.\*.text | string |  |   Compile Test  hello room 
action_result.data.\*.toPersonId | string |  |   Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hMzllMGQ4Mi01ZWE0LTQ3OTktOWM3Zi00M2E0MTI4MjUzYjU 
action_result.summary | string |  |  
action_result.message | string |  |     Message Sent 
summary.total_objects | numeric |  |   1 
summary.total_objects_successful | numeric |  |   1 