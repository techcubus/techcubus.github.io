# Music Production, Synths and Software
Music software and synth UIs are kind of ok now i guess

### VCV Rack under Windows 7?  
Rack2 needs opengl 3.2 so either:
* Use Rack 1.6 or 
* Dropping the DLLs opengl32.dll and libgallium_w32.dll from the mesa-dist-win package into the Rack 2 directory got it to actually start up
* Do **not** expect performance

### vst hosts for Windows 
* VSTHost
  * tres buggy  
  * no vst bundle support  
  * 32, 64-bit and 9x versions   
  * simple to intensely complicated patch bay 
  
* opencma / LightHost  
  * holy crap have the computer muted before you run it 
  * lives in the system tray which is probably a turn on for someone  
  * 32 and 64 bit versions in different archives
  * Windows binaries but supposed to be able to compile for Mac/Linux
  * Probably have to know how to build JUCE projects (proJUCEr? no build instructions)
  * Multiple instances with param `-multi-instance=uniqInstanceName`
  
* Tone2 / NanoHost  
  * cromulent but won't run vst3
  * can run multiple instances
  * 32 and 64 bit versions\
  * Supports XP-11
  
* VCV Rack  
  * great if you have the HP but automation controls are limited to like 24 inputs  
  * no 32 bit vsts == sadness :(  
  * make sure to set the midi to cv module to polyphonic if you're expecting polyphony or just let the plug-in talk to midi directly
