```shell

 disbro@Dis-Bro  ~  sudo iptables -L
[sudo] password for disbro:
Chain INPUT (policy ACCEPT)
target     prot opt source               destination

Chain FORWARD (policy ACCEPT)
target     prot opt source               destination

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination
 disbro@Dis-Bro  ~  # Все пусто, никаких правил нет
 disbro@Dis-Bro  ~  sudo iptables -P INPUT DROP
 disbro@Dis-Bro  ~  sudo iptables -A INPUT -i eth0 -p tcp --dport 80 -j ACCEPT
 disbro@Dis-Bro  ~  sudo iptables -A INPUT -i eth0 -p tcp --dport 22 -j ACCEPT
 disbro@Dis-Bro  ~  sudo iptables -L
Chain INPUT (policy DROP)
target     prot opt source               destination
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:http
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:ssh

Chain FORWARD (policy ACCEPT)
target     prot opt source               destination

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination
 disbro@Dis-Bro  ~  # Политика поменялась на DROP, добавились два правила
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~ 
  disbro@Dis-Bro  ~  sudo iptables -t nat -I PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
 disbro@Dis-Bro  ~  sudo iptables -L
Chain INPUT (policy DROP)
target     prot opt source               destination
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:http
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:ssh

Chain FORWARD (policy ACCEPT)
target     prot opt source               destination

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination
 disbro@Dis-Bro  ~  sudo iptables -L -t nat
Chain PREROUTING (policy ACCEPT)
target     prot opt source               destination
REDIRECT   tcp  --  anywhere             anywhere             tcp dpt:http redir ports 8080

Chain INPUT (policy ACCEPT)
target     prot opt source               destination

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination

Chain POSTROUTING (policy ACCEPT)
target     prot opt source               destination
 disbro@Dis-Bro  ~  # Правило применилось и пробрасывает на правильный порт
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~  sudo iptables -A INPUT -p tcp -s 3.4.5.6 -j DROP
 disbro@Dis-Bro  ~  sudo iptables -L
Chain INPUT (policy DROP)
target     prot opt source               destination
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:http
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:ssh
DROP       tcp  --  3.4.5.6              anywhere

Chain FORWARD (policy ACCEPT)
target     prot opt source               destination

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination
 disbro@Dis-Bro  ~  # Правило применилось и отображается в списке
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~ 
 disbro@Dis-Bro  ~  mc
 disbro@Dis-Bro  ~  ps aux | tail
root         585  0.0  0.1   5756  4240 pts/1    Ss   17:52   0:00 /bin/login -f
disbro       774  0.0  0.3  19108  9680 ?        Ss   17:52   0:00 /lib/systemd/systemd --user
disbro       776  0.0  0.1 171732  3760 ?        S    17:52   0:00 (sd-pam)
disbro       788  0.0  0.4 278076 14136 ?        Ssl  17:52   0:00 /usr/bin/pulseaudio --daemonize=no --log-target=journal
disbro       789  0.0  0.3 766860  9708 pts/1    S+   17:52   0:00 -fish
disbro       839  0.0  0.1   7116  4008 ?        Ss   17:52   0:00 /usr/bin/dbus-daemon --session --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
disbro      1611  0.0  0.3  20076  8944 pts/0    S+   18:02   0:00 mc
disbro      1613  1.3  0.2 308360  8552 pts/2    Ssl  18:02   0:01 /usr/bin/fish
disbro      1698  0.0  0.1   9208  3192 pts/2    R+   18:03   0:00 ps aux
disbro      1699  0.0  0.0   5832   584 pts/2    S+   18:03   0:00 tail
 disbro@Dis-Bro  ~  ps aux | grep mc
disbro      1611  0.0  0.3  20076  8944 pts/0    S+   18:02   0:00 mc
disbro      1723  0.0  0.0   6620   720 pts/2    S+   18:04   0:00 grep --color=auto mc
 disbro@Dis-Bro  ~  kill -s 9 1611
fish: Job 1, 'mc' terminated by signal SIGKILL (Forced quit)
                                                            ⏎
 ✘  disbro@Dis-Bro  ~  ps aux | grep mc
disbro      1820  0.0  0.0   6620   712 pts/0    S+   18:05   0:00 grep --color=auto mc
 disbro@Dis-Bro  ~  # Теперь процесса mc нет в списке (выше был показан только grep)

```