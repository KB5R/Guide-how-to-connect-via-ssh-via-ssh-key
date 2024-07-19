# Guide-how-to-connect-via-ssh-via-ssh-key
# Гайд как подключить по ssh через ssh-key

## Буду использовать 
* Windows
* Ubuntu
### 1. Буду подключатся с Windows к Ubuntu аналогично с Ubuntu к Windows
### 2. Открываем терминал Windows и переходим в любую удобную вам директорию
### 3. Когда перешли в директорию в терминале пишем 
```sh
ssh-keygen
```
#### 3.1 Придумываем имя файлу например `mykey`, далее везде Enter
#### 3.2 После данных операций в нашей директории появится 2 файла `mykey` и `mykey.pub`
### 4. Открыть файл или перекинуть данные файла `mykey.pub`
### 5. Данные необходимо перекинуть в данную директорию 
```
/home/k8s/.ssh
```
### В файл `authorized_keys`
### 6. Находясь в директорию в которой создавали ssh ключи, надо выполнить
```
ssh -i .\mykey user@***.***.***.***
```
* И чудеса мы подключились без пароля, при помощи ssh key
### 7. Но это ведь не удобно, всегда надо подключатся при помощи `-i .\mykey`
### Что бы исправить это надо выполнить

### 8. Надо взять содержимое файла `mykey` и скопировать или переименовать в
### `id_rsa`, вообщем должен получится файл `id_rsa` с содержимым `mykey` 
### 9. Далее надо переместить этот файл в
## `Для Windows`
```
C:\Users\User\.ssh\id_rsa
```
---
## `Для Linux`
```
/home/k8s/.ssh/id_rsa
```
### 10 Дополнительной требуется на локальной машине к которой вы хотите подключится надо в данной дериктории создать файл `authorized_keys` и наполнить его содержимым файлв mykey.pub и все
```
/home/user/.ssh/authorized_keys
```
### Ниже будет команда для быстрого наполнение файла `authorized_keys` поменяйте на свои значения
```
bash -c 'cat <<EOF > /home/medexpert/.ssh/authorized_keys
ssh-rsa /*****************************************************************r0lh3q1kDsLrAF5Y3IlemyVcknkVboi65Vo5Z4wzQb9OJ7Ak2kiLU8I2yfhWerrdDUTcRZjx1+bZfwVkOZkDvILqsBACJ6+74kY2CGLy8eFfJOS0KPXWZaiap/wrIHGa179rFSWXmghAE/ERgzG2aAamPz6Ty0utAnxgTRPpFTpOH0nKzMgujH5bYwy8DGSSs2z5tdE1j+o7K4s7PGF82YfDAbhtODF8fsqusKyNGct1NAatW5UTFQScBxJ1Ct10= kb5r@DESKTOP-VP10TEQ
EOF'

```
### 11. Пробуeм подключится 
```
ssh user@***.***.***.***
```
### И магия, все получилось
---
# Instructions in English

# Guide how to connect via ssh via ssh-key

## I will use 
* Windows
* Ubuntu
### 1. I will connect from Windows to Ubuntu in the same way as from Ubuntu to Windows
### 2. Open the Windows terminal and go to any directory convenient for you
### 3. When we moved to the directory in the terminal, we write 
``sh
ssh-keygen
``
#### 3.1 We come up with a file name for example `mykey`, then Enter everywhere
#### 3.2 After these operations, 2 files `mykey` and `mykey.pub` will appear in our directory
### 4. Open a file or transfer the data of the `mykey.pub` file
### 5. The data must be transferred to this directory 
``
/home/k8s/.ssh
``
### To the `authorized_keys` file
### 6. Being in the directory where ssh keys were created, you need to run
``
ssh -i .\mykey user@***.***.***.***
``
* And miraculously, we connected without a password, using ssh key
### 7. But it's not convenient, you always need to connect using `-i .\mykey`
### To fix this, you need to do

### 8. Take the contents of the `mykey` file and copy or rename it to
### `id_rsa`, in general, you should get an `id_rsa' file with the contents of `mykey` 
### 9. Next, you need to move this file to
## `For Windows`
``
C:\Users\User\.ssh\id_rsa
``
---
## `For Linux`
```
/home/k8s/.ssh/id_rsa
```
### 10. Trying to connect 
``
ssh user@***.***.***.***
``
### And the magic, everything worked out
