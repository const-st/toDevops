#### Users
 create a user with a home folder and bash shell 
`useradd -m -s /bin/bash username`
add a user to the sudo group (на Debian/Ubuntu)
`usermod -aG sudo username
or for CentOS/RHEL/Fedora  use wheel group:
`usermod -aG wheel username`
 Set a password (required!)
 `passwd usrname`
 Create the .ssh folder in the user's home directory
`mkdir /home/username/.ssh`

 Setting the correct access rights
```
chmod 700 /home/иusername.ssh
chown username:username /home/username/.ssh
```

(Optional) Crete the authorized_keys and set access rights 
`touch /home/username/.ssh/authorized_keys`
`chmod 600 /home/username/.ssh/authorized_keys`
```
chown username:username /home/username/.ssh/authorized_keys
```

```
useradd -m -s /bin/bash username && \
usermod -aG sudo username && \
echo "username:PASSWORD" | chpasswd && \
mkdir -m 700 /home/username/.ssh && \
chown username:username /home/username/.ssh
```

```
# Create the .ssh/ and a file with a key in one operation
mkdir -p /home/username/.ssh
echo "public_ssh_key" > /home/username.ssh/authorized_keys

# set access rights
chmod 700 /home/username/.ssh
chmod 600 /home/username/.ssh/authorized_keys
chown -R username:username /home/username/.ssh
```

#### Groups
/etc/group
/etc/gshadow
Easy creation (the system will assign the GID automatically)
`sudo groupadd GroupName`
Create with a specific GID
`sudo groupadd -g 1234 -g 1234 GroupName`
Create system group 
`sudo groupadd -r system_GroupName`
view the created group
`grep GroupName /etc/group`

group change
`sudo groupmod -n new_GroupName old_GroupName`
Change group GID
`sudo groupmod -g 2000-GID GrouName`
> [!attention] 
> After changing the Guid, you must manually update the owner of the files that referenced the old GID 

delete group
`sudo gropdel GroupName`

##### Managing users in groups
adding users to groups
`sudo usermod -aG GroupName username`
Removing a users from a groups
There's no direct command. I need to use `gpasswd` or edit a file
`sudo gpasswd -d username GroupName`

