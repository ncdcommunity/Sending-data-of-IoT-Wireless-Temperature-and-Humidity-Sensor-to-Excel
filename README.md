# Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel

We are using here NCD's Temperature and Humidity sensor, but the steps stay the equal for any of the **ncd** product, so if you have other ncd wireless sensors, experience free to observe alongside besides. By means of the stop of this text, you need to have a stable understanding of how to set up the sensors, configure node-red, and see the data on a dashboard like the one pictured right here.

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/Wireless%20Temp%20and%20Hum%20Sensor.png)
# IoT Long Range Wireless Temperature and Humidity  Sensor
Introducing NCD’s long-range wireless temperature humidity sensor, boasting up to a 28 Mile range using a wireless mesh networking architecture.  Incorporating the Honeywell HIH9130 temperature humidity sensor, transmits highly accurate temperature and humidity samples at user-defined intervals.

The on-board temperature sensor is rated for -25°C to 85°C or -13°F to 185°F and the humidity sensor is rated for 0 to 100% RH. It can be powered by just 2 AA batteries and an operational lifetime of 500,000 wireless transmissions.Battery life can be extended upto 10 years depending on environmental conditions and the data transmission interval.  Optionally, this sensor may be externally powered.

With an open communication protocol this IoT wireless temperature humidity product can be integrated with just about any control system or gateway.  Data can be transmitted to a PC, a Raspberry Pi, to Microsoft Azure® IoT, or Arduino. Sensor parameters and wireless transmission settings can be changed on the go using the open communication protocol providing maximum configurability depending on the intended application.

The long range, price, accuracy, battery life and security features of Long Range Wireless Temperature Humidity Sensor makes it an affordable choice which exceeds the requirements for most of the industrial as well as consumer market applications.

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/Zigmo.png)
# Long Range Wireless Mesh Modem with USB Interface
- **Zigmo Wireless Communication**
Mesh Networking is simply the hottest wireless technology of our time period. It’s fast, it’s very easy to use, highly reliable, and self healing. Three components are required for the ZigBee Mesh Network, the Coordinator (C), the Router (R) and the Endpoint (E). Your computer can speak to a ZigBee Mesh Network using a Coordinator. Think of the Coordinator as the interface to a Wireless Mesh Network. NCD Coordinators are equipped with a USB Interface. This Zigmo mounts as a Serial Port on your computer, and you will develop software that sends Serial commands at 115.2K Baud. The primary job of a router is to bridge the wireless gap between your computer (the Coordinator) and the device (Endpoint). If the Coordinator cannot speak to the Endpoint device because it is out of range, a Router can be used to bridge the two devices together. Endpoints are simply devices. With regard to NCD products, Endpoints can be relay controllers, data collection devices, PWM devices, and much more.

# Resources Required
- [IoT Long Range Wireless Temperature Humidity Sensor](https://store.ncd.io/product/industrial-long-range-wireless-temperature-humidity-sensor/) with power source Battery Or External DC.
- [Zigmo/Router for PC](https://store.ncd.io/product/900hp-s3b-long-range-wireless-mesh-modem-with-usb-interface/)
- PC/Laptop with an OS installed or Any IoT Embedded Device.

# Setting up Node-Red.
The sensor and Zigmo/Router come pre-programmed and work out of the box. In this section we will setup a sensor and Zigmo link and start receiving data on our PC
# Steps to install NODE-RED
Now that you have sensors running, we need a way to do something useful with that data.
- First of all you'll have to install [Node-RED](https://nodered.org/docs/getting-started/installation). 
- Once that’s done, you’ll need to enter your command line, or Power Shell for Windows users, navigate to the directory Node-RED is installed in.
- Now type **“npm i ncd-red-wireless node-red-dashboard“**. This will install the nodes required to receive data from your wireless sensors and you can start Node-RED once this is done.
- To start node server write **node-red** in the command prompt or terminal and press enter.

# Setting up the nodes
Assuming at this point you’ve started up Node-RED, you should be able to open a browser and navigate to http://localhost:1880, this will open up the flow builder that is the heart of the Node-RED experience.

**Steps to build the flow**

- **At this point you’ll be viewing a large blank flow with a long list of nodes on the left hand side, this sidebar is called the palette.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/blankpage.JPG)

- **Go ahead and drag a Wireless Gateway node over to your flow canvas to get started.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step1.JPG)

- **ncd-red-wireless**
Provides the nodes that manage the serial connection, parse incoming sensor data, filter it by specific parameters, and allow you to configure the wireless sensors.

# Finding your wireless sensors
Once you’ve added the node you’ll be able to view the info tab, which contains information about the node’s functionality, this tab is well populated for most node-red packages and contains valuable information, many times you will not need to view any other documentation outside of the info tab, so keep it in mind while you are building your flows if you have a question about how a node works. The next thing we need to do is configure the node, when you first add it you’ll notice that there is a small triangle on the top right corner next to a blue dot, the triangle indicates that the node needs additional configuration, the blue dot indicates that the node has not yet been deployed as part of the flow.

- **Double click on the node to open up the configuration options.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step2.JPG)

- **Click on the pencil icon next to the Serial Device field to configure your USB router, this will open a second configuration panel that only has a few options.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step3.JPG)

- **Click on the magnifying glass next to the Serial Port field and select the port that corresponds with your router, then click the “Add” button on top. The Serial Device field will now be populated based on that selection, and you can click “Done”, you now have direct access to your wireless sensors! To view the data coming in.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step4.JPG)

- **Now go back to your palette and type “debug” into the search field at the top, grab one of these nodes and drag it to the right of your Wireless Gateway.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug%20step1.JPG)

- **Double click on it and change “msg.” to “complete msg object” click done.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug%20step2.JPG)

- **Now draw a line between the two nodes, and click “Deploy” on the top right of the window..**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/deploy.JPG)

# Working with the data
Now out of your wireless sensors data is gathered and it is output to the “debug” tab, this "debug tab" is placed within the right sidebar subsequent to the information tab. To see the information are available in to hit the reset button. In node-red records is surpassed among nodes in a json packet. When the msg object comes into the debug tab you may make bigger it to view the overall list of information that comes with it. This is extraordinarily useful in case you need to quickly see which sensors are checking in. The other issue this node gives is a easy way to interchange your router to the network identity that devices in configuration mode document on, simply hit the button on the left of the node and the tool will switch to the configuration network, hit it once more to return it to listening mode. Once we get the wi-fi tool nodes set up, they may be set to routinely configure a sensor whilst it enters configuration mode, so it’s always available to maintain such a gateway nodes present at the flow for speedy configuring a device.

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/GatewayJson.png)

# Adding the wireless sensors
we need to separate wireless sensor records domestically in order that we are able to display it, we could use a switch node to split out the messages from the gateway based totally on the mac address with or sensor type, but as i referred to, the wireless nodes truly incorporate extra functionality for configuring the sensors, so we’ll start with them to give you a extra entire image of how those structures can work. In case you haven’t already seen packets coming in from both of your sensors, cross in advance and hit the reset button on the only that hasn’t stated. While a sensor assessments in thru any serial device configuration node, the mac address and kind of sensor is cached in a pool so we are able to quick find it for the duration of this next step.

- **Grab a Wireless Node from the palette and drag it onto the flow, double click on it to get it configured.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/wirelessdevice%20step1.JPG)

- **Select the serial device from the drop down that you used for the Wireless Gateway, now click the magnifying glass next to “Mac Address” and select one of the available options.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/wirelessdevice%20step2.JPG)

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/wirelessdevice%20step3.JPG)

You’ll notice this automatically sets the sensor type for you, you can also give it a name to make it easier to identify. As noted in the info tab, the Serial Device for Config field is optional, and we won’t worry about it right now. The node you have just added effectively works as a filter on incoming sensor data, only passing through data for the mac address, or sensor type if no mac address is present.

- **Now go back to your palette and type “debug” into the search field at the top, grab one of these nodes and drag it to the right of your Wireless Gateway.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug_wirelessdevice_step1.JPG)

- **Double click on it and click done.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug_wirelessdevice_step2.JPG)

# Adding Function Nodes
The function node is used to run JavaScript code against the msg object. The function node accepts a msg object as input and can return 0 or more message objects as output. This message object must have a payload property (msg.payload), and usually has other properties depending on the proceeding nodes.

- **Now grab a “function” node from the palette, and place it to the right of the Temp/Hum node.**

 ![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/temperature_function_node_step1.JPG)

- **Double click on the node to open up the configuration options.**

Here you have to write little javacript code to create a condition,so the temperature and humidity values will be written in the excel. 

 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/function_node_step2.JPG)
 
 - **Now grab a CSV node from the palette and place it to the right of the function node, it will convert the values csv format i.e comma seperated values.**
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/csv_node_step1.JPG)
 
 - **Now double click on it and type the column names seperated by comma and output as "a message per row" as show in the picture below.**
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/csv_node_step2.JPG)
 
 - **Now go back to your palette and type “file” into the search field at the top, grab one which shows "Writes msg.payload" to store the values and place it right to the csv node.You can also attach the debug node to check the out of the file node.**
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/output_file_node_step1.JPG)
 
 - **Double click on it to edit file node, enter the file name where you want to store the values as shown in the figure.**
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/output_file_node_step2.JPG)
 
 - **Now connect all the wires and click on the deploy button.**
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/final_wire_connection.JPG)
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/final_flow.JPG)
 
 # OUTPUT
 - **Now you can check the excel ouput.**
 
 ![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/output.JPG)
 
 # Also there is another way to send the data to excel by using "JSON" node and "excel" node.
 
 - First of all close the terminal or command prompt if you were doing with the above method. 
 - Then you have to install excel node to store the data.
 - So you’ll need to enter your command line, or Power Shell for Windows users, navigate to the directory Node-RED is installed in.
 - Now type **“npm install node-red-contrib-excel“**. This will install the **"excel"** node required to store data from your wireless     sensors and you can start Node-RED once this is done.
 - To start node server write **node-red** in the command prompt or terminal and press enter.
 - Now open a browser and navigate to http://localhost:1880 to open the flow builder.

# Now the steps are same upto adding the wireless sensor.

- So build the flow same as shown above upto adding wireless sensor. 

- **Then grab the json node from the palette and place it right to the Temperature/Humidity node.**

![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/json_step1.JPG)

- **Double click on it edit json node, edit it as shown in the picture below and click done.**

![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/json_step2.JPG)

- **Now grab the "excel" node that you have installed from the palette and place it to the right of "json" node.**

![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/excel_step1.JPG)

- **Double click on it to enter the file name where you want to store the temp/hum data and click done.**

![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/excel_step2.JPG)

# OUTPUT

![alt tag](https://github.com/rjrajbir/Sending-data-of-Wireless-Temperature-and-Humidity-Sensor-to-Excel/blob/master/excel_output.JPG)

But the limitation with excel node is that it overwrites the data in a single row.
