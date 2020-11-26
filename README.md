# Integrate Everything into IOTA Hackathon project submission.
![cover](https://github.com/ggreeve/IOTA-Trust-Drinking-Water/blob/main/images/cover.png/?raw=true)
## Personal Introduction
I am a Controls Engineer that designs, configures and integrates industrial control systems to include PLC's amd SCADA systems. I have been following the IOTA Foundations Tangle project for a few years now and find the technology fascinating. I was immediately attracted to this project since it requires no fees to interacting with their Distributed Ledger Technology called the Tangle, there are so many use cases that require micro payments and DLT, IOTA makes this possible. 

## Goal
Introduce Node-Red to the IOTA community, Node-Red was developed by IBM with IoT in mind. If you are a non-coder and would like to build your own Proof-of-Concept to interact with the Tangle this will be of of great interest to you.
You can literally integrate everything into IOTA using node-red since thousands of pre build nodes exist to communicate with various devices from Industrial controllers to home automation.

I am not a coder, but I have been able to successfully run some home automation and small IoT projects on [Node-Red](https://nodered.org/).
This hackathon gave me the motivation to attemp my first IOTA project. I always had a use case in mind that I wanted to implement using IOTA. 
With the release of IoT2Tangle's [Streams-http-gateway](https://github.com/iot2tangle/Streams-http-gateway) allowing for simple http interaction between Node-Red and the IOTA Tangle using IOTA Streams this goal was now within reach.
I am now able to show that a non-coder / tinkerer like me can do some pretty cool stuff with a Raspberry Pi, Node-Red and the IOTA Tangle

## Showcase
My project will integrate with an industrial water analyzer topically used in drinking water systems to measure water quility. This device allows the connection of multiple sensors/probes to meausure, for instance pH Chlorine and ORP.
Since not many people have access to Industrial equipment I build the application to insert a few static fields for testing and integration with your own equipment. There exists many node to import for communication with devices over MQTT, WiFi, Bluethooth Ethernet and Modbus-TCP
A Raspberry Pi will be used to run the Node-Red platform executing the following tasks.
* Sending sensor data to the IOTA Tangle using [IOTA Streams](https://github.com/iotaledger/streams)
* Have the device be its own “Economic Agent” with and IOTA wallet  so that it can receive payment from interested parties in exchange for the sensor      data stored on the tangle.
* Since this instrument can detect a probe calibration event it can then also send payments to humans for the calibration service it received.
* Issue the device a Decentralized Digital identity. DiD using [IOTA Identities](https://github.com/iotaledger/identity.rs)
* Utilize Verifiable Credentials, the service company can attach a VC to the sensors DiD to certify that the probes have been calibrated and the data reaching the tangle is accurate. Any entity interested in the data can then also verify the accuracy of the data by querying the history of the senors VC showing all past calibration certificates. 
Now we can truly have trust and transparency on the water quality data available

## Video Demo
[Video demonstration](https://youtu.be/w490AOxwYBI)

## Short Node-Red introduction video [https://www.youtube.com/watch?v=vYreeoCoQPI](https://www.youtube.com/watch?v=vYreeoCoQPI)


## FOR A STEP-BY-STEP GUIDE HAVE A LOOK AT THE [WIKI](https://github.com/ggreeve/IOTA-Trust-Drinking-Water/wiki)


## Software requirements

* [Node-Red](https://nodered.org/) Low-code programming tool.
* [Streams-http-gateway](https://github.com/iot2tangle/Streams-http-gateway) Rust based Streams implementation to send messages to the Tangle.
* [Keepy](https://github.com/iot2tangle/Keepy) A Nodejs Streams Gateway Keeper.

## Bill of materials

* Raspberry Pi, I used a RPi 3B+



