# PIA on fedora 20

**Tested on fedora 20 with pia v81**

PIA for linux is not supposed to work for fedora but you can get around its installer.

- First step is to download the [installer](https://www.privateinternetaccess.com/installer/download_installer_linux).
- Extract it
- Run it as a normal user and when it asks you for your password don't fill it
- Open a new shell and type `ls -a`, you will see a `.pia-install.random_number` folder
- `cd` into the folder and `cd` again to `installer_linux`
- `cp -r ~/.pia-manager/data/ deploy_files/` this step is necessary otherwise the installer will fail  
- `nano installer.sh` and modify the `sudo apt-get install -y ...` line by `sudo dnf install -y GConf2 net-tools libappindicator libXScrnSaver`
- `./installer.sh`
- kill the first shell you opened
