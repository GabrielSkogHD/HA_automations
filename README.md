# HA_automations

## HA Hue cycle
### Getting started
First you need to create a input_number entity inside of your HA 
``` input_number.hue_scene_index ``` 
Minimum value and maximum values are the number of scenes you want to cycle through. 
Step size: 1

You will then need to include this .yaml file in your automations. You will also need to replace device id.
