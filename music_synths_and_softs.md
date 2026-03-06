#### VCV Rack under Windows 7?  
Rack2 needs opengl 3.2 so either use Rack 1.6 or putting opengl32.dll and libgallium_w32.dll from the mesa-dist-win package into the Rack 2 directory got it to actually start up

#### vst hosts for Windows 

* vsthost  
  * tres buggy  
  * no bundle support  
  * probably runs on 9x still?  
  * simple to intensely complicated  
* lighthost  
  * holy crap have the computer muted before you run it 
  * lives in the system tray which is probably a turn on for someone  
* nanohost  
  * cromulent but won't run bundled  
* vcv rack  
  * great if you have the HP but automation controls are limited to like 24 inputs  
  * no 32 bit vsts == sadness :(  
  • make sure to set the midi to cv module to polyphonic if you're expecting polyphony or just let the plug-in talk to midi  