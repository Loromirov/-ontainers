Задание 1:
1) запустить контейнер с ubuntu, используя механизм LXC
2) ограничить контейнер 256 Мб ОЗУ и проверить, что ограничение работает

apt-get install lxc debootstrap bridge-utils lxc-templates
apt-get install lxd-installer
lxd init
lxc storage list
И создаем контейнер
lxc-create -n test12 -t ubuntu -f /usr/share/doc/lxc/example/lxc-veth.conf
![2023-08-20_21-43-38](https://github.com/Loromirov/-ontainers/assets/117039676/7c9e8e83-a930-4b79-a5da-e30ce58aca94)

nano /var/lib/lxc/test123/config-открываем
и дальше появляется надпись - 
![2023-08-20_22-05-23](https://github.com/Loromirov/-ontainers/assets/117039676/fedf05cd-f148-4129-a69e-277aaa845301)

пробовал переустанавливать все с начала, но все равно выходит так. Подскажите, как исправить?
