# Music Production, Synths and Software
Music software and synth UIs are kind of ok now i guess

### VCV Rack under Windows 7?  
Rack2 needs opengl 3.2 so either use Rack 1.6 or putting opengl32.dll and libgallium_w32.dll from the mesa-dist-win package into the Rack 2 directory got it to actually start up

### vst hosts for Windows 
* vsthost32/64  
  * tres buggy  
  * no vst bundle support  
  * probably runs on 9x still?  
  * simple to intensely complicated patch bay 
  
* lighthost  
  * holy crap have the computer muted before you run it 
  * lives in the system tray which is probably a turn on for someone  
  * 32 and 64 bit versions in different archives
  * Windows binaries but supposed to be able to compile for Mac/Linux
  * Probably have to know how to build JUCE projects (proJUCEr?)
  * Multiple instances with param `-multi-instance=uniqInstanceName`
  
* nanohost  
  * cromulent but won't run vst bundles
  * can run multiple instances
  * 32 and 64 bit versions
  
* vcv rack  
  * great if you have the HP but automation controls are limited to like 24 inputs  
  * no 32 bit vsts == sadness :(  
  • make sure to set the midi to cv module to polyphonic if you're expecting polyphony or just let the plug-in talk to midi  
