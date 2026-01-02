# STM32 USB FS with FatFS
Example for how to use STM32 usb interface as Mass storage device accessing SD card through 4-Wire SDMMC interface and implementing FatFS filesystem

## How to use
1. Clone this repository
2. Either check out STM411_DEV_1.ioc for how to set up or check out Phil's lab video in the link below
3. Generate the code using STM32CubeIDE and modify "USB_DEVICE/usbd_storage_if.c"
4. Check out "Core/Src/main.c", here we mount the SD card using "f_mount"

P.S. STM32CubeIDE version 1.17 is I think the last version with CubeMX function built-in for viewing .ioc so in case newer version, you might also need to download STM32CubeMX

## STM Interface Requirements
- USB FS or HS (Though, HS usually requires external PHY)
- SDMMC/SDIO

## Useful references
Special thanks to Phil's lab for the knowledge on [STM's USB mass storage](https://www.youtube.com/watch?v=aEwwQMdKd-c).