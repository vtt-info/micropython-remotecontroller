# micropython-remotecontroller
ESP8266 based smart remote controller. Code works on micropython.  
Please remember that this project is still on Alpha phase.  
The version with the C++: https://github.com/erdikusdemir/smarthome-wifi-remote  

# DESCRIPTION 

Portable remote controller to control smart home devices over MQTT protocol. It is based on micropython uploaded ESP8266 with OLED LCD and rotary encoder.
Remote can control switches, dimmers, fans, and temperature controllers.

The remote controller communicates with Node-Red flow by MQTT JSON messages. Node-Red flow converts the signals from both remote and HA side and makes implementation easier. Items you would like to control by remote can be edited by "config file" function. Arduino sketch only configures Wifi and MQTT settings. All the item information are called at the initialization stage of the remote.

Wemos kill its power after 15 secs of idle time. Thus, power consumption of the remote is zero when it is not used. 

Hardware is consist of;
1. Wemos D1 mini Pro,
2. A clickable rotary encoder,
3. 0.96" I2C 128x64 OLED display,
4. Wemos battery shield,
5. LIPO battery,
6. 3D printed enclosure (under progress),  
7. TPS27081ADDCR load switch,  
8. 2222A NPN transistor,  
9. 330, 1 k, and 1 MOhm resistors.  

<img src="https://github.com/erdikusdemir/micropython-remotecontroller/blob/master/remote_insidecover.jpg" width="600">
<img src="https://github.com/erdikusdemir/micropython-remotecontroller/blob/master/Schematic.PNG" width="800">

# Instructions:  
1. Follow the schematic and build the hardware,  
2.1. Modify the secret.json file according to your credentials,  
2.2. Copy the files into the micropython ESP8266,  
3.1. Copy NodeRed flow into your NodeRed server,  
3.2. Configure your HA and MQTT servers,  
3.3. Configure your items by editing "config file" function,  
(id: order in your OLED screen, HAid: id name of item you want to control, type: switch(0), dimmer(1), or temperature controller(2))  
4.4. Deploy the node and everything should works.  

# To do list:
1. Code still does not mqtt message to the server.  
2. ESP chip being very slow to connect to the wifi. This needs to be fasten up somehow.  
3. Case design needs to be finished.  

