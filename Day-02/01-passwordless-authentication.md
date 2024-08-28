# How to setup Passwordless Authentication

## EC2 Instances

### Using Public Key
1. Create a key pair to be reference later on e.g `/keys/DevOpsForJesus.pem`
2. Generate a ssh key by running the `ssh-keygen` command
3. Run the command below
```
ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
```

- ssh-copy-id: This is the command used to copy your public key to a remote machine.
- -f: This flag forces the copying of keys, which can be useful if you have keys already set up and want to overwrite them.
- "-o IdentityFile <PATH TO PEM FILE>": This option specifies the identity file (private key) to use for the connection. The -o flag passes this option to the underlying ssh command.
- ubuntu@<INSTANCE-IP>: This is the username (ubuntu) and the IP address of the remote server you want to access.

### Using Password 

- Go to the file `/etc/ssh/sshd_config.d/60-cloudimg-settings.conf`
- Update `PasswordAuthentication yes`
- Restart SSH -> `sudo systemctl restart ssh`
- Create a password for the user (ubuntu) - `sudo passwd ubuntu`
- Connect to the server using the command below
```
ssh-copy-id ubuntu@<INSTANCE-PUBLIC-IP>
```
