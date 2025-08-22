# Unbrick Guide for X6528B HOT 40I

This guide provides a step-by-step process to restore your X6528B HOT 40I device from a bricked state using the provided tools and firmware. Follow these instructions carefully to ensure a smooth recovery.

## Prerequisites
- **Unbrick.rar** [Releases]()
- **Original Firmware (V197)**: Available on [Google Drive](https://drive.usercontent.google.com/download?id=1WJWqoKDSN3JkUJEy-VWLHB-_qMEvSwaX&export=download&authuser=0) or [Yandex Disk](https://disk.yandex.ru/d/_Rc-oo57vE4PHg).
- **UpgradeDownload/ResearchDownload Tool**: Download and extract the tool to your desktop.

## Step-by-Step Instructions

1. **Prepare the Tools**  
   Download and extract the **UpgradeDownload/ResearchDownload** tool. Move the extracted "bin" folder to your desktop for easy access.

2. **Download the Firmware**  
   Obtain the original V197 firmware for the X6528B HOT 40I from the provided links on [Google Drive](https://drive.usercontent.google.com/download?id=1WJWqoKDSN3JkUJEy-VWLHB-_qMEvSwaX&export=download&authuser=0) or [Yandex Disk](https://disk.yandex.ru/d/_Rc-oo57vE4PHg).

3. **Load the Firmware**  
   - Launch **ResearchDownload.exe**.  
   - Click the gear icon and select the downloaded V197 firmware file.  
   - Once the file is verified, the program will create a folder in the **ImageFiles** directory containing the firmware contents.

4. **Extract Unbrick Files**  
   Unpack the contents of **Unbrick.rar** into the firmware folder located in **ImageFiles**. Ensure all files are correctly placed.

5. **Initiate Flashing**  
   - Locate and run the batch file (`.bat`) in the firmware folder.  
   - Connect your X6528B HOT 40I to your computer while holding the **Volume Down** button.  
   - Release the button once the console displays **"EXEC FDL1"**.

6. **Execute Partition Commands**  
   In the command interface, enter the following commands one by one to flash the respective partitions:

   ```
   write_part boot_a boot.img
   write_part boot_b boot.img
   write_part super super.img
   write_part dtbo dtbo.img
   write_part prodnv prodnv.img
   write_part vbmeta_a vbmeta-sign.img
   write_part vbmeta_system_a vbmeta_system.img
   write_part vbmeta_system_ext_a vbmeta_system_ext.img
   write_part vbmeta_product_a vbmeta_product.img
   write_part vbmeta_odm_a vbmeta_odm.img
   write_part vendor_boot_a vendor_boot.img
   write_part vbmeta_vendor_a vbmeta_vendor.img
   write_part blackbox blackbox.img
   write_part splloader u-boot-spl-16k-ufs-sign.bin
   write_part persist persist.img
   write_part uboot_a lk-sign.bin
   write_part sml_a sml-sign.bin
   write_part teecfg_a teecfg-sign.bin
   write_part trustos_a tos-sign.bin
   write_part tkv_a tkv.img
   write_part tranfs tranfs.img
   write_part cache cache.img
   write_part pm_sys_a qogirl6_cm4.bin
   write_part l_agdsp_a QogirL6_AUDCP_DSP_lit_dm.bin
   write_part l_gdsp_a qogirl6_pubcp_DM_DSP.bin
   write_part l_ldsp_a qogirl6_pubcp_LTEA_DSP.bin
   write_part l_deltanv_a qogirl6_pubcp_customer_deltanv.bin
   write_part l_modem_a SC9600_qogirl6_pubcp_modem.bin
   write_part userdata userdata.img
   erase_part misc
   erase_part sysdumpdb
   erase_part metadata
   ```

   **⚠️ Warning**: Do **not** execute `erase_part miscdata`. This command will lock the bootloader, preventing further modifications.

7. **Complete the Process**  
   After executing all commands, enter the following to reset the device:

   ```
   reset
   ```

8. **Power On and Celebrate**  
   Disconnect the device, power it on, and enjoy your fully restored X6528B HOT 40I!

## Notes
- Ensure all files are correctly placed in the **ImageFiles** directory to avoid errors during flashing.
- Double-check each command before execution to prevent mistakes.
- If you encounter issues, verify the firmware version and ensure the **Unbrick.rar** contents are properly extracted.

Happy unbricking! 🎉
