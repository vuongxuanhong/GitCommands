# Useful Git Commands

Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and password at each visit.

# Check for existing SSH keys

1. Open git bash
2. Enter `ls -al ~/.ssh` to see existing SSH keys are present.
   If you see any file with .pub suffix, it is an SSH key

# Generate a new SSH key

1. Enter `ssh-keygen -t rsa -b 4096 -C "youremailaddress@gmail.com"
2. Enter filename to save generated key (without any extension, it will be added afterward)
3. Enter passphrase if neccessary

# Add your key to ssh-agent

1. Verify whether ssh agent is running `eval $(ssh-agent -s)`
2. Add key `ssh-add ~/.ssh/<yourkey>` 

# Add config file (necessary for multiple ssh key for multiple Version Control System)

1. Add new file if it's not existed at location: ~/.ssh/config
2. Edit `config` file with content
   Host github.com
    IdentityFile ~/.ssh/<yourkey>
3. Remember add the indent at the second line


# Add public SSH key to Github account

1. Copy public SSH key
2. Paste into SSH setting page of github: `https://github.com/settings/keys`
3. Create

# Check the connection

Enter command `ssh -T git@github.com`
if you see the line "Hi <user>! You've successfully authenticated, but ...." => OK

