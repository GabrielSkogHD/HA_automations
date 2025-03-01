# HA_automations

## HA Hue cycle
### Getting started
First you need to create a input_number entity inside of your HA 
``` input_number.hue_scene_index ``` 
Minimum value and maximum values are the number of scenes you want to cycle through. 
Step size: 1

You will then need to include this .yaml file in your automations. You will also need to replace device id.

### Turning off lights
In the yaml file ```HUE_turn_off.yaml``` I turn off all the lights in the room but I also reset the ``` input_number.hue_scene_index ``` to the maximum value. When I press the button again it will activate the first scene in the list. 

### Include more scenes
If you want to add more scenes you must increase the maximum value of ``` input_number.hue_scene_index ```  and include another 

```
- choose:
      - conditions:
          - condition: state
            entity_id: input_number.hue_scene_index
            state: "NEW VALUE"
        sequence:
          - target:
              entity_id: YOUR HUE SCENE
            action: hue.activate_scene
            data: {}
```
inside of your script. 
Also you need to update your ```HUE_turn_off.yaml``` script to reset to the new maximum value. 


