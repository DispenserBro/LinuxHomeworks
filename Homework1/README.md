// Это powerline-символы, поэтому prompt некрасиво выглядит
// Две кавычки (`''s`), чтобы нормально отображалось в сноске

```shell
  ~    ssh -p 2022 disbro@localhost
disbro@localhost''s password:
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.15.90.1-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Пн 27 мар 2023 21:58:07 MSK

  System load:  0.08               Processes:             11
  Usage of /:   2.0% of 250.92GB   Users logged in:       0
  Memory usage: 14%                IPv4 address for eth0: 172.31.18.94
  Swap usage:   0%


Расширенное поддержание безопасности (ESM) для Applications выключено.

0 обновлений может быть применено немедленно.

Включите ESM Apps для получения дополнительных будущих обновлений безопасности.
Смотрите https://ubuntu.com/esm или выполните: sudo pro status

New release '22.04.2 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Mon Mar 27 20:45:52 2023 from 127.0.0.1
 disbro@Dis-Bro  ~  sudo apt update; sudo apt upgrade
[sudo] password for disbro:
Пол:1 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Сущ:2 http://ppa.launchpad.net/deadsnakes/ppa/ubuntu focal InRelease
Сущ:3 http://archive.ubuntu.com/ubuntu focal InRelease
Сущ:4 http://ppa.launchpad.net/fish-shell/release-3/ubuntu focal InRelease
Сущ:5 http://packages.microsoft.com/repos/code stable InRelease
Пол:6 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Сущ:7 http://ppa.launchpad.net/neovim-ppa/stable/ubuntu focal InRelease
Сущ:8 https://packages.microsoft.com/repos/vscode stable InRelease
Сущ:9 http://ppa.launchpad.net/neovim-ppa/unstable/ubuntu focal InRelease
Пол:10 http://archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Получено 336 kB за 2с (216 kB/s)
Чтение списков пакетов… Готово
Построение дерева зависимостей
Чтение информации о состоянии… Готово
Все пакеты имеют последние версии.
Чтение списков пакетов… Готово
Построение дерева зависимостей
Чтение информации о состоянии… Готово
Расчёт обновлений… Готово
Обновлено 0 пакетов, установлено 0 новых пакетов, для удаления отмечено 0 пакетов, и 0 пакетов не обновлено.
 disbro@Dis-Bro  ~  uname -a
Linux Dis-Bro 5.15.90.1-microsoft-standard-WSL2 #1 SMP Fri Jan 27 02:56:13 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
 disbro@Dis-Bro  ~  lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 20.04.6 LTS
Release:        20.04
Codename:       focal
 disbro@Dis-Bro  ~  sudo apt install mc
Чтение списков пакетов… Готово
Построение дерева зависимостей
Чтение информации о состоянии… Готово
Уже установлен пакет mc самой новой версии (3:4.8.24-2ubuntu1).
Обновлено 0 пакетов, установлено 0 новых пакетов, для удаления отмечено 0 пакетов, и 0 пакетов не обновлено.
 disbro@Dis-Bro  ~  mc
```