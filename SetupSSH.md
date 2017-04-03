Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and password at each visit.

# Check for existing SSH keys

1. Open git bash
2. See existing SSH keys are present 
```java
ls -al ~/.ssh
```
   If you see any file with .pub suffix, it is an SSH key

# Generate a new SSH key

1. Enter 
```java
ssh-keygen -t rsa -b 4096 -C "youremailaddress@gmail.com"
```
2. Enter filename to save generated key (without any extension, it will be added afterward)
3. Enter passphrase if neccessary

# Add your key to ssh-agent

1. Verify whether ssh agent is running 
```java
eval $(ssh-agent -s)`
```
2. Add key 
```java
ssh-add ~/.ssh/<yourkey> (without extension)
``` 

# Add config file (necessary for multiple ssh key for multiple Version Control System)

1. Add new file if it's not existed at location: 
```java 
~/.ssh/config
```
2. Edit `config` file with content
```java
   Host github.com
    IdentityFile ~/.ssh/<yourkey> (without extension)
```
3. Remember add the indent at the second line


# Add public SSH key to Github account

1. Copy public SSH key
2. Paste into SSH setting page of github: 
```java
https://github.com/settings/keys
```
3. Create

# Check the connection

Enter command 
```java 
ssh -T git@github.com
```
if you was request to add this host to known-hosts file, type yes to accept.
if you see the line "Hi <user>! You've successfully authenticated, but ...." => OK

