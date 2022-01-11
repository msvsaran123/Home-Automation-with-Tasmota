# Home-Automation-with-Tasmota
![image](https://user-images.githubusercontent.com/79988029/148891987-09dbe61e-b3b1-4d45-b05c-9b1fc232aa53.png)
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

![image](https://user-images.githubusercontent.com/79988029/148892018-246cdf40-1df0-430a-856e-cb3ccdcd9b44.png)
 Buy it from here

[https://www.hnhcart.com/products/node-mcu-cp-210x?\_pos=1&amp;\_sid=16b795a75&amp;\_ss=r](https://www.hnhcart.com/products/node-mcu-cp-210x?_pos=1&amp;_sid=16b795a75&amp;_ss=r)

If you want to make your project cheaper you can use ESP-12e board. You can check how to program it here

[https://youtu.be/UxIBCyP0V18](https://youtu.be/UxIBCyP0V18)

![image](https://user-images.githubusercontent.com/79988029/148892061-7570e0ba-cb77-4c76-a894-67cca815dec6.png)

Buy it from here

[https://www.hnhcart.com/products/esp-12e-wifi-module?\_pos=1&amp;\_sid=ec9ba047b&amp;\_ss=r](https://www.hnhcart.com/products/esp-12e-wifi-module?_pos=1&amp;_sid=ec9ba047b&amp;_ss=r)

Don&#39;t forgot to add 3.3v voltage regulator (AMS 1117 3.3v regulator is recommended)

Buy it from here

[https://www.hnhcart.com/products/reg1117-ic?\_pos=2&amp;\_sid=39426c2de&amp;\_ss=r](https://www.hnhcart.com/products/reg1117-ic?_pos=2&amp;_sid=39426c2de&amp;_ss=r)

### 2. 4 channel relay board:

It acts as a switch. It can be controlled with little dc voltage to control high voltage appliances. ![image](https://user-images.githubusercontent.com/79988029/148892141-70657c32-6f73-414a-9a30-52d44145d0a2.png)

[https://www.hnhcart.com/products/4-channel-5v-relay-module?\_pos=11&amp;\_sid=959d29598&amp;\_ss=r](https://www.hnhcart.com/products/4-channel-5v-relay-module?_pos=11&amp;_sid=959d29598&amp;_ss=r)

### 3. Jumper wires:

As its name, it is used to connect pins of NodeMCU and relay board as well as switches.

![image](https://user-images.githubusercontent.com/79988029/148892164-13fe4c03-7ab3-4339-9a0c-5303cd4970f7.png)

### 4.Power source:

![image](https://user-images.githubusercontent.com/79988029/148892185-5870267a-c5ef-4f61-b9cb-280efd9c0d56.png)

### You can use even a mobile charger for power source.

Or you can buy it from here

[https://www.hnhcart.com/collections/power-supply-and-regulators/products/5v-1-amp-power-supply-board-220v-ac-to-5v-dc](https://www.hnhcart.com/collections/power-supply-and-regulators/products/5v-1-amp-power-supply-board-220v-ac-to-5v-dc)

### 5. Switches, Sockets and 8-way Gang box:

There is nothing to talk about it. These are familiar to everyone. These are available in every electrical shop.

![image](https://user-images.githubusercontent.com/79988029/148892204-ff5b31c5-5628-4add-a567-c48e760232e0.png)

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

![image](https://user-images.githubusercontent.com/79988029/148892276-d2402120-af44-4f33-b889-6bcb511d0107.png)

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

![image](https://user-images.githubusercontent.com/79988029/148892336-95e8e6bb-dd8a-4b2f-a495-7ec768abc704.png)
![image](https://user-images.githubusercontent.com/79988029/148892353-89f0723b-fe60-4de5-ba76-f8cd834b9cf4.png)
![image](https://user-images.githubusercontent.com/79988029/148892378-44512e60-81e2-46d7-8689-3f6e115dbb58.png)

1. After Tasmotizing, click on &quot;ok&quot;.

Now, firmware flashing is completed. Your NodeMCU turned into a Tasmota Device.

# Connecting Tasmota Device to the Hotspot

1. Now, switch on the Wi-Fi in your mobile phone or laptop and select the &quot;tasmota\_\*\*\*\*\*\_\*\*\*\*\*&quot; access point.

Note: If your mobile phone shows the notification &quot;Internet connection may not be Available&quot;, just click on &quot;Keep the Connection&quot;.

2. Now open the Chrome or any of your favorite browser and enter the IP Address &quot;192.168.4.1&quot;

![image](https://user-images.githubusercontent.com/79988029/148892417-6b713ade-7ae8-48a7-9959-7c9697b3f746.png)

3. Enter the Wi-Fi credentials of your Hotspot and click on the &quot;Save&quot; button.

# Configuring the Tasmota Firmware

1. Open the Tasmotizer Software and click on &quot;Get IP&quot;. Note the IP Address.
2. Now, open the Wi-Fi settings in your mobile phone or laptop and connect your laptop to the Hotspot to which you have connected the Tasmota device.
3. Open any of your favorite browsers and enter the IP Address which you have noted.
4. You will see a page opened like this

![image](https://user-images.githubusercontent.com/79988029/148892494-8a34b479-2c6a-4871-b980-b8269003a73d.png)

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

![image](https://user-images.githubusercontent.com/79988029/148892521-5f71020e-8cb0-4158-85e2-8b65fd4e35c4.png)

7. Click on &quot;Configuration&quot; and then click on &quot;Configure module&quot;. A page will open like this

![image](https://user-images.githubusercontent.com/79988029/148892552-9c4c6194-d6cb-43e9-bb64-d98471aced7e.png)

8. Click on module type and select &quot;Generic (0)&quot;. And click &quot;Save&quot;. The Tasmota module will reboot automatically.
9. Now again click on &quot;Configuration&quot; and then click on &quot;Configure module&quot;. A page will open like this

![image](https://user-images.githubusercontent.com/79988029/148892680-a5aa93d8-3923-4df3-bfac-d2a70fa35765.png)

10. Set all the options as shown in the below picture. And click on &quot;Save&quot;.

![image](https://user-images.githubusercontent.com/79988029/148892699-0328548e-a4ae-45a2-a8f1-23a287a105e1.png)

11. Now again click on &quot;Configuration&quot; and then click on &quot;Configure other&quot; and enter the details as shown in picture. And then click &quot;Save&quot;.

![image](https://user-images.githubusercontent.com/79988029/148892733-97becf4e-3a55-4e77-8644-2adc8267e381.png)

12. Now your Tasmota Switch Board is ready for use. The Tasmota module will reboot automatically.

# Setting the Apps

Before opening any of the apps make sure your mobile phone to the Wi-Fi network with which the Tasmota device is connected.

# Alexa app

1. Open the Alexa app and login with your amazon account.
2. Go to the devices section and tap on &quot;+&quot; symbol which is present at the top right corner. ![image](https://user-images.githubusercontent.com/79988029/148892821-be1f79f9-ac20-46d1-bfaa-fe428c60864c.png)

3. Tap on &quot;Add Device&quot;.

![image](https://user-images.githubusercontent.com/79988029/148892841-0ed3c67d-2a39-4851-9f49-35ec292f1a51.png)

4. Scroll to bottom of the page and tap on &quot;Other&quot;.

![image](https://user-images.githubusercontent.com/79988029/148892876-9a72a3c2-8400-43b2-a716-9cdf1b24cc10.png)

5. Tap on &quot;Discover Devices&quot;. It may take up to 45 seconds.

![image](https://user-images.githubusercontent.com/79988029/148892897-4447c3a9-b3fa-47fb-821a-5b4479b70bd8.png)

6. You will get a notification that &quot;4 devices are found and connected&quot;.

Now you can control the appliances with your mobile phone via Internet.

# All 4 Hue App

1. Open the app and click on &quot;NEXT&quot;.

![image](https://user-images.githubusercontent.com/79988029/148892933-e54aa7e5-b683-447a-a1da-091900d0c715.png)

2. You will see search in progress. After the search is completed click on &quot;NEXT&quot;.

![image](https://user-images.githubusercontent.com/79988029/148892955-b120dca3-44bf-478b-9aa5-1bbf2fbd45df.png)
![image](https://user-images.githubusercontent.com/79988029/148892982-5548dd1a-4fe5-4cf3-b36d-d55946a100c5.png)

3. You will see the devices found.

![image](https://user-images.githubusercontent.com/79988029/148893011-248a5f76-152a-4095-a92c-194905dc665d.png)

Now you can control the appliances with your mobile phone without Internet connection. Just keep your phone and Tasmota device on the same Wi-Fi network. Voice assistant may not work without Internet. When the Internet comes back the Voice Assistant starts working.
