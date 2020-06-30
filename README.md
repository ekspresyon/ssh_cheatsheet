# ssh Commands
I can't remember a lot of the ssh commands that I use for some reason. So I'm just going to stash this reference here.  

### Generate an SSH Key pair

    ssh-keygen

This command will generate a public and private rsa key pair.  
There will be questions. Answer them. If you don't know how, you probably need to read more stuff on the matter in this [ssh-keygen reference](https://www.ssh.com/ssh/keygen)

### Copy the public key to a server

    ssh-copy-id -i ~/.ssh/the-key.pub username@host

Replace "the-key" with the actual name of the key.  
Make sure to use the public version of "the-key" which is marked as "the-key.pub".  
In case of failure visit this [ssh-copy-id reference](https://www.ssh.com/ssh/copy-id) site.

### Remove Host key from client computer

    ssh-keygen -R "hostname"

This command will remove the specific host key of the named host. If you used IP adress and host names interchangeably, you would have to run the command for each 

### Delete all host keys from client computer

    rm -f .ssh/known_hosts

This will delete the known host file and recreate it. All host keys will we removed.