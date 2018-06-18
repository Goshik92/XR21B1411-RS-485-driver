# XR21B1411 driver for Orange Pi Zero with forced RS-485 mode

This driver is based on the original driver from [Exar](https://www.exar.com/content/document.ashx?id=21652) (version 1A for Linux 2.6.18 to 3.4.x). Two amendments were made to the original version:
* RS-485 mode was forced
* The following compilation errors were fixed:
```
xr_usb_serial_common.c: In function ‘xr_usb_serial_init’:
xr_usb_serial_common.c:1565:18: error: implicit declaration of function ‘usb_serial_register’ [-Werror=implicit-function-declaration]
         retval = usb_serial_register(&xr_usb_serial_device);
                  ^
xr_usb_serial_common.c:1579:9: error: implicit declaration of function ‘usb_serial_deregister’ [-Werror=implicit-function-declaration]
         usb_serial_deregister(&xr_usb_serial_device);
         ^
```

If you do not need the RS-485 mode, checkout [RS-232](https://github.com/Goshik92/XR21B1411-RS-485-driver/tree/rs-232) branch.

The driver was tested with [Armbian 5.25](https://dl.armbian.com/orangepizero/archive/).

To build and install the driver follow [README.txt](README.txt).
