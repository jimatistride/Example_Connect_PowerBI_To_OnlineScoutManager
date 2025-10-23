## The following is taken from OSMs website October 2025

URLs

Authorisation
https://www.onlinescoutmanager.co.uk/oauth/authorize
If you are using the 'authorization code flow', your client library will build a link based on this URL that your users will click - this will bring them to OSM where they will be asked to log in. If they log in and authorise your application, they will be redirected back to the Redirect URL you specify.

Access token
https://www.onlinescoutmanager.co.uk/oauth/token
When the user has been redirected back to your application, your client library will make a request to this URL to get an 'access token' and a 'refresh token' - these should be stored in your database.

Resource owner
https://www.onlinescoutmanager.co.uk/oauth/resource
This will provide you with the user's full name, email address, and a list of sections that your application can access.

Scopes
Prefix each of the following scopes with 'section:' and add the suffix of ':read' or ':write' to determine if your application needs read access (:read) or read and write access (:write).

The 'administration' and 'finance' scopes have an additional suffix of ':admin' which is used for editing critical settings.

Please ask for the lowest possible set of permissions as you will not be able to see sections unless the user has all the permissions your application specifies.

administration - Administration / settings areas.

attendance - Attendance Register

badge - Badge records

event - Events

finance - Financial areas (online payments, invoices, etc)

flexirecord - Flexi-records

member - Personal details, including adding/removing/transferring, emailing, obtaining contact details etc.

programme - Programme

quartermaster - Quartermaster's area