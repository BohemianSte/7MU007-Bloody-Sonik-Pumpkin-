# 7MU007-Bloody-Sonik-Pumpkin-


## Description

The Bloody Sonik Pumpkin is a novel distortion effect proccessor built within the open source software PureData. The effect of the unit is based around the idea of a 'reverse distortion' with the distortion only being triggered as the input signal descends below a designated threshold. The inspiration for the design came from a personal enjoyment of distortion as a concept as well as an interest into using distortion in new ways in order to aid the creative process.


## Table of Contents
  - Usage
  - Research
  - Development
  - Sources

## Usage

**_Important:_** The external libraries **Cyclone** and **Moonlib** **_must_** be installed in order to run this patch!

### Initial Setup
Instal the latest patch [Found Here](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/Bloody%20Sonik%20Pumpkin%20Version%205.pd.zip)

Before beginning please make sure to double check that PD is setup to work with your chosen interface by checking the audio input and output withing the PD preferences menu. Once PD is enabled and working with your chosen interface you may need to head into the subpatch entitled [pd don't look here] and once inside make sure the [adc~] object has the correct input for your device. 

### Using the Bloody Sonik Pumpkin
The Bloody Sonik Pumpkin operates around the idea of a distortion triggered by an audio signal descending beyond a chosen threshold, within the patch there is a choice of four presets which would be an ideal place to begin. Now depending on your chosen instrument you may want to tweak and fine tune the settings to your preference.
A detailed breakdown of usage along with examples of how it may be used can be found in the following video:

But as a quick start guide here's a breakdown of each control:

**Threshold:**
![Threshold slider](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/threshold.png)


The threshold slider controls the point of triggering the distortion circuit, important to not that this value determines the point at which the signal will become distorted once descending below the chosen value.

**Decay:**
![Decay sliders](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/decay.png)


The Decay sliders determine how quickly the signal will decay from clean to distorted once it descends below the chosen threshold, there is both a Wet and Dry decay for a greater degree of control and sound possibilities.

**Distortion:**
![Distortion](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/gain.png)


The distortion circuit controls work similar to most distortion effect processing units with the gain knob controlling the amount of gain that will occur once the circuit is triggered. The tone knob is a high pass filter within the circuit and finally the volume knob will determine the amplitude of the overall signal.

## Research

The subject area of distortion processors is now long and varied thusly it was necessary when researching for this project to narrow my own view to a handful of processors and developments. In todays world there is a range of readily available effects processors on the market which decide to take more novel approaches to tradtional practice, units such as the [Geiger Counter by WMD](https://www.youtube.com/watch?v=we5JErCLwPk). The Geiger Counter is a wave-table based distortion with several parameters available to the user allowing for a range of sounds from tube based overdrive to fuzz. 
The Geiger Counter is an interesting pedal because of the variety within it's algorithms allowing for a comparison from three relevant forms of distortion which are clipping, wavefolding and harmonic distortion.


## Development

The following image is the initial design sketch as well as the initial concept of the software which at that time was intended to be a physical design. 

![BSP Initial Sketch](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/BSP%20initial%20sketch.jpg)

"Distortion plugin that dynamically reacts to certain inputs. Example with vocals as input: longer note sustained triggers gain to increase." 
This note has been the main goal of the overall project and the one part of the patch that came together during the final stages.


**Dev Image 1**
![dev image 1](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/BSP%20development%20image%202.png)
**Dev Image 2**
![dev image 2](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/BSP%20Development%20image%203.png)

In the above images you can see the first two stages of development with the first stage being a simple clipping based distortion circuit, I decided to begin by finding the correct sound of distortion to utilise first. I decided to stick with a clipping based distortion both for its simplicity in implementation and usability and its sound when interacting with both vocals and guitar as an input source.
The second image shows the beginning of implementing a trigger for the distortion, this early form is a triggered sequencer that is only activated when the amplitude goes above the designated threshold this is the opposite to the desired effect wherein the trigger would be to decline *below* a chosen threshold.

**Dev image 4**
![dev image 4](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/BSP%20working%20prototype%20no%20interface.png)
Now in the above image this is a pretty finalised version of the circuit the big obvious addition is the slider to the left side which connects and outputs the sound to the [DAC~] object, this section is the gate that opens or closes depending on the threshold, utilising the [togedge] object from the Cyclone external library. This object sends a signal out to one of two bang objects below depending on if the input amplitude is above or below the user chosen threshold, from either of those initial bangs it then sends the signal to another bang which trigers the slider of the decay circuit on the left. I began initially with only one decay slide trigger which achieved a nice effect to gradually transition from distorted to clean but as soon as the signal descended below the threshold it would sharply drop to a distorted signal so I thought it best to add another with both being indipendent of each other as to allow for more options for the user to alter the effect to best suit their needs.


**Working On The Interface**
![Interface ideas](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/BSP%20Interface%20variations.png)
As seen above the design of the interface went through several iterations before the final version seen below, I knew roughly what controls I did want to include; decay and gain controls mainly. Unfortunately due to the outbreak of Covid-19 in the UK conduction any sort of in-person survey's or feedback became impossible but between myself and a friend whose also a musician we had a few back and forth conversations wherein I would show him the first design on the top left and simply asked if he were to own this in a product what would be his ideal controls and what other parameters would he want to control.
From his feedback I went through a few more iterations before settling on the final version which features the addition of the threshold slider as well as as visual representation of the output audio signal.

## Evaluation

As a conclusion I think the current build is a good first working prototype and I would like to carry on the work started and develop it further by incorporating more control parameters as well as possibily having multiple types of distortion ontop of the current clipping based one. I think the next natural progression of this project would be getting a working prototype in a VST plugin so that the processor could be more easily used and incorporated within DAWs.

Unfortunately I was unable to include any sort of imagery within the current build of the BSP but for the next phase of its development I would like to include some imagery that can further distinguish it as a product.
The following image is an early mockup of the type of imagery that would be included in any further development of the BSP as a product:

![BSP logo design](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/IMG_0075.jpeg)

The above concept was a mockup created by the artist Kate Hawkins in New Zealand who can be contacted at the following email address: katejmh@gmail.com  


