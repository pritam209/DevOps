# How to generate and add SSH Key in ubuntu instance

# Follow this 2 steps:

- Step 1: Generate SSH Key

```bash
ssh-keygen -t rsa
```

- Step 2: Add your generated public key into authorized_keys file, inside SSH Folder of Ubuntu

Note: edit authorized_keys file - ( copy & paste your public key)

```bash
cd ~/.ssh
vim authorized_keys 
```

