
**Final Documentation and Description of the Project*

**What We Did**
 
In our project we did a Bike Security system connected over cellular Network. The device notifies you when your bicycle has been stolen or tampered with.  A built in accelerometer reads for changes in the acceleration thresholds and triggers a notification that will be sent to your phone. The system includes a GPS module, so when someone tries to steal your bike, you will know when it is being taken, and where is it going. Create a device that will notify you when someone is trying to steal your bike, based off changes in acceleration. When Bikeguard detects movement it will Text you notifying you that that there has been unusual activity. The device gathers readings from the accelerometer, and by linking it to IFTTT it sends back a notification to the user. The text contains an alert, and a link to google maps.
 
**How We Did it
 
We Accomplished this by using Particle Asset Tracker kit, which contains a electron and a asset tracker shield, which contains a Adafruit GPS and an accelerometer onboard. So essential our code, publishes any detection in movement and sends an alert with GPS coordinates which then trigger the IFTTT message. We programmed the Particle so that when it got a read from the accelerometer, (past a certain threshold) it publishes an event in particle´s website. This event triggers IFTTT to send a message that contains the location of the device by reading the latitude and longitude from the the GPS. 

What We learned along the way
 
Along the way we learn an incredible amount, we learn how to use boolean expressions, Char functions, write firmware, and reference Liberals also because Particles GPS library doesn't work, we learned about alternative libraries people at wrote and tried are best to integrate them
into out code 
 
**What We would do differently

I/we will try to not use Particle every again, for one there instructions are horrible and 2 they literally sell products that don't work like they claim to. Also I think I would do a simpler project next time and focus less on the concept and more on writing code
 
A description of the 5 most difficult problems WE had and how We overcame them

Getting the GPS to work properly 
Understanding code we never learned in class
Connecting it to IFTTT
Getting It to publish the write data to the console and then to IFTTT
Getting it to publish to only once and not continuously 


**CODE**

#include "AssetTracker.h"

int transmittingData=1;

long lastPublish=0 ;


int accelThreshold = 20000;

AssetTracker t = AssetTracker();

void setup() {
    t.begin();

    t.gpsOn();

    Serial.begin(9600); 
}

void loop() {
    if (t.readXYZmagnitude() > accelThreshold) {
    
        String pubAccel = String::format("%d,%d,%d", t.readX(), t.readY(), t.readZ());

        Serial.println(t.readXYZmagnitude());

            lastPublish = millis();
            Particle.publish("A", pubAccel, 60, PRIVATE);
            
   
     t.updateGPS();

            if (transmittingData) {
            
                Particle.publish("G", t.readLatLon(), 60, PRIVATE);
            }
      
            Serial.println(t.readLatLon());
            
        }
}

References

1. This helped us understand how/ why the gps was not working https://community.particle.io/t/is-your-project-related-to-asset-tracker/15590

 2. We used this for reference 
https://github.com/spark/AssetTracker

3. Also we used this to understand our problems with the GPS
https://community.particle.io/t/asset-tracker-accelerometer-gps-problem/20602

4. This helped to 
https://community.particle.io/t/asset-tracker-gps-your-experience-with-getting-gps-fix/21948

5. This helped us understand how/ why the gps was not working 
https://community.particle.io/t/asset-tracker-gps-your-experience-with-getting-gps-fix/21948



