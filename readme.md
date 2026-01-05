# STM32 USB FS with FatFS
Example for how to use STM32 usb interface as Mass storage device accessing SD card through 4-Wire SDMMC interface and implementing FatFS filesystem

![Dev board trace](/assets/images/stmf411dev.png)

## How to setup
### Option 1: Copy over
1. Clone this repository
2. Create your project using the option to create a project from existing .ioc file then select the included setup file
3. Generate the code
4. Replace the generated "USB_DEVICE/usbd_storage_if.c" and "Core/Src/main.c" with what's included here
### Option 2: Implement in an existing project
1. In CubeMX on the Connectivity tab, Enable USB_OTG_FS or USB_OTG_HS (Device only), SDIO (SD 4 bits Wide bus)
2. On Middleware and Software Packs, Enable FATFS (Check mark SD Card, Scroll down and set "USE_LFN" to "Enable with static working buffer on the BSS" ,go to "Platform Settings" tab and select a pin for detecting Card insert)
3. Now enable USB_Device middleware and set the MSC_MEDIA_PACKET to 32768 bytes (More = Faster data rates)
4. Generate the code in CubeIDE
5. Replace the generated "USB_DEVICE/usbd_storage_if.c" and place the f_mount command somewhere in main.c so it'll run at startup.

P.S. STM32CubeIDE version 1.17 is the last version with CubeMX function built-in for viewing .ioc

## STM Interface Requirements
- USB FS or HS
- SDMMC/SDIO

## Useful references
Special thanks to Phil's lab for the knowledge on [STM's USB mass storage](https://www.youtube.com/watch?v=aEwwQMdKd-c).