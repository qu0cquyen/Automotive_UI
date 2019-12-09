# Automotive_UI
<html>
	<head></head>
	<body>
	<ol>
		<li><h3>System Diagram</h3></li>
		<li><h3>Budget</h3></li>
		<p>To implement this project. There are some components and equipments are used: 
					<table>
						<tr><td>Raspberry Pi 4 - 32GB SDCard</td><td align="right">CDN$ 134.99</td></tr>
						<tr><td>ADS1015 Converter</td><td align="right">CDN$ 33.89</td></tr>
						<tr><td>Pulse Sensor</td><td align="right">CDN$ 48.43</td></tr>
						<tr><td>Customized PCB</td><td align="right">CDN$ 28.7</td></tr>
						<tr><td>Headers </td><td align="right">CDN$ 33.9</td></tr>
						<tr><td>Customized Enclosure</td><td align="right">CDN$ 30.00</td></tr>
						<tr><td>Total</td><td align="right">CDN$ 308.82</td></tr>
					</table>
			The total price is assumed that we do not possess any components aside from Standley tool kit (included jumper wires)
		</p>
		<li><h3>Time Commitment</h3></li>
		<p align='center'><img src="https://i.ibb.co/w6kB6XZ/download.png"></p>
		<p>
		&emsp;&emsp;This time commitment is writtent based on the assumption of not having any components except the tool kit and no experience of PCB designing. The total amount of time to accomplish this project is approximately 31 hours. This included waiting time for all components and equipments are shipped and gathered. For some side-work such as Project Selection (30 minutes), Proposal, Meeting and Budget will take roughly one to two hours to finish each of them. </p>
		<p>&emsp;&emsp;Fritzing software is used to design the Breadboard and PCB. Both designs are pretty straight forward, all we need to do is to properly wire up all the components. However, the software does not include Hearbeat sensor and ADS1015 converter. You can download these 2 components for Fritizing with this links: 
		<ul>
			<li><a href='https://raw.githubusercontent.com/adafruit/Fritzing-Library/master/parts/Adafruit%20ADS1015%2012Bit%20I2C%20ADC.fzpz'>ADS1015</a></li>
			<li><a href='https://raw.githubusercontent.com/WorldFamousElectronics/Fritzing_PulseSensor_Files/master/Pulse%20Sensor.fzpz'>Pulse Sensor</a></li>
		</ul>
		In additional, there are two things we need to adjust for the PCB design are the size of Vias and Wires, 0.9 and 16 mil accordingly. This process should take around 4 hours. A personal design can be found from this <a href='https://github.com/qu0cquyen/Automotive_UI/blob/master/electronics/Project_Fritzing.fzz'>link</a>. </p>
		<p>&emsp;&emsp;After having both designs are done, next all the necessary components will be hooked up on the breadboard first based upon the breadboard designed which is done on Fritizing. The amount of time should be spent on this process is 30 minutes to 1 hour. </p>
		<p>&emsp;&emsp;Once we have everything ready up to this point, building an enclosure for our components will be our next step. Personally, this can be seen as the most annoyed process in the whole project; apart from coming up with a design which can cover all the parts of our components, we also need to have a inctricate design in order to fit in all the parts together. In this process I spent about 21 hours for both designing and 3D printing the enclosure. During the process, I used school and 3rd-party 3D printing service outside the school to accelerate my process. There is a number of faulty designs have been made due to mistaking measurements, therefore, I would recommend that you should research or ask experts who are able to give some suggestions in details measurement, if you want all the parts of the enclosure can perfectly fit to each other.</p>
		<li><h3>Mechanical Assembly</h3></li>
		<p>In order to get the reading from the sensor. There are several steps we should take to create our development platform.</p>
		<h4>Step 1: Download and Install IOS for Raspberry Pi.</h4>
		<p>The image that we are going to use for our Pi is Raspbian. You can download from this <a href='https://downloads.raspberrypi.org/raspbian_full/images/raspbian_full-2019-09-30/2019-09-26-raspbian-buster-full.zip'>link</a></p>
		<p>Aside from downloading the image, we also need to download another software which helps to write the image to a SD card and this card is used by the Raspberry Pi.  You can download from here: https://www.balena.io/etcher/</p>
		<p align='center'><img src="https://i.ibb.co/fGg0bcV/animated.gif" alt="animated" border="0"></p>
		<h4>Step 2: Boost up Operating System</h4>
		<p>After writing the image to the SD card, it is time to boost up our Pi Operating System. First, we need to do some configuration if you want your Pi to be able to work remotely.</p>
		<p>&emsp;&emsp;- Open the terminal and type in: <b>sudo raspi-config</b></p>
		<p align='center'><img src="https://i.ibb.co/bFTySSz/Fig-10.jpg" alt="Fig-10" border="0"></p>
		<p align='center'><img src="https://i.ibb.co/PDCvr5X/Fig-11.jpg" alt="Fig-11" border="0"></p>
		<p>&emsp;&emsp;&emsp;&emsp;Enable SSH, VNC and I2C features</p>
		<p>&emsp;&emsp;- Next we will set up the WIFI: </p>
		<p>&emsp;&emsp;&emsp;&emsp;In the terminal type in: <b>sudo nano /etc/wpa_supplicant/wpa_supplicant.conf</b></p>
		<p>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Types in the following lines: </p>
		<p>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;<b>network={<br/>
		&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;ssid="YOUR WIFI NAME"<br/>
		&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;password="WIFI PASSWORD"<br/>
		&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;priority=999<br/>
		&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;}</b></p>
		<p>&emsp;&emsp;Notice the "priority" line, when you implement this line the Raspberry Pi will look for the network which has the highest priority first to connect, if the network is not avaiable it will automatic connect to any network that has accessed before.</p>
		<h4>Step 3: Assemble our components to Pi: </h4>
		<p align='center'><img src='https://raw.githubusercontent.com/qu0cquyen/Automotive_UI/master/images/ADS1105noPi_bb.png'  width='50%' height='50%'/></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Breadboard_Demo.png?raw=true' width='50%' height='50%' /></p>
		<h4>Step 4: Coding</h4>
		<p>&emsp;&emsp;You can refer to the code fragment from here: https://github.com/udayankumar/heart-rate-raspberry-pi. Code is written by using Python language.</p>
		<h4>Step 5: Result</h4>
		<p>&emsp;&emsp;If you are flowing those steps above, you should be able to get the reading from the sensor.</p>
		<p align='center'><img src='https://raw.githubusercontent.com/qu0cquyen/Automotive_UI/master/images/Figures.PNG' width='50%' height='50%' /></p>
		<li><h3>PCB/Soldering</h3></li>
		<p align='center'><img src='https://raw.githubusercontent.com/qu0cquyen/Automotive_UI/master/images/ADS1105noPi_pcb.png' width='50%' height='50%'/></p>
		<li><h3>Power Up and Production Testing</h3></li>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Pi_Measure.png?raw=true' width='50%' height='50%'/></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Sensor_Measure.png?raw=true' width='50%' height='50%'/></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/PCB_PowerUp_Pi.png?raw=true' width='50%' height='50%' /></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/PCB_PowerUp_Code.png?raw=true' width='50%' height='50%'/></p>
		<li><h3>Enclosure</h3></li>
		<p>&emsp;&emsp;To design the Enclosure, you can use either Sketchup or Tinkercad to desgin your own enclosure. After your design is done, you should generate a .STL file and feed to Cura - A software which is used for 3D printing purpose. Cura will provide us an insight information what need to be used/done in order to print out the real case. When you finish revewing configuration information, Cura can help you export a .G file which is used for 3D printer to continue printing our work. The printing process usually takes up around from 2 upto 8 hours depends on your design. Finally, when we have our case is properly printed, it is time to put our components into the enclosure. The images below is my personal enclosure. <b>Notice: There is still some minor mistakes, please reconsider if you are going to use this design.</b> You can find my design files here:
			<a href='https://github.com/qu0cquyen/Automotive_UI/blob/master/mechanical/Final_Bottom_Case_Enclousre.stl'>Bottom</a>
		<a href='https://github.com/qu0cquyen/Automotive_UI/blob/master/mechanical/Final_Middle_Case_Enclosure.stl'>Top</a></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Enclosure_1.png?raw=true' width='50%' height='50%'/></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Enclosure_2.png?raw=true' width='50%' height='50%'/></p>
	<li><h3>Reference: </h3></li>
	https://www.balena.io/blog/etcher-now-with-multi-write-and-compute-module-support/
	https://www.digikey.com/en/maker/blogs/2018/how-to-boot-to-command-line-and-ssh-on-raspberry-pi
	</ol>
	</body> 
</html> 
