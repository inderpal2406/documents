kernel version: `uname -r` <br>
output: 4.15.0-60-generic <br>
4: kernel version <br>
15: major revision <br>
0: minor revision <br>
60: bug fix <br>
generic: desktop version of ubuntu \(will be "server" in case of server version\)

`sudo usermod -a -G docker username`
This will add user to supplementary groups, otherwise all other secondary group membership is removed and user is assigned new secondary group.
