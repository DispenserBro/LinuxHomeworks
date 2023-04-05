```shell
 disbro@Dis-Bro  main  touch file1 file2
 disbro@Dis-Bro  main  chmod u=rw,g=rw,o=r file1
 disbro@Dis-Bro  main  chmod 600 file2
 disbro@Dis-Bro  main  ll
total 8
drwxr-xr-x  2 disbro disbro 4096 апр  5 17:54 ./
drwxr-xr-x 14 disbro disbro 4096 апр  3 20:14 ../
-rw-rw-r--  1 disbro disbro    0 апр  5 17:57 file1
-rw-------  1 disbro disbro    0 апр  5 17:57 file2
 disbro@Dis-Bro  main  sudo chown -R disbro:www-data .
[sudo] password for disbro:
 disbro@Dis-Bro  main  ll
total 8
drwxr-xr-x  2 disbro www-data 4096 апр  5 17:54 ./
drwxr-xr-x 14 disbro disbro   4096 апр  3 20:14 ../
-rw-rw-r--  1 disbro www-data    0 апр  5 17:57 file1
-rw-------  1 disbro www-data    0 апр  5 17:57 file2
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main  sudo useradd -m -d /home/testuser testuser
 disbro@Dis-Bro  main  sudo adduser testuser2
Adding user 'testuser2' ...
Adding new group 'testuser2' (1003) ...
Adding new user 'testuser2' (1002) with group 'testuser2' ...
Creating home directory '/home/testuser2' ...
Copying files from '/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for testuser2
Enter the new value, or press ENTER for the default
        Full Name []: John
        Room Number []: Doe
        Work Phone []: +0
        Home Phone []: +1
        Other []:
Is the information correct? [Y/n] y
 disbro@Dis-Bro  main  sudo userdel testuser -r
userdel: testuser mail spool (/var/mail/testuser) not found
 disbro@Dis-Bro  main  ll /home
total 16
drwxr-xr-x  4 root      root      4096 апр  5 18:05 ./
drwxr-xr-x 23 root      root      4096 апр  5 17:53 ../
drwxr-xr-x 14 disbro    disbro    4096 апр  3 20:14 disbro/
drwxr-xr-x  3 testuser2 testuser2 4096 апр  5 18:04 testuser2/
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main  sudo groupadd group1
 disbro@Dis-Bro  main  sudo addgroup group2
Adding group 'group2' (GID 1002) ...
Done.
 disbro@Dis-Bro  main  sudo usermod -g group1 testuser2
 disbro@Dis-Bro  main  id testuser2
uid=1002(testuser2) gid=1004(group1) groups=1004(group1)
 disbro@Dis-Bro  main  sudo usermod -aG group2 testuser2
 disbro@Dis-Bro  main  id testuser2
uid=1002(testuser2) gid=1004(group1) groups=1004(group1),1002(group2)
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main 
 disbro@Dis-Bro  main  sudo usermod -aG sudo testuser2
 disbro@Dis-Bro  main  su testuser2
Password:
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

testuser2@Dis-Bro:/home/disbro/main$ sudo whoami
[sudo] password for testuser2:
root
testuser2@Dis-Bro:/home/disbro/main$ sudo visudo
testuser2@Dis-Bro:/home/disbro/main$ # Добавил строку testuser2 ALL=(ALL) NOPASSWD:ALL
testuser2@Dis-Bro:/home/disbro/main$ exit
exit
 disbro@Dis-Bro  main  su testuser2
Password:
testuser2@Dis-Bro:/home/disbro/main$ sudo whoami
root
```