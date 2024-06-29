# How to copy file form Local Machine to Virtual  Machine (Vice Versa)

- Using this command to copy file from Local Machine to Virtual  Machine

```bash
scp -i path/to/file.pem ./file.txt ubuntu@server_ip:/home/ubuntu
```

- Using this command to copy file from Virtual Machine to Local Machine

Note : path/to/local(use - './' to copy file in same folder)

```bash
scp -i path/to/file.pem ubuntu@server_ip:/home/ubuntu/file.txt ./
```
