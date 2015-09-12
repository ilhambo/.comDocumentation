#Users in the Portal and the Umbraco Backoffice
For Agency plans you can add users to your projects from the Umbraco as a Service portal and these users get automatically added to the backoffice of all umbraco sites for your project.  The users will also be created in local clones of you development site.  The same username and password is used to login in all parts of Umbraco as a Service - portal, backoffice, Kudu console.

##User Roles
* Admin: An admin user has access to everything on a Project. An admin is the only user that can Delete and Rename a Project, and only admins can edit the Team (adding/removing other project users and changing permissions). An admin can deploy using Portal and has access to git

* Write: A user with Write permissions can do everything on a Project except Delete, Rename and edit Team. A user with Write permissions is able to Deploy through the Portal and they have access to Development and Staging environments and the git repositories

* Read: A user with Read permissions can only view the Project in the Portal, and is not able to Deploy or change anything on the Project through the Portal.

_Important Note:_
All users created through the Portal are created as admin users in the backoffice. This is currently (August 2015) being changed, so all users who are not explicitly created as Admin users in the Portal, will be created as Editors in the Umbraco backoffice.

In summary, currently:
* Admin, Write, Read permissions will give you an Umbraco Admin user in the backoffice.

In the future:
* Admin users will give you an Admin user in the Umbraco backoffice as well (with access to all sections)
* Users with Write and Read will give you an Editor user in the Umbraco backoffice with access to Content, Media, Forms and Member sections
