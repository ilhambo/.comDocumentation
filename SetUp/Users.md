##Users in the Portal and the Umbraco Backoffice

###User Roles
- Admin: An admin user has access to everything on a Project. An admin is the only user that can Delete and Rename a Project, and only admins can edit the Team (adding/removing other project users and changing permissions). An admin can deploy using Portal and has access to git.
- Write: A user with Write permissions can do everything on a Project except Delete, Rename and edit Team. A user with Write permissions is able to Deploy through the Portal and they have access to Development and Staging environments and the git repositories.
- Read: A user with Read permissions can only view the Project in the Portal, and is not able to Deploy or change anything on the Project through the Portal.

In terms of the Umbraco backoffice, all users created through the Portal is created as admin users in the backoffice. This is currently being changed, so all users who are not explicitly created as Admin (checkbox) in the Portal, will then be created as Editors in the Umbraco backoffice.

In summary, currently Admin, Write, Read permissions will give you an Umbraco admin user in the backoffice. 

Once the planned change has been implemented, and a new version of Courier is rolled out only (Portal) Admin users will give you an Admin user in the Umbraco backoffice as well (with access to all sections). Users with Write and Read will give you an Editor user in the Umbraco backoffice with access to Content, Media, Forms and Member sections
