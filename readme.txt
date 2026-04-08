Hello and thank you for downloading my ripped take of this project here: https://github.com/leozimmerman/parameterSender
There's a lot of stuff here and I am going to try to make this appealing to new Linux users who want to get their hands dirty compiling from source.
Read this whole thing before doing anything because the bottom of this doc will have a series of youtube videos I watched as my citations for getting started.
Thank you to the AudioProgrammer Discord group for helping me with the NormalizedRange aspect of float management.

I have to upload this whole mass of stuff because the file output is larger than the free-tier of github's allowance for a few files.

I compiled it in JUCE 8 and the main stuff I changed was adding more decimal places of precision to the floats sent and updating the default port number and OSC address. 

Changes can be seen in ParameterSender.h lines 59-67 or so and OscManager.h lines 4-8(give or take)

0) Making sure JUCE is working correctly and is compiling correctly on Linux is a pre-req before getting started. Check the audio plugins folder examples and make sure the makefile versions output. I got the gain and the basic audio plugin that plays delayed sine waves to work.

1) git clone this project to a dedicated folder where you will want bitwig to pick up your JUCE VSTs: https://github.com/leozimmerman/parameterSender
1.1) Feel free to compile just this project right here and now just to make sure you at least have 2 decimal places of output.
1.2) There's a sudo make here somewhere. Check the videos.

There really should only be warnings that the package associated with bold text is outdated.

2) Replace the files in the source code folder and the .jucer file with the ones provided on my github page (or just make the few edits manually).
3) Make sure you are only exporting as a makefile
3) Save the .jucer file into a new file directory for the build so you can have overwrite tracking history.

OR 

I am pretty sure you open the projucer, open my version of the .jucer file, save to target source code location, and run sudo make. The source files should be updated to mine anyways.

Make sure to point your plugin folder of your DAW to wherever you create your exports so you know what is and is not exporting.

---------------------WORKS CITED-----------------------

Relevant youtube videos that basically explain how the .jucer files work and how saving them works.
Basically when you do the initial saving of a jucer file, it creates the build and makefile repositories. 
Use these for step 0.
https://www.youtube.com/watch?v=yxx6xcj3dRE
https://www.youtube.com/watch?v=cXVieAbHvMw

I have also attached a pD file set up for playing back video files without a play button and having OSC scroll through frames instead.
It is advised to download packages through apt rather than the internal pD tool(Specifically Gem). Just make sure to point pD to the externals folder, in /usr/lib/pd.
Video:

https://www.youtube.com/watch?v=WgxwkAsNjYw
https://www.youtube.com/watch?v=XyS2M0mM5iA
https://www.youtube.com/watch?v=q72IUX6uZRI   (didn't really use this one but still cool)

OSC in pD: (you may have to run sudo apt install osc or something if some OSC stuff is missing for some unexplained reason)
https://www.youtube.com/watch?v=tJ2Kocl-2m4

OSC in bitwig: (can do without these but Im sure you will wonder how other stuff works so here you go)
You'll at least learn how generic all of this stuff is and you can learn to work with FOH before you show up to your gig
https://www.youtube.com/watch?v=GEH7k1kp5U8
https://www.youtube.com/watch?v=u-fgArpsHQQ
https://www.youtube.com/watch?v=RvEMlo72ynQ
