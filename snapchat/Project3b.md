## Customizing Our Marker  
1. Find the `DoorOpenEffect` prefab in the Resources panel and import it into the `Image Marker [EDIT_ME]` object. Now when your camera finds a comet card it will open like a barn door to a small empty virtual space inside.
2. Now lets take the `Temoc_Head` prefab and import it into the `Image Marker [EDIT_ME]` object. You will be able to see it in the Scene panel (center panel).
3. With the `Temoc_Head` object selected in the object panel we will move, scale, and rotate our Temoc head until it fits inside of the virtual box `DoorOpenEffect` created for us.
![Move Rotate Scale](https://i.imgur.com/zAPuxH8.png)
	> To pan your camera around the Scene Panel hold right click
		To move your camera around the scene hold your MMB (scroll wheel)
		To zoom in/out of your scene use the scroll wheel
		
	This is what your Lens Studio Scene and preview should look like after the transforms are completed, if you were unable to get the temoc in the exact location you can copy the data in the `Transform` component in the Inspector panel to your own `Temoc_Head` object: 
	![Completed Temoc transforms](https://i.imgur.com/flhnPos.png)
  
  ## Animating Our Model Using Tweens
1. While still in the `Temoc_Head` object we will click `+Add Component` within the Inspector panel, then add a script component.
2. Click `Add Script` then navigate (or search) for `Tween Transform`
	- Use the following settings in your TweenTransform Script
		- Tween Name: `move` ( A name we will use to reference this specific movement)
		- Play Automatically: `Disabled` (This will allow us to control when it is played)
		- Loop Type: `None` 
		- Type: `Move` 
		- Movement Type: `Offset` (We will be adding 15 units to the Vertical [Z] Axis)
		- Offset: `0.00 | 0.00 | 15.0`  [These are X|Y|Z]
		- Additive: `Enabled`
		- Time: `1.50` (How long it will take to add all 15 units to Z+)
		- Delay: `1.00` (We will delay for a second to allow the doors to open)
		- Is Local: `Enabled`
		- Easing Function: `Quadratic`
		- Easing Type: `Out`
3. Repeat Step 2 with the following settings:
	- Tween Name: `rotate` ( A name we will use to reference this specific movement)
		- Play Automatically: `Disabled` (This will allow us to control when it is played)
		- Loop Type: `Loop` 
		- Type: `Rotate` 
		- Movement Type: `Offset` (We will be adding 180 units to the Rotational [Y] Axis making our object spin)
		- Offset: `0.00 | 180.00 | 0.00`  [These are X|Y|Z]
		- Additive: `Enabled`
		- Time: `3.00` (How long it will take to spin 180 degrees)
		- Delay: `0.00` 
		- Is Local: `Enabled`
		- Easing Function: `Linear`
		- Easing Type: `Out`
4. Repeat Step 2 with the following settings:
	- Tween Name: `scale` ( A name we will use to reference this specific movement)
		- Play Automatically: `Disabled` (This will allow us to control when it is played)
		- Loop Type: `None` 
		- Type: `Scale` 
		- Movement Type: `Offset` (We will be adding 0.03 units to all 3 Axis of our object scaling it uniformly)
		- Offset: `0.03 | 0.03 | 0.03`  [These are X|Y|Z]
		- Additive: `Enabled`
		- Time: `2.00` (How long it will take to scale)
		- Delay: `1.00` (We want to allow the head to get out of the box before scaling)
		- Is Local: `Enabled`
		- Easing Function: `Quadratic`
		- Easing Type: `Out`
5. Now select the `Image Marker[EDIT_ME]` Object and add a script component then the `TweenChain` Script. The TweenChain script will allow us to execute all 3 of our tweens at the same time.
	- Use the following settings on the TweenChain:
		- Tween Name: `temoc`
		- Play Automatically: `Disabled`
		- Loop Type: `None`
		- Scene Object: `Temoc_Head` (Navigate to find this in Objects like you would a Resource)
		- All At Once: `Enabled`
		- Tween Names: Click `+Add Value` (recall the names we named our tweens in `Temoc_Head`)
			-  Value 0: `move`
			- Value 1: `rotate`
			- Value 2: `scale`
6. Finally we will add a Behavior script to tie the Marker being found to start the tweens. In the objects panel (top-left) click the + mark and search `Behavior` It will find `Helper Scripts` which `Behavior` is in. Add `Behavior` to our project.
7. In the newly created `Behavior` object set the Script component options to the following settings:
	- Trigger: `Marker Tracking Event` (Our goal is to trigger our tween animations when our marker is found)
	- Event Type: `Marker Found`
	- Marker Tracking: `Image Marker [EDIT_ME]. Marker Tracking`
	- Allow: `Always`
	- Delay Time: `0.00`
	- Response Type: `Run Tween` (When our behavior script is triggered by the Marker Foudn event it will run our tween)
	- Target Object: `Image Marker[EDIT_ME]`
	- Tween Name: `temoc`
	- Action: `start` 

If everything is done correctly the Lens should be complete! Try it on your Comet Card!
## Testing The Lens
[This section is only applicable if you have a mobile device with snapchat installed.]
Now we will pair our Snapchat to our Lens Studio so we can preview our lens before we upload it publicly. 

1. Click `Preview in Snapchat` on the top right of Lens Studio.
2. Scan the Snapcode displayed on screen like a QR code in Snapchat.
3. Push `Pair` on the prompt that displays after scanning the Snapcode.
4. Wait a few moments for the devices to pair, then click `Send Lens to Device` once it appears where `Preview in Snapchat` used to be.
5. Once it says `Lens Sent` open the Lens Carousel by tapping the small emoji face near the shutter button. 
![Lens Carousel Button](https://i.imgur.com/i1EyeV9.png)
6. Scroll to the right until you find your preview lens. 

## Done!
Publish the lens to your Snapchat account if you would like by clicking `Publish Lens` at the top-left of Lens Studio, then following the prompts on the website. Make sure you give it a new name and logo in `Project Info` before you upload.
