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

## Capture Software
Download CapSample1.exe to your local drive.  
Extract it.  
Go to:  
..\CapSample1\CapSample\bin  directory and run CapSample.exe  
Select camera  
![image](https://github.com/vintagefilmography/WolverineFix/assets/48537944/739e5040-5c82-4d1b-a6f2-12ea4512b99c)  
 
The config window should pop up  
![image](https://github.com/vintagefilmography/WolverineFix/assets/48537944/7d7a6b80-792d-4e58-8e67-b126cd560a5c)  
 
Select 15 FPS  
Click OK. 
The preview window should display the camera preview.  
![image](https://github.com/vintagefilmography/WolverineFix/assets/48537944/08fb6415-1df7-408d-b7a1-99aa4c23c814)  
 
Click on video capture device in the config window. 
The camera info window should pop up.  
![image](https://github.com/vintagefilmography/WolverineFix/assets/48537944/30fa9b15-1f12-44cc-9d48-7383b5f61a58)  
 
Click on Camera Control tab and set the exposure to manual and set the exposure control as needed.  
The auto exposure works ok sometimes but it can be fooled by the image white areas such as sprocket holes. 
Now, you are basically ready to start the capture. The default output directory in the config window is set to C:/Capture. 
You can leave it like that or change it to some other destination. 
It may be better to save the video to your local C: drive to ensure that there are no dropped frames.  
Once the capture is done it is easy just to copy the video from c: drive to an external drive and postprocess it right there.  
Press the start button:  
![image](https://github.com/vintagefilmography/WolverineFix/assets/48537944/ee5da0ec-926e-46f0-8f33-bc2f0a620e7e)  
 
Turn the unit of by pressing the power button in the original controller.  
Then, turn the run switch on and press the power button again.  
The unit should start running and the output will be sent to the C:\Capture directory or whatever directory you selected.  
Note that you can adjust the exposure dynamically while the capture is running. It is also possible to adjust other camera parameters if required.  
Once done, hit the Stop button in the preview window.  

## Alternative Capture Software
Download "3-H.264 USB Camera Testing software for Windows-20230606T131020Z-001.zip" file to your local directory.  
Unzip it and go into it.  
Then double click on H264_Preview.exe  
A window will open uo and should look like as shown:  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/674afcc9-88a0-41b1-b484-f3c62a66705c)   
Select the camera  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/952fda6c-07f7-4e3f-ae13-06673e56699b)  
Enable preview:  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/9e3792fa-4f28-45f2-9d5f-e48f9ba5cf48)    
The frame preview should be displayed.  
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
If you get some green frames at the beginning of the captured video with H264_preview.exe  do the following:  
Change the GOP in the H264 control pulldown to something lower than 29.  
![image](https://github.com/vintagefilmography/WolverineFix/assets/48537944/c75342b8-c7d0-45a0-9dd2-5f54c27ed86c)  

The GOP is a compression scheme where you group a set of images and use the first one as the key image.  
In the subsequent images you just send the diff info.  
But if the group is too long and you have dropped images the stream can go out of sequence and cannot decode the images completely.  
In the same popup window you can adjust the bit rate. Around 4000 kbps is still good quality. 
Check the dropped frames info on the bottom while capturing. A few here and there are ok but you do not want this  
get large. If it is then lower the FPS or bit rate or increase the GOP.  

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
The video file obtained by the capture sw uses the H264 codec and cannot be processed directly by the dups  
script. To get around this issue drag the video into virtual dub and save it using lagarith codec or raw.  
Raw obviously will take up more space. Now this saved file will be compatible with the dups script.  

Go to the scripts directory and open up remove_dups.avs in any text editor like Notepad or any other text editor.  
Change the source path in the script to point to your vdeo. 
Example:  
film = "F:\canon\clip1_raw.avi"  

Once done with the script, just drag the script file into the VirtualDub window.  
After a minute or so the video first frame will be displayed.  
At that point, set the video compression in the video pulldown and save the video.  
In unlikely case that there are black frames in the resulting video,   
run the remove_black_frames.avs script included here.  
Once this is completed the resulting video can be brought back into VirtualDub  
or DaVinci Resolve to do the final cut.
If the script reports issues with loading certain plugins, the most likely reason is that the your window installation 
is missing some DLLs. 
Run avsmeter.exe. in command window. It is in the scripts directory. 
avsmeter remove_dups.avs  
avsmeter provides the report and may give you additional info why the script is not loading properly.  
Here  is an example of the report:
AVSMeter 2.9.9.1 (x86), 2012-2020, (c) Groucho2004  
AviSynth 2.60, build:Feb 20 2015 [03:16:45] (2.6.0.5)  
  
Number of frames:                     2170  
Length (hh:mm:ss.ms):         00:02:00.556  
Frame width:                          1920  
Frame height:                         1080  
Framerate:                          18.000 (18/1)  
Colorspace:                           YV12  
Active MT Mode:                          0  
  
Frame (current | last):             292 | 2169  
FPS (cur | min | max | avg):        10.48 | 0.206 | 16.92 | 7.286  
Process memory usage:               617 MiB  
Thread count:                       4  
CPU usage (current | average):      24.7% | 24.5%  
  
Time (elapsed | estimated):         00:00:40.076 | 00:04:57.825  

In some cases avsmeter may not be able to help you and it may not give additional info on why a perticular DLL in  
not loading.  
You can also try dependency walker then.
https://www.dependencywalker.com/#:~:text=Dependency%20Walker%20is%20a%20free,diagram%20of%20all%20dependent%20modules.  
Download the zip into a local folder and unzip it there.  
Run dependds.exe by double clicking on it.  
A window will open.  
![image](https://github.com/vintagefilmography/Hawkeye3/assets/48537944/5d0250d9-9b23-49b1-ba27-8fc986cedb36)  
Do File->Open and open the DLL that has issues loading.
You will get a bunch of errors. Most of these are no problem beecause the tool is old and dodes not  
recognize the new calls. Go don to the bottom of the error list and you will notice different types of errors.
For example:  
HVSIFILETRUST.DLL  
IESHIMS.DLL  
PDMUTILITIES.DLL  
You can search for DLL description and dwhere used but most likely these are used by  
Microsoft redistrbutable package that is not loaded on your system.  
https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170
Install the 2015-2022 version and see if this fixes your issue. Most likely it will.

Some more details here:  
https://forum.doom9.org/showthread.php?t=172793

## Further Postprocessing  
Use option4.avs script in the scripts directory if additional film cleaning is required.  
Here is the desription of whata the script does.   
You start at thee bottom of the script  
Eval(result)#.converttoRGB24()  

Then search for result:  
result="result4" # specify the wanted output here  

Then search for result4  
 result4= interpolated.coloryuv(off_U=blue,off_V=red).levels(black_level,1.0,white_level,0,255)\  

Then for interpolated -- not these are all video streams in a pipeline feeding each other  
interpolated= denoised.MFlowFps(super, backward_vec, forward_vec, num=numerator, den= denumerator, ml=100)\  

Then denoised
denoised= cleaned.MVDegrainMulti(vectors, thSAD=denoising_strenght, SadMode=1, idx=2).unsharpmask(USM_sharp_ness3,USM_radi_us3,0)  

cleaned= RemoveDirtMC(noise_baseclip,dirt_strenght).unsharpmask(USM_sharp_ness1,USM_radi_us1,0)\  
.unsharpmask(USM_sharp_ness2,USM_radi_us2,0).Lanczos4Resize(W,H)  

noise_baseclip= stab2.levels(0,gamma,255,0,255).tweak(sat=saturation)  
stab2= stab.crop(CLeft,CTop,-CRight,-CBottom)  

stab=DePanStabilize(source1,data=mdata,cutoff=cutoff_value,dxmax=maxstabH,dymax=maxstabV,method=0,mirror=15).deflicker()  

source1= trim(source,0,trimming)  

source= AviSource(film).assumefps(play_speed).trim(trim_begin,0).converttoYV12()  

film= "F:\Hawkeye2\clip1-raw.avi"  

Note that the sections of the pipeline can be bypassed and new filters inserted if needed.  
It is fully customizable. 
