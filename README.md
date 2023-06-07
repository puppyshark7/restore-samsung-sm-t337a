# Restore Galaxy Tab 4 8.0 (AT&T)

An easy way to completely reset this tablet

## Preparation

1. Plug in the device into your computer 
2. Enter "Download Mode" or "Odin Mode" (same thing) by pressing and holding Power, Volume Down, and Home at the same time. 
3. Once you see a dialog, release the three keys and press Volume Up to enable your device to be overwritten
4. Download the firmware files [here](https://androidfilehost.com/?fid=529152257862688251). Make sure to unzip the folder and place it somewhere you know.

## Configuration

1. Launch Odin from the Odin folder. You will see a lot of options, leave them alone for now.
2. If you wish to completely overwrite the partition table (recommended if tablet is broken), click on PIT and select the only pit file in the folder of the firmware you downloaded. Also select the Re-Partition and Nand Erase All options. Skip this step if you want to keep the partition table (untested).
3. Click on the BL, AP, CP, and CSC boxes and select the appropriate file in the same folder (make sure the beginning matches the box you click on).
4. Make sure Auto Reboot and F. Reset Time are selected (they should've been selected when you started Odin).

## Flashing

1. Making sure that you have a device (on top of the options, there should be an ID for your device followed by the COM port), click on START at the bottom. The firmware will flash on to the device and it will reboot once or twice.
2. If the device gets stuck at AT&T logo, wait a few seconds and press the home button.
3. Pick a language and setup the device. You need to enter the credentials to the same Samsung account you had before you reset the device. If the account says processing failed, try turning off two-step verification. If that doesn't work, keep reading. Otherwise, you're done!

## Bypassing Samsung Account

1. Reboot the device to get back to the language selection screen.
2. Hold two fingers on the screen until you get to the tutorial.
3. Click exit to select it, then double click to exit the tutorial.
4. Make a large L starting at the top-left corner of the tablet and finishing at the bottom right at the tablet to open up the TalkBack menu.
5. Click on Text-to-Speech settings in the lower-right corner, which opens the main settings.
6. Make another L in the same way, this time clicking Pause Feedback in the upper-left corner, then click OK to disable TalkBack.
7. In settings, scroll down to system, then find and click on Build Number until it says "You are a developer!" at the bottom of the screen.
8. In the setting categories, open developer options, then find and toggle USB debugging on.
9. On your PC, go to the ADB folder and go to File, Open in Windows Powershell.
10. Connect the device to the PC.
11. Type ./adb devices in the terminal to start ADB.
12. Allow USB debugging on the device.
13. On the computer, type the following commands:
    ./adb shell
    pm hide com.osp.app.signin
    pm hide com.sec.android.SecSetupWizard
14. Reboot the device, and you won't have to sign in with Samsung.

NOTE: This is a temporary procedure and blocks you from using a samsung account, disabling reactivation lock, or factory resetting from settings.

## You've finished!

If you have any other problems that built in tools don't solve, redo these steps, or try downloading different firmware.

## About

All of the resources aren't original (except this file).

Odin (at the bottom of first post): https://forum.xda-developers.com/t/guide-how-to-restore-stock-firmware-images-in-all-tab-4-series-7-0-8-0-10-1.2979006/

Firmware: https://androidfilehost.com/?fid=529152257862688251

Tutorial for flashing firmware (tutorial for 4 file firmware): https://forum.xda-developers.com/t/download-sm-t337a-lollipop-firmware-finally-available-for-download.3536509/

Tutorial for bypassing lock (I didn't root the device, didn't think it was worth the risk): https://forum.xda-developers.com/t/tutorial-remove-samsung-recovery-lock-sm-t337a.4171199/

ADB (it's version 34.0.1 which I copied from my computer into these files, using a newer version shouldn't matter): https://developer.android.com/tools/releases/platform-tools

## Contributing

All contributions are accepted if you find another way of making it work. Please make a pull request and I will review it.