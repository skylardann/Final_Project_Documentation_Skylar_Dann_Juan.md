Smart Bike Security System 
Final Project P&E
Team: Skylar, Juan  


**Summary**

The Bike Security system is a cellular connected device that notifies you when your bicycle has been stolen. The system includes a GPS module and a built-in accelerometer, so when someone tries to steal your bike, the motion sensor will be triggered, reporting location, orientation and movement to its user. The GPS will be activated once the accelerometer notices any changes in motion, and will then send you a message notifying you of unusual activity, this way you will be able to track your bike and retrieve it, or give the police the coordinates. 


**Component Parts**

3 months of Particle's 1MB monthly data plan (delivered by email)
Particle Electron PCB
Weatherproof Enclosure
Asset Tracker Shield PCB
Particle SIM Card
Li-Po battery (2000mAh)
USB cable
Breadboard
Pinout reference card





**Code**

Our code will have to perform the following operations:
Read a change in acceleration from the accelerometer 
Reading values from a GPS/Asset Tracker
Trigger a function by evaluating an inequality (change in acceleration)
Send GPS Location and alert message to a cellular device.
Activate through internet connection to Particle App. 

We will be creating thresholds of acceleration, that will trigger  “transmitMode”, which will trigger the sending of gps coordinates via text with a indicated delay, based on the amount of acceleration and the location of the GPS. 




**Links to example/reference code work in google doc**

ASSETTRACKER: Reference files and basic examples that we will need to build on 

Files

ASSETTRACKER.CPP

ASSETTRACKER.H

**Examples**

1_GPS_FEATURES.CPP
2_ACCELEROMETER.CPP

**Challenges**

It will be challenging to perform a synchronized transition of data from the different sensors and elements in our device. The main challenge will be to trigger a function based on readings of the accelerometer, and to find a threshold of acceleration that will be appropriate to trigger the alert. It will also be challenging to create a link between the device and the user's cellular connection. In the process we will also encounter issues  of connectivity, and range potential.




**Timeline**
Week 1: Write proposal, get approval, order the parts.
Week 2: Write code, and construct 
Week 3: Integrate all the components together and debug.
Week 4: Complete project, & present. 









