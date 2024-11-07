# Connect Raspberry Pi Pico W to AWS IoT Core

This project demonstrates how to connect a Raspberry Pi Pico W to AWS IoT Core using MicroPython and MQTT.

## Project Requirements

- **Hardware**
  - Raspberry Pi Pico W x1
  - Push buttons x4
- **Software**
  - [AWS IoT Core](https://us-east-2.console.aws.amazon.com/iot/home?region=us-east-2#/home)
  - MicroPython
  - Thonny IDE

## Overview

Using AWS IoT Core’s message broker, this setup enables secure message transmission between AWS IoT Core and the Pico W. 

The application:
- Publishes button status to the `picow/button` topic when buttons are pressed or released.
- Subscribes to the `pico/led` topic to control the Pico W’s onboard LED based on received messages (`on`, `off`, `toggle`).

---

## Hardware Setup

1. Connect each button between the **GND** and **GP3** pins on the Raspberry Pi Pico W.

---

## AWS IoT Core Setup

1. **Create an AWS Account and Access IoT Core**
   - Sign in to AWS, search for **IoT Core**, and open it.

2. **Configure Policies**
   - Go to **Security** > **Policies** and create a policy to control access.
   - Add the necessary policy actions, including the ability to publish and subscribe.
   - [AWS IoT Core Policies Documentation](https://docs.aws.amazon.com/iot/latest/developerguide/iot-policies.html)

3. **Register Your Device**
   - Go to **All devices** > **Things** > **Create thing** to register your Pico W device.
   - Name the thing and generate a new certificate for authentication.
   - Download the certificates for later use.

4. **Endpoint Configuration**
   - Under **Settings**, note the **Endpoint** URL, as it will be used to set up the MQTT connection.

---

## Code Setup

1. **Upload Certificate and Key Files**
   - In **Thonny IDE**, navigate to `View -> Files` and locate the AWS IoT Core certificate and key files you downloaded earlier. 
   - Upload them to the Pico W using `Upload to /`.

2. **Update Code with AWS Information**
   - Use the AWS IoT Endpoint URL and certificate filenames in your MicroPython code to configure the MQTT client.
  
3. **Download the mainAWS.py file**
  - Move to Raspberry Pico or prefered location in Computer and open in Thonny.
  - Run script.
    
---

