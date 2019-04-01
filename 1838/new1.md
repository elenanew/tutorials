---
title:  form 1
description: 111 description
primary_tag: products>sap-s-4hana-cloud-sdk
tags: [tutorial>intermediate, tutorial>license , tutorial:product/sapHana, products>sap-s-4hana-cloud-sdk]
time: 123
---

## Details
### You will learn  
Now that your IoT Services are collecting data and you were able to view it your deployed Java application, now how about redirecting the data to a shared SAP HANA XS instance and making a small SAP HANA XSC application to show the data.  



---

  **Example:code** 
```
let apples = 3
class TriangleAndSquare {
    var triangle: EquilateralTriangle {
        willSet {
            square.sideLength = newValue.sideLength
        }
```
***14Example:shell code** 
```shell
$ chmod a+x name.sh
$ ./name.sh Hans-Wolfgang Loidl
My first name is Hans-Wolfgang
My surname is Loidl
Total number of arguments is 2
```
***13Example: r code** 
```r
w = rnorm(500,0,1)  # 500 N(0,1) variates
v = filter(w, sides=2, rep(1/3,3))  # moving average
par(mfrow=c(2,1))
plot.ts(w, main="white noise")
plot.ts(v, ylim=c(-3,3), main="moving average")

# now try this (not in text):  
dev.new()  # open a new graphic device
ts.plot(w, v, lty=2:1, col=1:2, lwd=1:2)
```
***12Example:Python code** 
```python
"""This is a 
multiline docstring."""
print("Hello, World!")
```
## Prerequisites  
 - **Proficiency:** Beginner
 - **Tutorials:** [Internet of Things (IoT) Viewing your Tessel data from IoT Services](http://go.sap.com/developer/tutorials/iot-part9-hcp-services-viewdata.html)

## Next Steps
 - Select a tutorial from the [Tutorial Navigator](http://go.sap.com/developer/tutorial-navigator.html) or the [Tutorial Catalog](http://go.sap.com/developer/tutorials.html)




1. To be on the safe side go ahead and stop your `iotmms` Java application.


2. From within the cockpit now choose Databases & Schemas and create a new SAP HANA XS Shared instance.

    ![HANA instances](https://raw.githubusercontent.com/SAPDocuments/Tutorials/master/tutorials/iot-part10-hcp-services-hanaxs/1.png)

    ![HANA instances](https://raw.githubusercontent.com/SAPDocuments/Tutorials/master/tutorials/iot-part10-hcp-services-hanaxs/2.png)

3. Under the first one, our `XXXXXXtrial.iotmms.web` you’ll notice we have an existing binding in place. We need to remove that one. Then we will need to add the new binding to our new HANA XS (shared) instance.

4. Once you have that complete you will need to start your “IOTMMS” Java Application and send some data through your device which will then generate the proper tables in your HANA XS (shared) instance ([see tutorial](http://go.sap.com/developer/tutorials/iot-part7-add-device.html)). So provided you received the “200” status in your messages then we should now have data in our tables and can begin working on our XS application.

    ![bindings](https://raw.githubusercontent.com/SAPDocuments/Tutorials/master/tutorials/iot-part10-hcp-services-hanaxs/3.png)

5. Choose the “SAP HANA Web-based Development Workbench,” now right click on your package name, `XXXXXXXTrial`, and choose “New Application”. We’ll choose the “Blank Application” option and the “sub package” - `codejam.iotmmsxs`

    ![new application](https://raw.githubusercontent.com/SAPDocuments/Tutorials/master/tutorials/iot-part10-hcp-services-hanaxs/4.png)

6. Now we’ll want to create a new file in this new sub package called `iotmmsxs` called `.xsprivileges` (remember the . in the front)

	```
	 	{
		 	"privileges": [
		 		{
					"name":"Basic",
		 			"description":"Basic IoT MMS privilege"
				}  
		  	]
		}
	```

7. Now switch to the catalog view to determine the next values you will need.

    ![catalog](https://raw.githubusercontent.com/SAPDocuments/Tutorials/master/tutorials/iot-part10-hcp-services-hanaxs/5.png)

8. Now check under the `NEO_` schema, you will need to make a note of that specific schema name as you will need it in a moment. Under this schema you will find your tables. These are the tables created by the IoT Services for our devices.

   
