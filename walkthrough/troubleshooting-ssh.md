# Troubleshooting SSH

## Connecting to EC2 instance

### Problem

```
$ ssh -i ~/KEYS/my-key.pem ec2-user@ec2-xxx-xxx-xxx-xxx.compute-1.amazonaws.com

The authenticity of host 'xxx.xxx.xxx.xxx (xxx.xxx.xxx.xxx)' can't be established.
ECDSA key fingerprint is SHA256:5wxVn/uYL6XgYAYEvrvILvRxbLleXzcqqUbNh7MCQ4o.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'xxx.xxx.xxx.xxx' (ECDSA) to the list of known hosts.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0664 for '~/KEYS/my-key.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "~/KEYS/my-key.pem": bad permissions
```

### Solution

```
$ chmod 400 ~/KEYS/my-key.pem
```

### Verification

```
$ ssh -i ~/KEYS/my-key.pem ec2-user@ec2-xxx-xxx-xxx-xxx.compute-1.amazonaws.com
```

### Sources

* Right click EC2 instance in Dashboard; click [`Connect`]; get instructions.
* https://unix.stackexchange.com/questions/115838/what-is-the-right-file-permission-for-a-pem-file-to-ssh-and-scp
