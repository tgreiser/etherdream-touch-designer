# Laser control code and examples for Ether Dream and TouchDesigner

## Intro

[Ether Dream](http://ether-dream.com/) is an open source [DAC](https://en.wikipedia.org/wiki/Laser_projector#Controller_.28DAC.29) for controlling laser animations via [ILDA](http://www.laserfx.com/Backstage.LaserFX.com/Standards/ILDAframes.html). We will use [TouchDesigner](https://www.derivative.ca/) to generate the control signals for the Ether Dream, which will output them to our ILDA compatible laser scanner.

## Getting Started

You can hook your Ether Dream directly to your computer with a regular ethernet cable. Run the ["sitter" diagnostic tool](http://ether-dream.com/downloads.html) to get the IP address. You will need to enter this IP into the Ether Dream CHOP in TouchDesigner in order to enable laser output.

## Setup

1. Lasers are dangerous to your vision if used incorrectly. Use safety glasses and common sense. Think about what your projection may be doing and where to safely set up your scanner.
2. Laser scanners all have ratings for the galvos. This will be something like: 
  Scanner: 30K PPS @4°
  Scan Angle max.: 40° max
3. 30kpps means 30,000 Points Per Second. This rating is at a small animation size (4 degrees), if you are using closer to the max angle, your scan rating will be more like half, 15K PPS in this example. Start the project in TouchDesigner with your laser turned off or in safe mode.
4. In TouchDesigner, set the sample rate on the CHOP network to 80% of the safe scan rate you figured out for your scanner in step 3. Say we are doing a large animation and using the 15,000 PPS number above - 15,000 * .80 = 12,000
5. Once you have set the sample rate, you can start the laser. If you hear a loud whining noise coming from your galvos you need to reduce the sample rate.

[![Laser Kung Fu](http://img.youtube.com/vi/uXsIaUebKx4/0.jpg)](http://www.youtube.com/watch?v=uXsIaUebKx4 "Laser Kung Fu")

Resources:
* EtherDream example by Derivative - http://derivative.ca/Forum/viewtopic.php?f=20&t=8114&p=30561
* LaserFire by higa - http://derivative.ca/Forum/viewtopic.php?f=22&t=8365&p=31829
* ILDA Tutorial (ofx related, but good general info) by Memo Akten - https://github.com/memo/ofxIlda/wiki
* Accurate and Efficient Drawing Method for Laser Projection by Purkhet Abderyim, Osama Halabi, Tadahiro Fujimoto, Norishige Chiba - http://www.art-science.org/journal/v7n4/v7n4pp155/artsci-v7n4pp155.pdf
