---
layout: post
title:  "Paring Raboo Blueooth Mouse with Ubuntu 15.10"
date:   2015-03-18 10:36:29
categories: Bluetooth,Ubuntu 
---

Yesterday, I purchased a Rapoo Bluetooth Mouse 6010B and tried to work with my Ubuntu 15.10. Sadly, it can be paried, but ubuntu told me "Connection failed". As a programmer knowning little about bluetooth, I used `hcidump` to capture a log and found nothing. Ubuntu seems pair with mouse successful and after a bunch of SDP negotitation, disconnect with mouse with no obvious reason. 

After that, I tried the mouse with my android phone, everything works perfect. 

After Google a lot, someone mentions Ubuntu 15.10 has some problem of bluetooth with its Bluetooth GUI, suggests that command line may work. So I tried `bluetoothctl`:

`
scan on
#Found the mac with your mouse here
scan off
pair 00:11:xx:xx  #Pair with your mouse
connect 00:11:xx:xx 
`

Everything goes OK. After that, I tried powerdown/poweron bluetooth mouse, everythings is ok. 



