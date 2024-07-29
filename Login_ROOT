# Логинимся по SSH под ROOT
```bash
passwd root
```
## Указываем пароль `root`
```bash
nano /etc/ssh/sshd_config
```
## Меняяем строку как на примере
```bash
PermitRootLogin yes
```
## Рестартим службы
```bash
systemctl restart ssh && systemctl restart sshd
```
## Проверяем
```bash
ssh root@ip
```
