### Setting Up Rasberry Pi's

----------

The Raspberry Pi is an amazingly capable device, but they take a couple of steps to get setup appropriately. There are many phases to the setup, which are detailed below.


##### Hooking up the Raspberry Pi for the First Time
You will need to connect componets to your Raspberry Pi in the correct order. 

1. An HDMI monitor and cable
2. USB mouse and keyboard
3. Micro SD card preloaded with NOOBS
4. 5V Micro-USB power supply

The red led on the board should light up and your HDMI monitor will soon illuminate, allowing you to install the Raspbian operating system and expand your filesystem. Click on 'Install' to begin the 5 minute process.

#### OS Configuration

The Raspberry Pi will reboot into the Raspbian PIXEL desktop. Welcome to Linux!

Before doing anything, the time must be correctly set so wifi networking connects appropriately. Click on the `Raspberry Menu` icon in the upper left hand corner, navigate to `Preferences` and select `Raspberry Pi Configuration`. Within this dialog box, make some changes...

`System` Tab
- `Change Password` to a password of your choosing of at least 8 characters. The current password is `raspberry`.
- Hostname: yourname-pi

`Interface` Tab
- Toggle `SSH` to `Enable`
- Toggle `VNC` to `Enable`

`Localisation` Tab
- `Set Locale` to `en (English)`, `US(USA)`, and `UTF-8`
- `Set Timezone` to `America`, and `Chicago`
- `Set Keyboard` to `United States` and `English (US)` or to your taste
- `Set Wifi Country` to `US United States`

#### Connecting to the Class Wifi Network

Click on the wifi symbol and connect to the "Nerd Corner" network. There is no password.

Use the Chromium browser (globe icon in the menu bar) and browse the internet. YThis browser is the open source version of Google Chrome. You may notice certain pages render differently, and some may even crash your browser. Welcome to Linux.  

#### Updating and Upgrading Software on Linux

Unlike Windows and macOS, much of the software for the Linux platform is free of charge and readily available. Software is managed in Raspbian by a software package manager called `Aptitude` that can be run interactively from the command line. Open up the Terminal application `[>_]` from the menu bar and type the following, being mindful of capitalization and spaces.

```
sudo apt-get update
```
This line of code checks for updated software and ensures you don't get old versions of packages.

```
sudo apt-get upgrade
```
This line of code installs all new software packages available, ensuring the Raspberry Pi is fully up-to-date. You may need to press 'q', 'y', or 'i' at various points if the installers require it. The process will likely take around 10 minutes.

#### Restart your Raspberry Pi

Click on the `Raspberry Menu` and click `Shut Down`. A dialog will pop open and allow you to `Restart`.

#### Static IP and VNC

It is necessary that the Raspberry Pi always be available at a reliably consistent location on the internet. For this reason, we can set a static IP address.

```
sudo nano /etc/dhcpcd.conf
```

add to the very bottom of the file...

```
# Custom static IP address for wlan0.
interface wlan0
static ip_address=192.168.0.$$$
static routers=192.168.0.1
static domain_name_servers=192.168.0.1
```

Change the `$$$` to three random numbers and remember that address.

Finally, download [VNC viewer](https://www.realvnc.com/en/connect/download/viewer/) for your platform of choice to connect to your Raspberry Pi at that address. But, restart first!

#### Restart your Raspberry Pi

Yes, again. Click on the `Raspberry Menu` and click `Shut Down`. A dialog will pop open and allow you to `Restart`.


