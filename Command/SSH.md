# With key

Перед использованием изменить настройки безобасности ключа. Свойства-Безопасность-Дополнительно-Отключить наследование.
Запуска командной строки/powershell от администратора!

`ssh -i "F:/Documents/Exadel/SshKey/Task4VM_key.pem" azureuser@13.81.111.118`

# Without key

`ssh testadmin@20.126.13.137`

# WARNING: UNPROTECTED PRIVATE KEY FILE!   

`chmod 600 ec2-private-key.pem`


# Uploading a file from a local computer to a remote one:

`scp /path/to/local/file username@hostname:/path/to/remote/file`

Example:

`scp /home/testadmin/nginx-1.22.0-1.el7.ngx.x86_64.rpm testadmin@10.0.2.4:/home/testadmin`

# Downloading a file from a remote system to your computer:

`scp username@hostname:/path/to/remote/file /path/to/local/file`