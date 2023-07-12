# script-test
This is only a script test project.

## Preconfigured `/boot/config.txt`
To install pwm fan, first add `dtoverlay=pwm-2chan` to `/boot/config.txt` under `[all]` and reboot:
<pre>
sudo vi /boot/config.txt
</pre>
Save & exit.
<pre>
sudo reboot
</pre>
Reboot this device.

## Clone the script
<pre>
git clone https://github.com/geekworm-com/script-test

cd script-test
chmod +x *.sh
chown root:root *.sh
</pre>

## Prepair the `x-c1-fan` service
<pre>
sudo cp -f ./x-c1-fan.sh                /usr/local/bin/
sudo cp -f ./x-c1-fan.service           /lib/systemd/system
sudo systemctl daemon-reload
sudo systemctl enable x-c1-fan
sudo systemctl start x-c1-fan
</pre>

## Prepair the `x-c1-pwr` service
<pre>
sudo cp -f ./x-c1-pwr.sh                /usr/local/bin/
sudo cp -f x-c1-pwr.service             /lib/systemd/system
sudo systemctl daemon-reload
sudo systemctl enable x-c1-pwr
sudo systemctl start x-c1-pwr
</pre>

## Prepair software shutdown
<pre>
sudo cp -f ./x-c1-softsd.sh             /usr/local/bin/
</pre>
Create a alias `xoff` command to execute the software shutdown
<pre>
echo "alias xoff='sudo /usr/local/bin/x-c1-softsd.sh'" >>   ~/.bashrc
source ~/.bashrc
</pre>
Then you can run `xoff` to execute software shutdown.
