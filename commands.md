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

To fetch all public IPs in azure <br>
`az network public-ip list -o table > Azure_Public_IP.csv`

ANSI escape quotes for different colors in bash. <br>
Black        0;30     Dark Gray     1;30
Red          0;31     Light Red     1;31
Green        0;32     Light Green   1;32
Brown/Orange 0;33     Yellow        1;33
Blue         0;34     Light Blue    1;34
Purple       0;35     Light Purple  1;35
Cyan         0;36     Light Cyan    1;36
Light Gray   0;37     White         1;37

And then use them like this in our script:
```
RED='\033[0;31m'
NC='\033[0m' # No Color
printf "I ${RED}love${NC} Stack Overflow\n"
```

If we are using the echo command, be sure to use the -e flag to allow backslash escapes.
`echo -e "I ${RED}love${NC} Stack Overflow"`

How to negate a condition in if in bash? <br>
```
if ! [[ -d /root/backup ]]
then
    mkdir /root/backup
fi
```
Above code will test if /root/backup exists or not and will create it if it doesn't exists.

`tar -cvf test.tar test1 test2` <br>
`tar -cvf dir.tar ./dir/` <br>
`tar -cvzf test.tar.gz test1 test2` <br>
`tar -xvf test.tar` <br>
`tar -xvf test.tar -C ./unpack/` (provided \./unpack/ exists) <br>
`tar -xvf test.tar.gz` <br>
If we extract and a new directory get created after extract, then it means that while zipping it, the directory was zipped and not individual files. <br>
`tar -czf $BACKUP_DIR/gitlab-$CURRENT_VERSION.tar.gz gitlab-runner > /dev/null 2>&1` creates error of redirection. So, <br>
`tar -czf $BACKUP_DIR/gitlab-$CURRENT_VERSION.tar.gz gitlab-runner 2>/dev/null 1>/dev/null`

**curl**

`curl -L --output /path_of_download https://link-to-download > /dev/null 2>&1` <br>
-L: to follow redirections (if any) in webpages. <br>
--output: to specify download path. We need to specify a name for the file in the download path. The downloaded file will have this name. If we don't specify any name or just specify the directory name in which we want to downoad, then downoaded file will fail. <br>
`curl -O https://bootstrap.pypa.io/get-pip.py` <br>
-O: write ouput to a local file named like the remote file we get. <br>
A combination of both -O --output doesn't work to download remote file with same remote name but in a different directory. <br>
`curl -u user:password https://url` <br>
Above command will specify user and password to access the url. However, this will make the password visible when we view the history of commands. <br>
`curl -u user https://url` <br>
By specifying only user, we'll be prompted to enter password on terminal and the password won't be recorded in history. While we enter password, it is invisible as it is always in Unix prompt.

**git**

To clone a single remote branch into local repo. <br>
`git clone --single-branch --branch <branch_name> git@github.com:/shady/repo.git`

[Guide for .gitignore file](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)
