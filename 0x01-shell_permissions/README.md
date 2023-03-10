<h1>Scripts Functions</h1>

<b>0-iam_betty:</b> switches the current user to the user betty.

<b>1-who_am_i:</b> prints the effective username of the current user

<b>2-groups:</b> prints all the groups the current user is part of.

<b>3-new_owner:</b> changes the owner of the file hello to the user betty.

<b>4-empty:</b> creates an empty file called hello

<b>5-execute:</b> adds execute permission to the owner of the file hello

<b>6-multiple_permissions:</b> adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.

<b>7-everybody:</b> adds execution permission to the owner, the group owner and the other users, to the file hello

<b>8-James_Bond:</b> sets the permission to the file hello as follows:

		Owner: no permission at all
		Group: no permission at all
		Other users: all the permissions

<b>9-John_Doe:</b> sets the mode of the file hello to this: -rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello

<b>10-mirror_permissions:</b> sets the mode of the file hello the same as olleh’s mode.

<b>11-directories_permissions:</b> adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.

<b>12-directory_permissions:</b> creates a directory called my_dir with permissions 751 in the working directory.

<b>13-change_group:</b> changes the group owner to school for the file hello

<b>100-change_owner_and_group:</b> changes the owner to vincent and the group owner to staff for all the files and directories in the working directory.

<b>101-symbolic_link_permissions:</b> changes the owner and the group owner of _hello to vincent and staff respectively.

<b>102-if_only:</b> changes the owner of the file hello to betty only if it is owned by the user guillaume.

<b>103-Star_Wars:</b> play the StarWars IV episode in the terminal.
