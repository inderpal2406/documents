## Enable root login in ubuntu GUI on login screen.
[Online ink](https://www.youtube.com/watch?v=hlVMT3Ap8o4)

## Steps
1. Set root password.<br>
   `sudo passwd`
2. `sudo apt update`
3. `sudo apt install lightdm` <br>
   This will install a new display manager for our xterm terminal emulator for our X Window System desktop environment. We have other desktop envs such as GNOME.
4. `sudo vi /etc/lightdm.conf` <br>
   ```
   [SeatDefaults]
   greeter-session=unity-greeter
   user-session=ubuntu
   greeter-show-manual-login=true
   ```
5. `sudo reboot` or `sudo shutdown -r 0`

Now, we'll get `login` option on screen wherein we can enter `root` username and password and ogin as root. But we get another `tty` problem due to which we cannot get terminal in root login. This can be solved by further steps. We're not working on these further steps as of now. However,to get a root shell, we have the option of booting ubuntu in recovery mode \(by pressing left shift key multiple times on boot\) and entering the root bash shell.
