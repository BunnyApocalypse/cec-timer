# cec-timer

cec-timer is a set of systemd timers and services that will turn off and on cec controlled TVs at specific times, it was designed to be used on Fedora using a Raspberry Pi 3 and uses cec-ctl to control the cec device.

## How to use

* Enable cec on your TV, it may go by different names depending on the vendor, a list of names and a guide can be found [here](https://www.howtogeek.com/207186/how-to-enable-hdmi-cec-on-your-tv-and-why-you-should)
* Enable the systemd timers and initialization service `systemctl enable cec-on.timer cec-off.timer cec-initialize.service` 
* Either reboot or `systemctl start cec-initialize.service` and the tv should turn on and off at the times specified by the timer files

## Configuration

* Edit the [timer files](https://wiki.archlinux.org/index.php/Systemd/Timers) (located at `/usr/lib/systemd/system/cec-on/off.timer`) for your desired days and times to turn the monitor on and off. 

* If you are using a different cec control device than the raspberry pi 3, you may need to configure the `cec-initialize.service` for your device.

## Usecases

* Turning on and off an office dashboard TV at specific times so that it doesn't waste energy running when people aren't around
