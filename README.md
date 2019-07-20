# Hackintosh-Razer-Blade-Basic
How to fix Razer Blade 15 basic model's trackpad.

##Guide for advance model
https://www.tonymacx86.com/threads/guide-razer-blade-15-2018-detailed-install-guide-high-sierra-10-13-6-17g2208-17g5019.264017/

##Trackpad fix
Ben Raz @ben9923 14:04
@incfex Remove VoodooI2CELAN, install VoodooI2CHID
Replace your SSDT-XOSI with this one (compile, of course):
https://github.com/RehabMan/OS-X-Clover-Laptop-Config/blob/master/hotpatch/SSDT-XOSI.dsl
In your DSDT replace If (USTP) with If (One), you didn't do that...
Patch _CRS so it only has this inside:
Return (ConcatenateResTemplate (I2CM (I2CX, BADR, SPED), SBFG))
Your ELAN0406 is under I2C0.

Add battery patch to show trackpad.

##Nvidia Driver not loading
check inject nvidia web drivier in clover settings.
