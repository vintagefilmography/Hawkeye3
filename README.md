# Hawkeye3  
![PXL_20230605_171622429](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/76f12083-cb40-40c8-8c1e-61eb8d10e631)  

This is the documentation for Hawkeye3 simple Wolverine mod that replaces the stock camera 
with an equvalent camera that does not have digital artifacts issue.
The Wolverine controller and its camera are moved to the back of the unit allowing enough free space for the new camera.
The camera used is the usb ELP model ELP-USBFHD04H-FV. It uses an AR0330 sensor with 1080P resolution. Essentially, the same
sensor that the Wolverine model uses but unlike Wolverine this one allows the user full access to the camera settings. 
The camera connects to a Windows PC that runs a capture software (included here). The capture software anywhere between 
10 and 30 FPS and dcreates a video that includes the film transitions. The transitions can subsequently be removed with the 
postprocessing software (also included).

## Instructions
Plug the dc adapter into the unit as shown.
![power](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/cde0c2a6-33e7-4f4b-bd65-a12478188a30)
Set the R8/S8 (regular 8 or super 8 film) switch as needed.
![r8s8](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/06ce9cfd-f50c-4a43-b0dc-85dadc4a7da3)  

Thread the film in.  
Activate Run switch  
![run](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/f8b615e2-4715-441a-9b3f-7cf5f29cb0a6)  
Press power button on the Wolverine controller.  
![power_button](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/152a4774-1ef5-4bcd-877f-c5bd2511aa2f)  
The unit should start advancing the film.  
Once the lead is done and the good film section start running through the gate, turn the run switch off.  
The motor will stop but the light will be still on.
Plug the camera usb cable into the camera usb connector.
Download 3-H.264 USB Camera Testing software for Windows-20230606T131020Z-001.zip file to your local directory.
Unzip it and go into it. 
Then double click on H264_Preview.exe  
A window will open uo and dshould look like as shown:
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/674afcc9-88a0-41b1-b484-f3c62a66705c)  
Select the camera
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/952fda6c-07f7-4e3f-ae13-06673e56699b)  
Enable preview:
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/9e3792fa-4f28-45f2-9d5f-e48f9ba5cf48)  
The frame preview shouldd be displayed. This one should here is  for the 6mm lens. The 12mm will have larger frame and
proper orientation.
If you get the white screen only then the camera may need a reset. Just unplug the camera from the PC and   
plug it back in.  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/0eb5f07b-6494-4933-baf3-db8127d419ab)  

Note: Make sure that there is no external light shining on the gate like a daylight frorm the eindow etc. 
Additional camera controls are available via   options pulldown:
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/a80bc6a0-8deb-4ed7-ae05-cbf88292b43b) 
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/0026c09f-cd08-4a86-88d3-8b0e64a03b30)
and camera controls
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/1954d44c-acd5-4b7b-9898-d391f2e12684)  
These can be let as is. Under some conditions manual exposure and manual white balance may work better.  
The best way is to experiment with the settings  to achiveve best results. 
Some additional info:  
https://docs.arducam.com/UVC-Camera/Quick-Start-for-Different-Systems/Windows/  

Once all of this is set, run capture.  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/532e3005-2209-4884-9a9a-d0ce9e1cad0a)  
Set the destination file path. Make sure eto type the .avi after the file name.  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/fd581b8e-145f-454d-8941-1a31b9da45b2)  
Click OK. Do not have to change the file allocation size.  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/3a54eae9-b6fe-4cc7-83c1-3449642b831d)  
Press the power button to turn the unit off. Then turn the RUN switch on  and press the power button again.
The unit will run and the film capture will start.   


Once the video is done, turn the RUN switch off and power the unit off.  
The video will have duplicate frames and transitions in it.  
The duplicates are transitions get cleaned up by the avisynth script.
Here are instructions on how to run the script.

## Postprocessing  
The video will contain many duplicate frames and transitions.  
It is easy to remove the duplicates and the transition frames by using the Avisynth remove_dups script.  
The first step in getting the the script working is to get Avisynth from:  
https://sourceforge.net/projects/avisynth2/  
Here is the avisynth page. You can skip it for now. It is just for your reference.
http://avisynth.nl/index.php/Main_Page   
Avisynth does not run as a standalone application. It is a tool that allows video editors and viewers to run the script.  
The script is essentially a text file that contains the avisynth commands for video processing.  
One video tool that is very handy for video processing is called VirtualDub.  
In addition to basic video processing, VirtialDub reads the avisynth script as well.  
Download VirtualDub from here:  
https://sourceforge.net/projects/vdfiltermod/files/  
Run VirtualDub.
Should get a dub window that looks like the following picture:  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/abe5bc97-fe19-4714-ac30-c9fc77c092d3)

Using the avisynth script can get a bit tricky because there are so many plugins out there and you will usually
run into a plugin missing error. That is why the scripts zip file here contains most of the DLLs needed.  
Download the scripts zip file and unzip it somewhere in your work directory.  

Go to the scripts directory and open up remove_dups.avs in any text editor like Notepad or any other text editor.  
Change the source path in the script to point to your vdeo. 
Example:  
film = "F:\canon\clip1_raw.avi"  

Once done with the script, just drag the script file into the VirtualDub window.  
After a minute or so the video first frame will be displayed.  
At that point, set the video compression in the video pulldown and save the video.  
No further processing will be required. 
In unlikely case that there are black frames in the resulting video, run the remove_black_frames.avs script included here

If the script reports issues with loading certain plugins the most likely reason is that the your window installation 
is missing some DLLs. 
Run avsmeter.exe. in command window. It is in the scripts directory.
You can also try dependency walker.
https://www.dependencywalker.com/#:~:text=Dependency%20Walker%20is%20a%20free,diagram%20of%20all%20dependent%20modules.  
Some emore details here:  
https://forum.doom9.org/showthread.php?t=172793
