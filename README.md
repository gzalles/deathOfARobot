# deathOfARobot
a max/msp patch I made. inspired by poeme electronique (varese ~1958)

[![YTVidlink](img/fakeit.jpg)](https://youtu.be/8GkU9zU_NVM)

## analysis:

438 images from Unsplash change 100ms at a time. Electronic sounds play behind that as a shader applies glitch to the video. The initial intention was not to make deathOfARobot but that's what it looks like to me. The output of this patch resembles what we might imagine the last moments of an artifical life form, which operates on data and instruction sets, might look like. There are only about 10 sounds from the dataset in this version but in theory we can use hundreds. The FSDKaggle2018 has over 9,000 wav files. The video is slowed down because my computer could not handle it the screen capture, sorry...I purposefully did not include the video or the soundfiles since I think it will be more interesting for the user to use/make their own. There is paper and presentation in the pdf folder that also provides more context for the piece.

## notes:
* My 2015 MacBook Pro with 2.9GHz Intel Core i5 can hardly handle the video and the audio. It takes about 30 seconds to stuff to get going...There is likely a way to optimize it but I don't know if I will ever get to it.

## musical elements:
* voice 1 = polybuffer~ with feedback
* voice 2 = circular FM (from [TRE](http://tre.ucsd.edu/wordpress/))
* voice 3 = triangle wave
* voice 4 = noise shaped with lores~

<!-- ## to do:
* add more ridiculous bits for Edgar (final paper)
* upload everything to the web.
	* document on site -->

## ingredients:
* Freesound Dataset (FSDKaggle2018)
* Bulksplash - command line tool for batch Unsplash image downloads.
* [I borrowed this patch](http://abstrakt.vade.info/?p=48) ("shader?")
* [Used this answer to make my movie](https://cycling74.com/forums/reading-jpg-files-from-a-folder)
  * This is the makeMov patch. Not sure if my edits got saved.
* Handbrake to compress the Quicktime screen capture
* ICST ambisonic package for MAX/MSP (in case we want multichannel)

## how I made this:
* used Bulksplash to get a bunch of pictures.
	* I took a screenshot of the categories I used
	* Settings: 49 images each time (max), featured (yes) and landscape.  
  <img src="img/categories.jpg" alt="drawing" width="200"/>
* used a max/msp patch to play the pictures 100ms at a time.
	* I had to edit the patch (made the matrix larger to increase quality)
	* It takes a while to load 300+ images into RAM, I had to wait like 3-4 min.
* used quicktime to screen capture the movie
	* I used a timer on my phone to figure out how long it was.
	* Then I trimmed it in Quicktime.
* used handbrake to compress the movie
	* I had to do this because the movie was not playing correctly.
	* from MOV to MP4
	* 5GB down to 1GB - much faster
* used the shader to add something special to the movie.
* used the Freesound dataset to make the polybuffer voice. instead of fishing for samples now I have this huge library for future max patches.
* used circular FM patch by Tom to make the main sound.
* I captured the whole thing again with Quicktime this time sending the sound out via SoundFlower.
