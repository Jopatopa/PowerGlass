POWER GLASS
===========
Advanced power management for Android: Reboot, Recovery, Bootloader,
Fastboot and Power Off, using ROOT or Shizuku.

Made by tt:@josipzzz | GitHub: jopatopa  (https://github.com/jopatopa)


REQUIREMENTS
------------
- Android 6.0 (API 23) or newer
- ONE of the following:
    * ROOT (Magisk, KernelSU, etc.), or
    * Shizuku installed and running (https://shizuku.rikka.app)


HOW TO USE
----------
1. Open Power Glass.
   The app checks for access automatically. It tries Shizuku first, then ROOT.

2. Grant access when asked.
   - Shizuku: tap "Allow" when Shizuku asks about Power Glass.
   - ROOT: tap "Grant" in your root manager's prompt.

3. Check the label above the buttons.
   "Access: Shizuku" or "Access: Root" means you are ready.

4. Tap an action and confirm:
   - Reboot      Restarts the phone normally.
   - Recovery    Restarts into recovery mode.
   - Bootloader  Restarts into the bootloader (fastboot mode).
   - Fastboot    Restarts into fastbootd (userspace fastboot). Only works
                 on devices with dynamic partitions.
   - Power Off   Shuts the phone down.
   Every tap gives a small vibration; confirming gives a stronger one.

5. Change the look:
   Tap the gear icon (top right) and pick a design. It applies instantly
   and is remembered the next time you open the app.
   - Apple iOS Liquid Glass
   - Google Material 3 (You)       (uses your wallpaper colors on Android 12+)
   - Samsung One UI                (buttons at the bottom for one-handed use)
   - Xiaomi Material 3 / HyperOS


IF YOU SEE "ROOT OR SHIZUKU REQUIRED"
-------------------------------------
- Retry         Checks access again.
- Open Shizuku  Opens the Shizuku app (shown only if it is installed).
- Exit          Closes the app.

Fixes:
- Shizuku: start the Shizuku service first (wireless debugging or root),
  then tap Retry. If you chose "Deny and don't ask again", open Shizuku,
  go to the authorized apps list and enable Power Glass.
- ROOT: open your root manager and allow superuser for Power Glass.
  Then tap Retry.


TROUBLESHOOTING
---------------
- Buttons are greyed out: there is no access yet. Fix it as above.
- "Command failed" message: your ROM may block that command. Try ROOT
  instead of Shizuku, or the other reboot option.
- Fastboot does nothing: your device probably has no fastbootd. Use
  Bootloader instead.
- Shizuku stops after a reboot: that is normal on non-root devices.
  Start Shizuku again, then reopen Power Glass.


BUILDING FROM SOURCE
--------------------
1. Open the PowerGlass folder in Android Studio.
2. Let Gradle sync (JDK 17, Android Gradle Plugin 8.5.2).
3. Run the "app" configuration on a device, or use
   Build > Build Bundle(s) / APK(s) > Build APK(s).


WARNING
-------
These actions restart or shut down your device immediately after you
confirm. Save your work first. Booting into recovery or the bootloader
is safe by itself, but flashing anything from there is at your own risk.
