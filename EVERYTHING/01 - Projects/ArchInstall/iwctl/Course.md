Alright, Dylan, let's dive deep into `iwctl` (iNet Wireless Daemon Command Line Interface), a command-line tool used to manage Wi-Fi connections on systems running `iwd`. This guide will cover everything from the basics to advanced usage, so you’ll have a comprehensive understanding of how to use `iwctl`.

### What is `iwctl`?

`iwctl` is part of the iNet Wireless Daemon (`iwd`) suite, which is designed to manage Wi-Fi connections on Linux systems. It offers a simple and straightforward command-line interface to scan for networks, connect to Wi-Fi networks, manage saved networks, and more.

### Installing `iwd`

First, ensure you have `iwd` installed on your system. On Arch Linux, you can install it using `pacman`:

```sh
sudo pacman -S iwd
```

After installing, you need to start and enable the `iwd` service:

```sh
sudo systemctl start iwd
sudo systemctl enable iwd
```

### Basic Usage of `iwctl`

#### 1. Launching `iwctl`

To start using `iwctl`, simply type `iwctl` in your terminal:

```sh
iwctl
```

This will drop you into the `iwctl` interactive shell, where you can start issuing commands. If you prefer, you can also use `iwctl` with arguments directly from your regular shell without entering the interactive mode.

#### 2. Listing Devices

To see the list of Wi-Fi devices, use:

```sh
device list
```

This command will output something like:

```plaintext
Devices:
        phy0 wlan0
```

#### 3. Scanning for Networks

To scan for available Wi-Fi networks, use:

```sh
station wlan0 scan
```

Replace `wlan0` with your actual device name. After scanning, you can list the available networks:

```sh
station wlan0 get-networks
```

#### 4. Connecting to a Network

To connect to a network, use:

```sh
station wlan0 connect SSID
```

Replace `SSID` with the name of the network you want to connect to. If the network is secured, `iwctl` will prompt you to enter the passphrase.

#### 5. Disconnecting from a Network

To disconnect from a network, use:

```sh
station wlan0 disconnect
```

#### 6. Displaying Connection Status

To check the status of your connection:

```sh
station wlan0 show
```

### Advanced Usage

#### 1. Managing Known Networks

You can list all known (saved) networks with:

```sh
known-networks list
```

To forget a known network:

```sh
known-networks remove SSID
```

#### 2. Setting Up a Persistent Configuration

You can create a configuration file to store network settings persistently. Create or edit `/etc/iwd/main.conf` and add your configurations. For example:

```ini
[General]
EnableNetworkConfiguration=true

[Network]
NameResolvingService=resolvconf
```

#### 3. Using Hidden Networks

To connect to a hidden network (SSID not broadcasted):

```sh
station wlan0 connect-hidden SSID
```

#### 4. Setting Up a Wi-Fi Access Point

To set up your device as an access point:

```sh
ap wlan0 start SSID
```

To stop the access point:

```sh
ap wlan0 stop
```

#### 5. Debugging and Logs

You can enable more verbose logging for debugging:

```sh
set log-level debug
```

Logs can be found in the system journal. Use `journalctl` to view them:

```sh
sudo journalctl -u iwd
```

### Practical Examples

Let's go through a practical session where you connect to a network, manage it, and troubleshoot common issues.

#### Example: Connecting to a New Network

1. **List devices:**

    ```sh
    iwctl device list
    ```

2. **Scan for networks:**

    ```sh
    iwctl station wlan0 scan
    iwctl station wlan0 get-networks
    ```

3. **Connect to the desired network:**

    ```sh
    iwctl station wlan0 connect YourNetworkSSID
    ```

    Enter the passphrase if prompted.

4. **Verify connection:**

    ```sh
    iwctl station wlan0 show
    ```

#### Example: Managing Known Networks

1. **List known networks:**

    ```sh
    iwctl known-networks list
    ```

2. **Remove a known network:**

    ```sh
    iwctl known-networks remove UnwantedSSID
    ```

#### Example: Troubleshooting Connection Issues

1. **Check connection status:**

    ```sh
    iwctl station wlan0 show
    ```

2. **Check logs for errors:**

    ```sh
    sudo journalctl -u iwd
    ```

3. **Enable debug logging and retry connection:**

    ```sh
    iwctl set log-level debug
    iwctl station wlan0 connect YourNetworkSSID
    ```

### Customizing and Scripting

`iwctl` commands can be scripted for automation. For example, a simple script to connect to a Wi-Fi network could look like this:

```sh
#!/bin/bash

DEVICE="wlan0"
SSID="YourNetworkSSID"
PASSPHRASE="YourNetworkPassphrase"

iwctl --passphrase $PASSPHRASE station $DEVICE connect $SSID
```

Make the script executable and run it:

```sh
chmod +x connect_wifi.sh
./connect_wifi.sh
```

### Conclusion

You now have a comprehensive understanding of `iwctl` and how to manage Wi-Fi connections on your Arch Linux system using `iwd`. From basic commands to advanced configuration and troubleshooting, this guide covers everything you need to become proficient in using `iwctl`. If you encounter any issues or need further assistance, feel free to ask!