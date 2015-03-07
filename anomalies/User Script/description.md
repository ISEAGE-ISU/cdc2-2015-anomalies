#User Script
##Description
Our administrators would like to the ability to edit the users on our two websites via the commandline on the managements server rather than needing to use the web interface on the websites.
##Instructions
Add a script in the same folder as the management scripts.  The script should be named "users.?" where ? is the extension of the file.  You may use PHP, a bash script, or Python.  The script should follow the API below and should take care of all necessary operations to update the website and the backend database.

Adding User:
Should be able to add Employees or Administrators (not necessary to be able to add clients)
users.? add <server> <username> <password> <permission>
<server> Website for which to add user; either "www" or "www2"
<username> Username of new user
<password> Password of new user
<permission> Either "admin" or "employee".  You do not need to allow employees to be created on www website.

Example:  "users.sh add www2 Alice password123 employee"

Removing User:
users.? remove <server> <username>
<server> Server for which to remove user; either "www" or "www2"
<username> Username of user to remove

Example: "python users.py remove www Alice"

Edit User:
users.? edit <server> <username> field1 new_value field2 new_value ...
<server> Server for which to edit user; either "www" or "www2"
<username> Username of user to edit
field1 new_value ... Field names followed by new values.  Possible field names are "username", "password", and "permission".  Not all fields are required.

Examples: "php users.php edit www Alice password 123456"  - which would set Alice's password to 123456.

Print Users:
users.? print <server>
<server> Website for which to print users; either "www" or "www2"
Example:  "php users.php print www"
