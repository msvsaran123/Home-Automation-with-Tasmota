# Home-Automation-with-Tasmota
![](RackMultipart20220111-4-sts3az_html_ae9773f6c407f957.jpg)
# Alexa Controlled Home Automation with Tasmota (no coding required)

Hello friends! Welcome back to the Home Automation Series. In the previous blog we have learnt how to make a smart switch board with the help of Sinric server. If you haven&#39;t read it yet this is the link

[https://www.hnhcart.com/blogs/learn/voice-and-manual-controlled-smart-switch-board-with-feedback](https://www.hnhcart.com/blogs/learn/voice-and-manual-controlled-smart-switch-board-with-feedback)

just go through it to get a brief Idea about home automation.

We have to go a step forward because Sinric is going to terminate its free services from 31st of August this year. That&#39;s why I came with a new idea. That is home automation using Tasmota.

# A Brief Introduction about Tasmota

Tasmota contains a myriad of features and supported peripherals (sensors, controllers and similar). Due to the flash size and memory constraints of ESP8266 not all features can be included in precompiled release binaries.

To enable some of the features you have to compile your own binary. Each feature with such requirement has a warning with instructions on how to enable it.

Tasmota has released so many binary files to use ESP8266 based modules as web servers. Here, we will use one of its basic binary files.

Objective

The main objective of this project is to control any Electrical appliances with both voice commands, Alexa app and with manual switches from anywhere in the world.

\*We can check the state of appliances whether it is turned on or off in our mobile at anytime and anywhere in the world.

\*You can also control the appliances with both manual switches and from an app in our mobile phone when the internet connection is not alive.

\*As Tasmota is a web server itself in the ESP8266 based module, it is so responsive and the commands that are sent to the module will work accurately.

\*You can also get real time feedback of the responses.

Let&#39;s start our project.

# Components required

# Hardware

### 1.Nodemcu board:

We will upload our code into this development board. It is more compatible than any other development boards available.

![](RackMultipart20220111-4-sts3az_html_133d7177f71791aa.jpg)
 Buy it from here

[https://www.hnhcart.com/products/node-mcu-cp-210x?\_pos=1&amp;\_sid=16b795a75&amp;\_ss=r](https://www.hnhcart.com/products/node-mcu-cp-210x?_pos=1&amp;_sid=16b795a75&amp;_ss=r)

If you want to make your project cheaper you can use ESP-12e board. You can check how to program it here

[https://youtu.be/UxIBCyP0V18](https://youtu.be/UxIBCyP0V18)

![](RackMultipart20220111-4-sts3az_html_1179391320ec147b.png)

Buy it from here

[https://www.hnhcart.com/products/esp-12e-wifi-module?\_pos=1&amp;\_sid=ec9ba047b&amp;\_ss=r](https://www.hnhcart.com/products/esp-12e-wifi-module?_pos=1&amp;_sid=ec9ba047b&amp;_ss=r)

Don&#39;t forgot to add 3.3v voltage regulator (AMS 1117 3.3v regulator is recommended)

Buy it from here

[https://www.hnhcart.com/products/reg1117-ic?\_pos=2&amp;\_sid=39426c2de&amp;\_ss=r](https://www.hnhcart.com/products/reg1117-ic?_pos=2&amp;_sid=39426c2de&amp;_ss=r)

### 2. 4 channel relay board:

It acts as a switch. It can be controlled with little dc voltage to control high voltage appliances. ![](RackMultipart20220111-4-sts3az_html_a2cd6c647114ce18.png)

![](RackMultipart20220111-4-sts3az_html_4e92671b71be6f69.gif)

[https://www.hnhcart.com/products/4-channel-5v-relay-module?\_pos=11&amp;\_sid=959d29598&amp;\_ss=r](https://www.hnhcart.com/products/4-channel-5v-relay-module?_pos=11&amp;_sid=959d29598&amp;_ss=r)

### 3. Jumper wires:

As its name, it is used to connect pins of NodeMCU and relay board as well as switches.

![](RackMultipart20220111-4-sts3az_html_b4cae2f7bd41431.png)

### 4.Power source:

![](RackMultipart20220111-4-sts3az_html_9e7625bd708025cc.jpg)

### You can use even a mobile charger for power source.

Or you can buy it from here

[https://www.hnhcart.com/collections/power-supply-and-regulators/products/5v-1-amp-power-supply-board-220v-ac-to-5v-dc](https://www.hnhcart.com/collections/power-supply-and-regulators/products/5v-1-amp-power-supply-board-220v-ac-to-5v-dc)

### 5. Switches, Sockets and 8-way Gang box:

There is nothing to talk about it. These are familiar to everyone. These are available in every electrical shop.

![](RackMultipart20220111-4-sts3az_html_f6968d4511bc1d29.jpg) ![](RackMultipart20220111-4-sts3az_html_1cfef57b3b2d8a42.png) ![](RackMultipart20220111-4-sts3az_html_73e746452d176e8d.jpg)

### 6. Any Alexa device:

Alexa is a voice assistant made by Amazon.

Some Alexa devices are mentioned here. You can buy any of these for this project:

Note: If you want the Voice control, then an Alexa device is compulsory otherwise you can&#39;t control appliances with your voice. But still, you can control it using your mobile phone.

1. Alexa Echo Dot:

[https://www.amazon.in/Echo-Dot-3rd-Gen/dp/B07PFFMP9P/ref=sr\_1\_1?dchild=1&amp;keywords=alexa+devices&amp;qid=1610024316&amp;sr=8-1](https://www.amazon.in/Echo-Dot-3rd-Gen/dp/B07PFFMP9P/ref=sr_1_1?dchild=1&amp;keywords=alexa+devices&amp;qid=1610024316&amp;sr=8-1)

[https://www.amazon.in/Echo-Dot-4th-Gen-Blue/dp/B084KSRFXJ/ref=sr\_1\_2?dchild=1&amp;keywords=alexa+devices&amp;qid=1610024411&amp;sr=8-2](https://www.amazon.in/Echo-Dot-4th-Gen-Blue/dp/B084KSRFXJ/ref=sr_1_2?dchild=1&amp;keywords=alexa+devices&amp;qid=1610024411&amp;sr=8-2)

1. Alexa Echo Portable:

[https://www.amazon.in/Echo-Input-Portable-Smart-Speaker/dp/B07YP9WYFN/ref=sr\_1\_10?dchild=1&amp;keywords=alexa+devices&amp;qid=1610024411&amp;sr=8-10](https://www.amazon.in/Echo-Input-Portable-Smart-Speaker/dp/B07YP9WYFN/ref=sr_1_10?dchild=1&amp;keywords=alexa+devices&amp;qid=1610024411&amp;sr=8-10)

Circuit Diagram

GPIO 0 - D3 of NodeMCU - IN 1 of Relay board

GPIO2 - D4 of NodeMCU - IN 2 of Relay board

GPIO12 - D6 of NodeMCU - IN 3 of Relay board

GPIO13 - D7 of NodeMCU - IN 4 of Relay board

GPIO5 - D1 of NodeMCU - Switch 1

GPIO4 - D2 of NodeMCU - Switch 2

GPIO14 - D5 of NodeMCU - Switch 3

GPIO10 - SD3 of NodeMCU - Switch 4

![](RackMultipart20220111-4-sts3az_html_c9539b9e3d3815a8.png)

# Software

1. TASMOTA firmware flasher (Tasmotizer). You can download it from here

[https://github.com/tasmota/tasmotizer/releases/download/v.1.2/tasmotizer-1.2.exe](https://github.com/tasmota/tasmotizer/releases/download/v.1.2/tasmotizer-1.2.exe)

Note: On opening this file Windows warn you to not to run the software. No problem. The software is completely safe. Just click on More info and click on Run it Anyway.

1. Tasmota binary file. You can download it from here

[http://ota.tasmota.com/tasmota/release/tasmota.bin](http://ota.tasmota.com/tasmota/release/tasmota.bin)

1. Alexa app should be installed in your mobile phone. With this app you can control appliances from anywhere in the world. But here internet connection should be alive. You can install it from here

[https://play.google.com/store/apps/details?id=com.amazon.dee.app](https://play.google.com/store/apps/details?id=com.amazon.dee.app)

1. All 4 Hue app also should be installed in your mobile phone. With this app you can control appliances if you are connected to the common access point. Internet connection does not matter here. You can install it from here

[https://play.google.com/store/apps/details?id=de.renewahl.all4hue](https://play.google.com/store/apps/details?id=de.renewahl.all4hue)

After downloading and installing all the software, files and apps we can the start the project.

# Process

# Flashing Firmware to NodeMCU

1. Open the Tasmotizer Software and connect and connect any ESP8266 based module (for convenience let&#39;s say NodeMCU) and select the correct COM port of the module.
2. Click on open and select the &quot;tasmota.bin&quot; file which we have downloaded.
3. If you want to save the original firmware, click on the &quot;save original firmware&quot;. Otherwise, don&#39;t click.
4. By default, &quot;BIN file&quot; option is already selected. If not select it.
5. Make a tick on &quot;Self-resetting device&quot; and also on &quot;Erase before flashing&quot; (by default it is already selected).
6. Now, click on &quot;Tasmotize&quot;.

![](RackMultipart20220111-4-sts3az_html_a1003087a47f38fa.png) ![](RackMultipart20220111-4-sts3az_html_2d69ef900d80c9bc.png)

![](RackMultipart20220111-4-sts3az_html_75141677debcee37.png)

1. After Tasmotizing, click on &quot;ok&quot;.

Now, firmware flashing is completed. Your NodeMCU turned into a Tasmota Device.

# Connecting Tasmota Device to the Hotspot

1. Now, switch on the Wi-Fi in your mobile phone or laptop and select the &quot;tasmota\_\*\*\*\*\*\_\*\*\*\*\*&quot; access point.

Note: If your mobile phone shows the notification &quot;Internet connection may not be Available&quot;, just click on &quot;Keep the Connection&quot;.

1. Now open the Chrome or any of your favorite browser and enter the IP Address &quot;192.168.4.1&quot;

![](RackMultipart20220111-4-sts3az_html_46e70e38eea99917.png)

1. Enter the Wi-Fi credentials of your Hotspot and click on the &quot;Save&quot; button.

# Configuring the Tasmota Firmware

1. Open the Tasmotizer Software and click on &quot;Get IP&quot;. Note the IP Address.
2. Now, open the Wi-Fi settings in your mobile phone or laptop and connect your laptop to the Hotspot to which you have connected the Tasmota device.
3. Open any of your favorite browsers and enter the IP Address which you have noted.
4. You will see a page opened like this

![](RackMultipart20220111-4-sts3az_html_529b6b3c5b93f6a8.png)

5. Static IP address is important for various reason such as all 4-hue app will use that address to connect a Tasmota device and toggle its relays. Change in IP address by your router will result in failure to control a Tasmota device using all 4-hue app. We can use Tasmota Console to issue commands to change these settings. Navigate to  **Console** , enter commands one by one in given box and press Enter key each time. Various commands are discussed below;

**1) IP Address:**

IPAddress1 192.168.50.41

- First three pair should match your router configuration.
- Change fourth pair as desired.

**2) Gateway:**

IPAddress2 192.168.50.1

- Gateway is the IP address of your router.

**3) Subnet Mask:**

IPAddress3 255.255.255.0

**4) DNS Server:**

IPAddress4 192.168.50.1

- DNS Server is the IP address of your router.

**5) Reboot:**

restart 1

- Reboot Tasmota device after setting up IP address, Gateway, Subnet Mask and DNS Server

**Update all of these settings at once using Backlog command:**

Backlog IPAddress1 192.168.50.41; IPAddress2 255.255.255.0; IPAddress3 192.168.50.41; IPAddress4 192.168.50.1; restart 1

The device will restart automatically.

6. Navigate to Configuration \&gt; Configure Other and input Web Admin Password in respective field. You can also change Friendly Name if required. Click on the &quot;Hue Bridge&quot; option. Hit Save to take changes effect. Without enabling Hue bridge, you can&#39;t use all 4-hue app. Now browser will ask for user name and password. Admin is default user name and input the password you entered in Web Admin Password field before. Tasmota device will restart in few seconds to apply the configuration.

![](RackMultipart20220111-4-sts3az_html_ed2666a0b054c70a.png)

7. Click on &quot;Configuration&quot; and then click on &quot;Configure module&quot;. A page will open like this

![](RackMultipart20220111-4-sts3az_html_fa7f24264af9f8ba.png)

1. Click on module type and select &quot;Generic (0)&quot;. And click &quot;Save&quot;. The Tasmota module will reboot automatically.
2. Now again click on &quot;Configuration&quot; and then click on &quot;Configure module&quot;. A page will open like this

![](RackMultipart20220111-4-sts3az_html_cfcd03f3aa2dbbed.png)

1. Set all the options as shown in the below picture. And click on &quot;Save&quot;.

![](RackMultipart20220111-4-sts3az_html_1f09325361c7c1df.png)

1. Now again click on &quot;Configuration&quot; and then click on &quot;Configure other&quot; and enter the details as shown in picture. And then click &quot;Save&quot;.

![](RackMultipart20220111-4-sts3az_html_3a71ca2dcc71bdbc.png)

1. Now your Tasmota Switch Board is ready for use. The Tasmota module will reboot automatically.

# Setting the Apps

Before opening any of the apps make sure your mobile phone to the Wi-Fi network with which the Tasmota device is connected.

# Alexa app

1. Open the Alexa app and login with your amazon account.
2. Go to the devices section and tap on &quot;+&quot; symbol which is present at the top right corner. ![](RackMultipart20220111-4-sts3az_html_d26d6cb95af5c325.jpg)

1. Tap on &quot;Add Device&quot;.

![](RackMultipart20220111-4-sts3az_html_c52ae5637c737197.jpg)

1. Scroll to bottom of the page and tap on &quot;Other&quot;.

![](RackMultipart20220111-4-sts3az_html_de1645913f757158.jpg)

1. Tap on &quot;Discover Devices&quot;. It may take up to 45 seconds.

![](RackMultipart20220111-4-sts3az_html_dbb9a3d977516c3a.jpg)

1. You will get a notification that &quot;4 devices are found and connected&quot;.

Now you can control the appliances with your mobile phone via Internet.

# All 4 Hue App

1. Open the app and click on &quot;NEXT&quot;.

![](RackMultipart20220111-4-sts3az_html_4ce1ec9228233548.jpg)

1. You will see search in progress. After the search is completed click on &quot;NEXT&quot;.

![](RackMultipart20220111-4-sts3az_html_d8d39e83e560e1e9.jpg) ![](RackMultipart20220111-4-sts3az_html_63947c2085da2647.jpg)

1. You will see the devices found.

![](RackMultipart20220111-4-sts3az_html_69cd59c799ed6f95.jpg)

Now you can control the appliances with your mobile phone without Internet connection. Just keep your phone and Tasmota device on the same Wi-Fi network. Voice assistant may not work without Internet. When the Internet comes back the Voice Assistant starts working.
