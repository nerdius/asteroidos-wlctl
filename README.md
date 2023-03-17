# wlctl
`wlctl` is a simple wrapper shell script for [AsteroidOS](https://asteroidos.org/)'s `connmanctl` that aims to simplify managing wireless lan (WLAN) interface

# Prerequisites
In order to use the script, both the device you have and the AsteroidOS build you're running needs to support WLAN.

# Installation
1. Clone the repository or download the *wlctl* file.
2. Connect your watch to your computer using the USB cable.
3. Enable ADB interface from AsteroidOS settings.
4. `cd` into the directory that contains the *wlctl* script file.
5. Run:
    ```
    adb push wlctl /usr/bin
    ```
6. Get the ADB shell:
    ```
    adb shell
    ```
7. Make the shell script executable:
    ```
    chmod +x /usr/bin/wlctl
    ```
8. Run `wlctl` to confirm the installation.

**Note:** If you have more than one devices connected, you'll need to specify the device using the *-s* when running `adb push` or `adb shell` using the following syntax: `adb -s SERIAL_NUMBER ...`

# Usage
You can run `wlctl help` to get the usage information:

```
USAGE
  wlctl ACTION [NAME_PATTERN]

  Actions:
    enable                      Enable Wi-Fi.
    disable                     Disable Wi-Fi.
    connect [NAME_PATTERN]      Connect to a Wi-Fi network. You can specify an
                                unique name pattern in order to connect to a
                                specific network available.
    disconnect [NAME_PATTERN]   Disonnect from a Wi-Fi network. You can specify
                                an unique name pattern in order to connect to a
                                specific network available.
    status                      Get connection and hardware status.
    help                        Get this help.
```

# Limitations
Due to the `connmanctl`'s limitations, you can't initially connect to a protected Wi-Fi network via this script directly. If you're connecting to a Wi-Fi network for the first time, follow [these instructions](https://asteroidos.org/wiki/ip-connection/#ip-over-wlan) first. Once you've connected to the network, it's saved, so you can use this script to switch between the saved networks or disconnect from them.

# License
This script is available under the [MIT License](LICENSE).

