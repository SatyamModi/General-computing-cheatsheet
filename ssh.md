# For ssh related issues

Hi! welcome here you will find all the solution for the issues related to ssh.

### How to generate public-private key pair for passwordless ssh into a server?

For this, first generate a public-private key pair on your local system. 
Use `ssh-keygen -t rsa -b  4096` in the `~/.ssh` directory. This will generate two keys mainly `id_rsa` and `id_rsa.pub`. Here, id_rsa is your private key and .pub is your public key. First ssh to the server and then copy the public key in its `.ssh` directory and also into its `authorized_keys` file. Now you are good to go. 

You can also generate the keys with some specific name. Just pass the `-f <path/name>` in the `ssh-keygen` command. 

### How to access your friend's server using these generated public/private key pair?

For this, the steps are similiar. Copy your public key to your friend's server in the `authorized_keys` file and then in your local ssh config file, write this. 
```
Host <Any name>
HostName hpc.iitd.ac.in
User <username>
IdentityFile ~/.ssh/id_rsa
IdentitiesOnly yes 
```
