# script-test
This is only a script test project.

To install, first add dtoverlay=pwm-2chan to /boot/config.txt under [all] and reboot:
> sudo vi /boot/config.txt
Then save&reboot.

> git clone https://github.com/geekworm-com/script-test

> sudo cp -f x-c1-fan.sh                /usr/local/bin
> sudo chmod +x /usr/local/bin/x-c1-fan.sh
> sudo cp -f x-c1-fan.service           /lib/systemd/system
> sudo systemctl daemon-reload
> sudo systemctl enable x-c1-fan
> sudo systemctl start x-c1-fan

sudo cp -f ./x-c1-pwr.sh                /usr/local/bin/pwr.sh
sudo cp -f ./x-c1-softsd.sh             /usr/local/bin/softsd.sh

sudo cp -f x-c1-pwr.service             /lib/systemd/system
sudo systemctl daemon-reload
sudo systemctl enable x-c1-pwr
sudo systemctl start x-c1-pwr
