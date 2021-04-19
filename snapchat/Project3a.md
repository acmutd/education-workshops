# Project 3: Marker Template  
## Downloading assets  
**Assets** [Required]: https://drive.google.com/drive/folders/1hWrTCCOTqRh08o15UtYnRt80Wacn3mwH?usp=sharing
or  https://bit.ly/3glYfw5
## Marker Template  
The goal of this project is to use the skills we learned so far to create an interactive marker experience. The Marker Template allows you to specify an image that is recognized and tracked by the Snapchat camera.
  
## Setting Up Our Marker 
Begin by opening lens studio or returning to Lens Studio home with `CTRL+W` or `CMD+W`.  
  
Download the asset(s) above and put them somewhere safe.  

1. Open the project titled `Modified Marker Template` provided in the asset pack you downloaded by clicking `Open Project` on the middle-left of Lens Studio home, then navigating to the `Modified Marker Template.lsproj` file in your file browser.
		- It is normal for errors to exist in the Logger panel when opening this project. We will fix them in the next steps.
2. First we will set the image our Marker tracker will use to track by selecting the `Image Marker [EDIT_ME]` object in the object panel. Then we will select the `CometCard Template` Image marker resource located in the `Markers [REPLACE_ME]` folder.
3. Next select the `Magnifiying Hint [EDIT_ME]` object and set the `Preview Texture` Image to the `CometCard Template Source` located in the `Markers [REPLACE_ME]` folder.
4. Now we will test if our marker is working correctly by using our webcam in the preview panel to check if the marker is recognized. You will know it is recognized when a rainbow checker pattern displays over it.
		- I have also included a preview image you can use if you do not have a webcam available. Import it by selecting the preview dropdown and `+From Files` then navigating to `cometcard preview.jpg`.  To select it scroll up, it will be at the top of the list. 
		
    ![enter image description here](https://i.imgur.com/Co3s43j.png)
  
Congratulations you now have a working marker asset!
