# Automotive_UI
<html>
	<head></head>
	<body>
	<ol>
		<li></li>
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
		<p>After writing the image to the SD card, it is time to boost up our Pi Operating System. First, we need to do some configuration if you want your Pi to be able to work remotely.
			<ul>
				<p><li>Open the terminal and type in: <h5>sudo raspi-config</h5></li></p>
			</ul>
		</p>
		<li><h3>PCB/Soldering</h3></li>
		<li><h3>Power Up and Production Testing</h3></li>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Pi_Measure.png?raw=true' width='50%' height='50%'/></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/Sensor_Measure.png?raw=true' width='50%' height='50%'/></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/PCB_PowerUp_Pi.png?raw=true' width='50%' height='50%' /></p>
		<p align='center'><img src='https://github.com/qu0cquyen/Automotive_UI/blob/master/images/PCB_PowerUp_Code.png?raw=true' width='50%' height='50%'/></p>
		<li><h3>Enclosure</h3></li>
	</ol>
	</body> 
</html> 
