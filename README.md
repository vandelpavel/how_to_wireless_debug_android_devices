### How to wireless debug an android device

- Enable "developer mode" on the device
- Enable "Debug USB"
- Enable "Debug ADB while charging"
- Connect the device via USB (and allow every related popup)
- Copy the "platform-tools_r34.0.5-windows.zip" file
- Extract it and open a terminal in the same location as the "adb.exe" file
- launch next command to open a tcpip connection on port 5555:

```bash
 adb tcpip 5555
```

- launch next command and check if your usb device is listed:

```bash
adb devices
```

- launch next command to enable wireless debug on the device:

```bash
adb connect <device_ip_address>
```

- launch again this command to verify that your device is listed as connected both USB and wireless

```bash
 adb devices
```

- disconnect the usb
- launch again this command to verify that your device is still there only as wireless connected

```bash
 adb devices
```

- search for "chrome://inspect" and wait a few until all the device chrome's

-If you find any problem just kill the tcp connection and restart:

```bash
adb kill-server
```

### Encountered issues

- Both devices must be connected to the same network
- Sometimes you need to disable end re-enable "usb debug"
- When on "chrome://inspect" you may need to open a few tabs to make it appear in the list or just wait a bit (it's not that rapid)
