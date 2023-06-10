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
Download Amcap app from this repository.
Note that there are two versions of capture software here at this site.  
amcap 
H264  
H264 is just another rversiion of amcap. Some testing is required to see which version runs better. 
Here are instructions on how to setuo amcap:  
https://docs.arducam.com/UVC-Camera/Quick-Start-for-Different-Systems/Windows/  
Once the video is captured, it will have duplicate frames and transitions in it.  
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
Download the zip file and unzip it somewhere in your work directory.  

Go to the scripts directory and open up remove_dups.avs in any text editor like Notepad or any other text editor.. Change the clip source path to wherever the clip is stored. #=============================================================================================

Clip source.
#=============================================================================================

film = "F:\canon\clip1_raw.avi" # source clip, you must specify the full path here

Change the threshold:
source= AviSource(film).assumefps(play_speed).trim(trim_begin,0).converttoYV12()
trimming= framecount(source)-trim_end
source1= trim(source,0,trimming)
source2= AssumeTFF(source1)
fc=Framecount(source2)
source3 = GetDups(source2,mode=-2,threshold=30.0)
source4 = Trim(source3,0,fc/3).coloryuv(autowhite=true)
#Eval(film)

Here it is set to 30. Lower threshold will have less chance of saving the bad frames but if it is too low it may remove some good frames.
It is a good idea to check the frame count uo front by running teh projector at low speed and counting the frames for a minute or two to
determine the frame rate and then run the complete reel and multiply the rate with duration. Alternatively a rough frame count can be obtained from the size of the reel.

Once done with the script, just drag the script file into the VirtualDub window. After a minute or so the video first frame will be displayed.
At that point, set the video compression in the video pulldown and save the video. No further processing will be required, although soemtimes you may get a few blank frames. If that happens run the remove_black_frames.avs script included here

Issue with avisynth dlls:  
https://forum.doom9.org/showthread.php?t=172793
