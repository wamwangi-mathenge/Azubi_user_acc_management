# User Account Management
An introduction to user account management in Python

## Commands

```
useradd => Create a new user

groupadd => Create a new group

userdel => Delete a user

groupdel => Delete a group

usermod => Modify a user
```

## Files
Whenever we create a new user, their record is maintained in 3 different files

```
/etc/passwd

/etc/group

/etc/shadow
```

Example:

```
useradd -g superheros -s /bin/bash -c "user description" -m -d /home/spiderman spiderman
```

### Creating a user
The first command we will run is:
```
sudo useradd spiderman
```

Once it gives the prompt back, it means it did create your user "spiderman".

There is a command you can run to verify your user was created:

```
id spiderman
```

This will generate an output showing an ID assigned to the user "spiderman"

```
uid=1001(spiderman) gid=1005(spiderman) groups=1005(spiderman)
```

## Creating a Group
The command to add a new group is:

```
sudo groupadd superheroes
```
Once it gives the prompt back, it means it did create your group. 

You can verify by looking at the group file
```
# cat /etc/group
```
This will produce an output that shows the group you created.

## Delete a User
You can delete the user created by running the command:

```
sudo userdel -r spiderman
```

The `-r` deletes the directory as well.

You can verify that the user and the directory were deleted by running:

```
# ls -ltr
```

## Delete a Group
You can delete a group by running the command:
```
sudo group del superheroes
```

You can verify that the group was deleted by running:
```
$ cat /etc/group
```

## Modify a User
To modify a user, you can run:
```
sudo usermod -G superheroes spiderman
```
You can verify by running the command:
```
grep spiderman /etc/group
```

## Viewing Files
On creating a user or a group, there are files created. To view these files you can run the command:
```
cat /etc/passwd
```

At the bottom as you add your user to the Linux system, it adds the information of the user at the bottom:

```
spiderman:x:1002:1002::home/spiderman:/bin/bash
```

The first column tells you the name, the second one tells you the password which is encrypted, denoted by the `x`. It is followed by the user_id and the group_id and the directory of the user. The shell the user is using is shown at the very end.

The same can be used to view the group:
```
cat /etc/group
```
The output appears as such:
```
spiderman:x:1002
```
The output denotes the group by a name, then the group password which is the same password which is the same password that is used for anyone within that group and then the group id.

Another file you can look at is:
```
cat /etc/shadow
```

This file is strictly for passwords of users that we create. The passwords are encrypted thus cannot be seen.

To view the information on one user, you can run the command:
```
grep spiderman /etc/passwd
```
This gives only the information about the matching user - spiderman.

The above commands can be written in one single command like so:
```
useradd -g superheroes -s /bon/bash -c "Ironman Character" -m -d /home/ironman ironman
```

## Create a Password
After creating a user, it's best practice to create a password. This can be done by running the command:
```
passwd ironman
```