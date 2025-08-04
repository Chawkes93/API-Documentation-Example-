https://docs.google.com/document/d/1mMFDLcRsz-lhOhG6QccSI34rxuuuadQn3iWdObYw0dE/edit?usp=sharing

Tag & Consent Category Management
Summary: The following endpoints will be required to handle tag and consent category data, to and from ObservePoint, within an internal customer interface.

Get All Tags in OP Database:

URL
https://api.observepoint.com/v3/tags
Method
GET
Payload
N/A
Notes


Purpose
When a customer interface user wants to request a tag to be approved, they will select from a list of all ObservePoint tags



Get List of All Consent Categories:

URL
https://api.observepoint.com/v3/consent-categories/library
Method
GET
Payload
N/A
Notes


Purpose
For customer interface users  to pul al list of Consent Categories currently in OP, from which they can select for later adding tags, or for viewing which tags are currently listed in the Consent Category; Consent Category ID is found in payload










Get list of tags within a particular Consent Category:

URL
https://api.observepoint.com/v3/consent-categories/{consent-category-ID}/tags
Method
GET
Payload
N/A
Notes


Purpose
For viewing which tags are currently listed in the selected Consent Category; Consent Category ID is found in payload



Create new Consent Category:

URL
https://api.observepoint.com/v3/consent-categories/library
Method
POST
Payload
{"name":"Test","notes":"","type":"approved","isDefaultCC":false}
Notes
Tags will need to be added with another endpoint afterwards (below). This endpoint does not add tags to Consent Categories.
Purpose
If the customer interfacex user cannot find an already existing Consent Category for the website they are targeting, this endpoint will create one.














Add tag(s) to Consent Category:

URL

https://api.observepoint.com/v3/consent-categories/{consent-category-ID}/tags
Method
PATCH
Payload
[{"op":"add","path":"/0","value":{"tagId":1,"accounts":[]}}]
Notes
Tag Id is referenced in the JSON object, Consent Category ID is referenced in the path (/consent-categories/{consent_category_ID}/tags)
Purpose
Customer interface will ultimately add newly approved/categorized tags into Consent Categories in OP





Reporting
The following link provides documentation on how to pull in a pre-configured report from ObservePoint:
https://api-docs.observepoint.com/sections/grid-api-examples/use-saved-report-configruation
