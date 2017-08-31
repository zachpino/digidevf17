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

##### OS Configuration

The Raspberry Pi will reboot into the Raspbian PIXEL desktop. Welcome to Linux!

Before doing anything, the time must be correctly set so wifi networking connects appropriately. Click on the `Raspberry Menu` icon in the upper left hand corner, navigate to `Preferences` and select `Raspberry Pi Configuration`. Within this dialog box, make some changes...

`System` Tab
- Hostname: yourname-pi

`Interface` Tab
- Toggle `SSH` to `Enable`
- Toggle `VNC` to `Enable`

`Localisation` Tab
- `Set Locale` to `en (English)`, `US(USA)`, and `UTF-8`
- `Set Timezone` to `America`, and `Chicago`
- `Set Wifi Country` to `US United States`

##### Connecting to the Class Wifi Network

Click on the wifi symbol and connect to the "Nerd Corner" network. There is no password.
