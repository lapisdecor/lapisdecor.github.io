---
layout: post
title:  "Ubuntu 20.04 on a Acer Aspire A315-55G"
---


# How to install Ubuntu 20.04 on a Acer Aspire A315-55G

I bougth a new laptop, the Acer Aspire A315-55G-KL for 549€. It arrived quickly (1 day) but as soon as I turn it on I was faced not with the Linux I expected but only with EFI shell.

Not knowing anything about EFI shell, I just put a USB drive with Ubuntu 19.04 on it and boot it, and soon I discovered two things:
- the SSD was not visible
- 19.04 behaved strangely (MX230 graphics probably)

So I decided to try out 20.04 beta. It worked well but the SSD was still not visible. But now it's working :-) here's what you have to do:

- press F2 when you see the acer logo. This will take to the BIOS
- see for yourself that the system is probably using optane memory in SATA mode.
- set an admin password to change some advanced stuff on your BIOS
- open the hidden sata commands by pressing CTRL + S
- change the SATA mode (the disk will now be recognized by Ubuntu)
- reboot with the USB drive put in
- install Ubuntu (I erased the entire disk and installed Ubuntu)
- enjoy :-)

That's it, I now have a fully functional Acer laptop.