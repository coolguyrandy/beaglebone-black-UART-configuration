# beaglebone-black-UART-configuration
This repository details how to enable UART pins on BeagleBone Black running a provided BBB Debian 11.11 image 

# Steps

Add the following line to /boot/uEnv.txt to enable UART4 (UART Pins P9_11 and P9_13 on my beaglebone black):

"uboot_overlay_addr1=BB-UART4-00A0.dtbo"

Also, make sure to give the proper permissions to the interface:

"sudo chmod +rw /dev/ttyS4"

# IMPORTANT

Older BBB debian images use the following command:

config-pin <expansion_header>-<pin_number> <desired_mode> 

Despite being deprecated, config-pin still runs and produces the expected output on Debian 11 (even though it does not actually work). Be forewarned. 

I did quite a bit of digging online but could not determine exactly when config-pin was deprecated. I can only say for certain that it does not seem to work properly on the BBB Debian 11 image. Also please note that there may be some other way of configuring the pins that I did not cover here depending on the BBB image you are using. If neither method works, my suggestion is to do some digging on the beaglebone forums. They seem to have changed this configuration numerous times over the years, so be prepared to sift through much outdated/irrelevant information before finding something useful.
