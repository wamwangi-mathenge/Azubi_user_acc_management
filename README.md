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