kernel version: `uname -r` <br>
output: 4.15.0-60-generic <br>
4: kernel version <br>
15: major revision <br>
0: minor revision <br>
60: bug fix <br>
generic: desktop version of ubuntu \(will be "server" in case of server version\)

`sudo usermod -a -G docker username` <br>
This will add user to supplementary groups, otherwise all other secondary group membership is removed and user is assigned new secondary group.

`sudo apt list --installed` <br>
This will list all installed packages in ubuntu. We can grep our desired package further.

`sudo apt list --upgradable` <br>
This will list packages for which new updates/upgrades are available.

`sudo apt update` <br>
This will update APT repositories.

`sudo apt upgrade` <br>
This will update packages to available newer versions.

`echo ${!i}` Indirect variable substitution in bash.<br>
[Click here](https://stackoverflow.com/questions/57957477/how-to-perform-variable-substitution-in-bash-scripting?noredirect=1#comment102327282_57957477) for more info.

`echo "PFA the report" | mail -s "Status mail" -A /path/of/attachment xxx@x.com,yyy@y.com` <br>
Command to send mail from Linux machine with an attachments to multiple mail IDs.

To convert files from windows format to linux and vice versa. <br>
`unix2dos unix.txt windows.txt` <br>
`dos2unix windows.txt unix.txt` <br>
`awk '{ sub("\r$", ""); print }' windows.txt > unix.txt` <br>
`awk 'sub("$", "\r")' unix.txt > windows.txt` <br>

To copy all files including hidden files and directories using `cp` command: <br>
`cp -r /etc/skel /home/user` <br>
Note that /home/user must not exist otherwise it'll create /home/user/skel <br>

`hostname` : reveals the hostname <br>
`hostname -f` : reveals the FQDN <br>
`hostname -i` : reveals the IP address of the hostname
