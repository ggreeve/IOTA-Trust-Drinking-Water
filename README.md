# Integrate Everything into IOTA Hackathon project submission.
![cover](https://github.com/ggreeve/IOTA-Trust-Drinking-Water/blob/main/images/cover.png/?raw=true)
## Personal Introduction
I am a Controls Engineer that designs, configures and integrates industrial control systems to include PLC's and SCADA systems. I have been following the IOTA Foundations Tangle project for a few years now and find the technology fascinating. I was immediately attracted to this project since it requires no fees to interacting with their Distributed Ledger Technology called the Tangle, there are so many use cases that require micro payments and DLT, IOTA makes this possible. 

## Goal
Introduce Node-Red to the IOTA community, Node-Red was developed by IBM with IoT in mind. If you are a non-coder and would like to build your own Proof-of-Concept to interact with the Tangle this will be of of great interest to you.
You can literally integrate everything into IOTA using node-red since thousands of pre build nodes exist to communicate with various devices from Industrial controllers to home automation.

I am not a coder, but I have been able to successfully run some home automation and small IoT projects on [Node-Red](https://nodered.org/).
This hackathon gave me the motivation to attemp my first IOTA project. I always had a use case in mind that I wanted to implement using IOTA. 
With the release of IoT2Tangle's [Streams-http-gateway](https://github.com/iot2tangle/Streams-http-gateway) allowing for simple http interaction between Node-Red and the IOTA Tangle using IOTA Streams this goal was now within reach.
I am now able to show that a non-coder / tinkerer like me can do some pretty cool stuff with a Raspberry Pi, Node-Red and the IOTA Tangle

## Showcase
My project will integrate with an industrial water analyzer typically used in drinking water systems to measure water quility. This device allows the connection of multiple sensors/probes to meausure, for instance pH Chlorine and ORP.
Since not many people have access to Industrial equipment I build the application to insert a few static fields for testing and integration with your own equipment. There exists many node to import for communication with devices over MQTT, WiFi, Bluethooth Ethernet and Modbus-TCP
A Raspberry Pi will be used to run the Node-Red platform executing the following tasks.
* Sending sensor data to the IOTA Tangle using [IOTA Streams](https://github.com/iotaledger/streams)
* Have the device be its own “Economic Agent” with and IOTA wallet  so that it can receive payment from interested parties in exchange for the sensor      data stored on the tangle.
* Since this instrument can detect a probe calibration event it can then also send payments to humans for the calibration service it received.
* Issue the device a Decentralized Digital identity. DiD using [IOTA Identities](https://github.com/iotaledger/identity.rs)
* Utilize Verifiable Credentials, the service company can attach a VC to the sensors DiD to certify that the probes have been calibrated and the data reaching the tangle is accurate. Any entity interested in the data can then also verify the accuracy of the data by querying the history of the senors VC showing all past calibration certificates. 
Now we can truly have trust and transparency on the water quality data available

## Why did I use Decentralized Identifiers and Verifiable Credentials in my project?

To insure trust in sensor data.
Recently there has been a movement to secure valuable data by utilizing Distributed Ledger Technology for trust and transparacy.

As an example Walmart recently issued a mandate to all its suppliers of leafy greens stating that they have to utilize “Blockchain” for proving its supply chain history.

The idea is that the data is stored immutably and open to the regulatory agencies and the public.
But storing the data on a DLT is creating a false sense of trust.

We know the data is immutable, but how do we know the data was accurate before storing it on the DLT?  We do not.
There is no way to proof that for example a IoT temperature sensor in a refrigerated food truck is storing accurate temperature readings on the DLT. What if the sensors is reporting just 2 degrees lower than actual?
It could be a life or death difference...
Looking at the data on the DLT then does not proof that the truck remained within the temperature range as expected and so you have the garbage-in-garbage-out problem.

There is a solution to the problem:

Decentralized Identifiers and Verifiable Credentials. https://www.w3.org/TR/did-core
For these critical IoT sensors a unique identifier can be issued to them using “DID” Decentralized Identifiers and now that the sensors are uniquely identified we can also attach VC’s, Verifiable Credentials to them. 
A certified company can take scheduled readings alongside the IoT sensor with lab certified temperature probes, maybe on quarterly basis, if the live data that the IoT sensor has attached to the DLT matches their instrument then they will issue a “certificates of accuracy” credential to the IoT sensor, only then can we be assured that the temperature of the truck is actually what is stored on the DLT.

Now that the sensor can present its Verifiable Credential ( proof of accuracy) we can be assured that the data is accurate. The complete history of all the accuracy certificates are linked to the IoT sensor in a decentralized manner.

![](https://i.imgur.com/IwDnfgj.png)

## Video Demo of my Project
* [Video demonstration of my project](https://youtu.be/w490AOxwYBI)

* Short Node-Red introduction video [https://www.youtube.com/watch?v=vYreeoCoQPI](https://www.youtube.com/watch?v=vYreeoCoQPI)


## FOR A STEP-BY-STEP GUIDE HAVE A LOOK AT THE [WIKI](https://github.com/ggreeve/IOTA-Trust-Drinking-Water/wiki)


## Software requirements

* [Node-Red](https://nodered.org/) Low-code programming tool.
* [Streams-http-gateway](https://github.com/iot2tangle/Streams-http-gateway) Rust based Streams implementation to send messages to the Tangle.
* [Keepy](https://github.com/iot2tangle/Keepy) A Nodejs Streams Gateway Keeper.

## Bill of materials

* Raspberry Pi, I used a RPi 3B+
* Water Analyzer from [Endress Hauser](https://www.us.endress.com/en/field-instruments-overview/measurement-technologies/liquiline-transmitter-analyzer-sampler-platform?gclid=CjwKCAiA5IL-BRAzEiwA0lcWYumwld-m1dVSxhPQw8XWeJgQqzHCC6X8vQFYTjOQBfdo0VVnnC5D-hoCPboQAvD_BwE)
* [pH Probe](https://www.us.endress.com/en/field-instruments-overview/liquid-analysis-product-overview/pH-digital-sensor-cps77d)

