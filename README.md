# 7MU007-Bloody-Sonik-Pumpkin-


## Description

The Bloody Sonik Pumpkin is a novel distortion effect proccessor built within the open source software PureData. The effect of the unit is based around the idea of a 'reverse distortion' with the distortion only being triggered as the input signal descends below a designated threshold. The inspiration for the design came from a personal enjoyment of distortion as a concept as well as an interest into using distortion in new ways in order to aid the creative process.


## Table of Contents
  - Usage
  - Development
  - Research
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


The distortion circuit controls work similar to most distortion effect processing units with the gain knob controlling the amount of gain that will occur once the circuit is triggered. The tone knob is a high pass filter within the circuit and finally the volume knob will determine how amplitude of the overall signal.

## Research

The subject area of distortion processors is now long and varied thusly it was necessary when researching for this project to narrow my own view to a handful of processors and developments. In todays world there is a range of readily available effects processors on the market which decide to take more novel approaches to tradtional practice, units such as 

## Development

The following image is the initial design sketch as well as the initial concept of the software which at that time was intended to be a physical design. 

![BSP Initial Sketch](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/BSP%20initial%20sketch.jpg)

"Distortion plugin that dynamically reacts to certain inputs. Example with vocals as input: longer note sustained triggers gain to increase." 
This note has been the main goal of the overall project and the one part of the patch that came together during the final stages.


Unfortunately I was unable to include any sort of imagery within the current build of the BSP but for the next phase of its development I would like to include some imagery that can further distinguish it as a product.
The following image is an early mockup of the type of imagery that would be included in any further development of the BSP as a product:

![BSP logo design](https://github.com/BohemianSte/7MU007-Bloody-Sonik-Pumpkin-/blob/master/IMG_0075.jpeg)



