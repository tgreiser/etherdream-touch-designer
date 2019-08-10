# Laser control code and examples for Ether Dream and TouchDesigner

## Intro

[Ether Dream](http://ether-dream.com/) is an open source [DAC](https://en.wikipedia.org/wiki/Laser_projector#Controller_.28DAC.29) for controlling laser animations via [ILDA](http://www.laserfx.com/Backstage.LaserFX.com/Standards/ILDAframes.html). We will use [TouchDesigner](https://www.derivative.ca/) to generate the control signals for the Ether Dream, which will output them to our ILDA compatible laser scanner.

## Getting Started

If you want to learn more about the basics, start with our presentation, [#LaserHack 101](https://github.com/tgreiser/etherdream-touch-designer/raw/master/laser_hack_101.pdf).

You can hook your Ether Dream directly to your computer with a regular ethernet cable. Run the ["sitter" diagnostic tool](http://ether-dream.com/downloads.html) to get the IP address. You will need to enter this IP into the Ether Dream CHOP in TouchDesigner in order to enable laser output.

![Setup Diagram](https://raw.githubusercontent.com/tgreiser/etherdream-touch-designer/master/ether_dream_connections.png)

## Setup

1. Lasers are dangerous to your vision if used incorrectly. Use safety glasses and common sense. Think about what your projection may be doing and where to safely set up your scanner.
2. Laser scanners all have ratings for the galvos. This will be something like: 
  Scanner: 30K PPS @ 8°
  Scan Angle max.: 40° max
3. 30kpps means 30,000 Points Per Second. This rating is only a guideline, and complex shapes at close to the recommended scan angle may perform better at a reduced scan rate.
4. Start the project in TouchDesigner with your laser turned off or in safe mode.
5. In TouchDesigner, set the sample rate on the CHOP network to at or below the max scan rate. In general you probably want to draw shapes at maybe 50% scale, and only scale it up if you know things work at a smaller size.
6. Once you have set the sample rate, you can start the laser. If you hear a loud whining noise coming from your galvos you need to reduce the sample rate or scale.

[![Laser Kung Fu](http://img.youtube.com/vi/uXsIaUebKx4/0.jpg)](http://www.youtube.com/watch?v=uXsIaUebKx4 "Laser Kung Fu")
[![Kinect Trace](http://img.youtube.com/vi/CZ1Ek5ifigc/0.jpg)](http://www.youtube.com/watch?v=CZ1Ek5ifigc "Kinect Trace")
[![Experiments](http://img.youtube.com/vi/2xt8s92Lp-g/0.jpg)](http://www.youtube.com/watch?v=2xt8s92Lp-g "Experiments")
[![Laser Pong](http://img.youtube.com/vi/c3P6thmMLx0/0.jpg)](https://www.youtube.com/watch?v=c3P6thmMLx0 "Laser Pong")


Resources:
* EtherDream example by Derivative - http://derivative.ca/Forum/viewtopic.php?f=20&t=8114&p=30561
* LaserFire by higa - http://derivative.ca/Forum/viewtopic.php?f=22&t=8365&p=31829
* ILDA Tutorial (ofx related, but good general info) by Memo Akten - https://github.com/memo/ofxIlda/wiki
* Accurate and Efficient Drawing Method for Laser Projection by Purkhet Abderyim, Osama Halabi, Tadahiro Fujimoto, Norishige Chiba - http://www.art-science.org/journal/v7n4/v7n4pp155/artsci-v7n4pp155.pdf
