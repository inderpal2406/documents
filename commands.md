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
