
   
## Planning
After being inspired to build this keyboard, the first goal I wanted to achieve was using capacitive touch to automatically switch to mouse layer.  
I knew this was possible as I saw username ufan mock up a test build with a stainless steel ball bearing in the ZMK Discord server, so I naturally decided to use one as well.  
With the constraint of having a stainless steel trackball, I thought wood and metal would create an intriguing vintage-furniture-like design.  
Although I learned that I didn't really need an auto-switch mouse layer and thus decided not to use capacitive touch later in the building process, I liked the design theme and decided to keep it.  
  
Regarding functionality, I wanted to make it wireless, add a button switch to save battery, add magnets to the original tents to attach/detach them conveniently, and install nice!view displays to know the pairing status and battery level.  
I knew the first three goals were achievable, but I've never seen someone using both a trackball and display on the same keyboard as pointing devices are currently experimental on ZMK.  
With these challenges in mind, I proceeded to the building process.  
  
I highly recommend watching [EIGAtech's wireless Charybdis video,](https://www.youtube.com/watch?v=Mks7QDxFreY&t) as it was incredibly helpful for me to visualize my build plan.


## Modeling
![Three-quarter view of modified case](Images/16.jpg)  
I have practically no knowledge in Fusion360, but as the changes I was about to make were minimal, it fortunately didn't deter the process too much.  
Firstly, I just simply added two holes on the side for the button switch and covered up the TRRS hole.  
I also changed the MCU holder for handwiring so that it didn't hold the TRRS conenector, grabbed on millmax hotswap sockets, and used a 3x6 button switch since that's what I had in stock.    
Everything except for the nice!view part was easy, as there was nothing to hold the nice!view to begin with.  
So I followed [BastardKB's keyboard design video](https://youtu.be/scoX8NZv4MI?si=uietOpE2jdQoaGku&t=1031) to make some walls on the side the exact way he did, and then I made a rectangular hole big enough to fit the nice!view flush.  
![Multiple nice!view hole variations that show my inexpertise](Images/14.jpg)  
If I was better in using Fusion360, I would have added a latch or any other mechanism to hold the nice!view in place.  
However, as I was limited by the fact that I don't know what I am doing, I simply stopped and decided to glue it in place.  
  
![Alien tent modeling file](Images/17.jpg)  
I also added four holes to the alien tent to hold 6cm magnets.  
The front legs were tall enough to fit two 3x6 magnets, and the back legs only managed to fit one 2x6 magnet each.  
I had to use the magnets this way in order to support the heavy keyboard in place without slipping.  
  
## Printing, Sanding, and Staining
![Unsanded case](Images/07.jpg)  
After the modeling process was finished, I 3D printed the cases and tents with wood PLA.  
I decided to use wood PLA was because I wanted the keyboard to feel like actual wood, and I saw some guides online that suggested sanding and staining.  
However, I later learned that just painting regular PLA like wood was way simpler, offered much more control, and achieved better results.  
If I were to rebuild this keyboard the same way, I think I would do that instead.  
  
![Sanded case](Images/08.jpg)  
I roughly sanded the printed 3D models with an 80 grit sandpaper to make it absorb the wood stain more easily.  
I could have used 160 or 200 grit sandpaper instead, but I expected the coarse 80 grit sandpaper to shorten the sanding process and produce a more unrefined, natural look opposed to the smooth, layered surface you get 3D printing.  
And I also tried to make the surface as smooth as possible without showing any staircase effects.  
  
![Stained case comparison](Images/09.jpg)  
![Finished case](Images/10.jpg)  
Once the cases and tents were ready, I stained them with two to three coats of some generic wood stain and finished the surface with a matte varnish.  
The final product turned out a bit too bright and red than I intended, but it was acceptable so I moved on.  

## Wiring and Electronics
![Messy handwiring](Images/11.jpg)  
I handwired the keyboard because I happened to have everything I needed, and I wanted to save some money. I deeply regret this decision as the inner height of the Charybdis Nano is so low that the wire and hotswap sockets could touch the floor below the metal plate and potentially cause shorts. Due to this reason, I strongly recommend using flexible PCBs if you were to build a Charybdis Nano yourself.  
As I have little to no knowledge about electronics, and all I am doing is guesswork based on pre-existing builds. This acted as a major obstacle for handwiring this keyboard as it meant I couldn't just install the firmware and had to figure out which wires were connected to which pin on the MCU.  
This is another reason why you should use flexible PCBs alongside [VOID's nice!nano holder](https://github.com/victorlucachi/Elite-C-holder), as everything is pre-positioned.  
So I dug up EIGAtech's [zmk config](https://github.com/eigatech/zmk-config/tree/charybdis) to find out how everything had to be wired, and I found three important files.  

![row2col and row pins](Images/18.jpg)  
  
charybdis.dsti : Here, I found row2col and row-gpios. 
row2col means electricity flowed from rows to columns for keyboard scanning.  
It is very important to know this detail, as this indicates which direction we must wire the diodes so that we ensure electricity doesn't flow the opposite way.  
row-gpios showed which pins were assigned to each row, so I just had to wire them accordingly.  
And also, I don't have to stick to these pins and just change them in this file to whichever pin I like.  
This applies to all the pins with some exceptions, so you should keep that in mind.  
  
![column pins](Images/19.jpg)  
  
charybdis_left.overlay : Here I found col-gpios. This told me where to wire the columns.  
One small issue I had was that this config was written for the 3x6 Charybdis Mini, but I was making a 3x5 Charybdis Nano.  
So there was one excess column pin that wasn't used on my keyboard, and I didn't know which one it was.  
To solve this problem, I just wired column 2 and tested which column it was on the keyboard to find out whether column 1 or 6 was unused.  
It was column 1, so I just didn't wire anything to it.  
  
![trackball pins](Images/20.jpg)  
  
charybdis_right.overlay : Here I found &pinctrl and &spi1. This showed me which pins were assigned for the trackball sensor.  

Now I just had to learn how to add a nice!view to the keyboard, so I searched online to find ZMK folders that had nice!view added to their keyboards.  
  
![niceview charybdis.conf](Images/25.jpg)  
  
In charybdis.conf, you have to add CONFIG_ZMK_DISPLAY=y and CONFIG_SSD1306=n as seen in the screenshot above.  
  
![niceview charybdis.dtsi](Images/22.jpg)  
  
In charybdis.dtsi, you have to add the entire &pinctrl and nice_view_spi sections as seen in the screenshot above.  
  
![niceview charybdis.zmk.yml](Images/23.jpg)  
  
In charybdis.zmk.yml, you have to add - display under the features section.  
  
![niceview charybdis.zmk.yml](Images/24.jpg)  

And most importantly, in build.yami, you have to add nice_view behind both shield: charybdis_left and shield: charybdis_right as seen above.  
I am not sure if you have to do all of these changes, but they are what I did to make the nice!view work on my keyboard.    
I hope it is clear that you can change all of the file names from charybdis to whatever keyboard you want to add the nice!view to.  
  
![My pinout](Images/21.png)  
With all the info I needed to handwire the keyboard, I came up with this pinout.  
The trackball/nice!view SCK/MOSI/CS/IRQ pins each can be interchanged with their corresponding positions.  
Although I ended up with this seemengly random placement, I believe only the VCC and RST pins must be wired at the same spot and would rather recommend organizing it to be more easily comprehensible. But keep in mind that it is preferred to use high-freuquency pins for the nice!view and trackball sensor.  

![Positioning the trackball sensor](Images/12.jpg)  
I used [ufan's original pmw-3610 breakboard](https://github.com/ufan/pmw3610_breakout) opposed to the [Charybdis pmw-3610 breakboard](https://github.com/Bastardkb/charybdis-pmw3610-breakout) because it was smaller, and since I am forced to buy 5 of these at least when ordered from JLCPCB, I planned to use the leftover ones for different keyboard projects.  
However, this meant the pmw-3610 doesn't have a way to be positioned correctly, so I had to change VOID's trackball sensor adapter to hold the pmw-3610 in place. I have failed in fine-tuning the position, and I worked around this problem by adjusting how tightly the bottom screws are turned.   
The trackball position must be in the exact configuration shown in the photo to work with my settings, and I strongly recommend using the Charybdis breakboard as it is very finicky to work with and hard to callibrate.  

![nice!view malfunctioning](Images/15.jpg)  

As far as I know, nobody wired a nice!view to a keyboard with a pointing device on ZMK, so I didn't know how their SPIs would interact, let alone what an SPI even is. 
I first thought they could share the same spi device and wired them to the exact same pins, and the nice!view started malfunctioning as shown in the photo.  
This is a very stupid thing to do in hindsight, but my lack of knowledge prevented me from realizing what an idiot I was.  
Whatever signals sent by the trackball interferred with the nice!view, and now I know they must use different pins.  
I set the trackball to use spi1, the nice!view to use spi3, wired the trackball and nice!view to different pins, and everything worked flawlessly.  
I then tested to see if they just had to use different pins and was able to share the same spi device, but although the nice!view screen showed up normally, the trackball didn't work.  
Maybe there might be an error on my side, but with this, I came to believe that the trackball sensor and nice!view must use both different pins and spi devices.  


## Final Stretch
With the keyboard now functioning properly, I just had to get keyswitches and keycaps to finish the build.  
I got Gazzew Boba U4 keyswitches as I prefer having no noise, and I got a set of Ogre zinc alloy keycaps to further push the metal-wood aesthetics.  
They feel cold to touch for the first couple minutes, but they'll warm up eventually. Sometimes they make a metallic clank sound when I type, which I think is cool.  
The Ogre keycaps are sold in Korea for roughly $48 for 72 caps, making them far more affordable than aluminum or stainless steel keycaps.  
However, as zinc alloy keycaps are notoriously subseptible to discoloration, I might have to replace them after a couple months or years later.  
![Pseudo-keywell](Images/04.jpg)  
I've installed the R4 keycaps upside down in row one and R2 and R3 keycaps in rows two and three, thus creating a pseudo-keywell structure.  
It would have been better to use other keycaps, but as these were the only metal keycaps I were willing to afford, I had to make use of what I could.  
The pseudo-keywell had a surprisingly satisfying curvature, although the bottom row felt a bit flat. To me, it is not inferior to uniform DSA keycaps, albeit having strengths and shortcomings in different areas.  
![Captain's chair](Images/05.jpg)  
I am currently mainly using the keyboard clamped to my chair with Magsafe adapters and 141cm magic arms.  
It is very convenient to type, and the battery lasts about 5 days.  
When I don't use the keyboard, I detach both halves and place them on the magnetic alien tents as display.    

## Limitations
Now with the keyboard finished, there are some huge flaws that must be fixed.  
![nice!view hotglued in place](Images/06.jpg)    
1. The nice!view must have a non-destructive way to install. I just hotglued mine and they work fine to me, but this is not a reliable way to manufacture a keyboard, and I will have a huge problem replacing them when they eventually break down.  
2. The right half resets sometimes when I detach it from the chair. I believe this is happening due to a short, but it is practically impossible to address as I did a messy job handwiring the keyboard.  
3. My ZMK config is outdated. Whenever I turn off the keyboards, the peripheral left half loses connection to the right half and fails pairing. This is fixed by changing the config file a bit, but it in turns drains the left half's battery extremely fast, so it also only lasts about 5 days and not the expected one month. I can actually fix this easily by using the most recent ZMK pointer branch, so it isn't as critical as the other flaws. 
4. I am using a 3x6 Charybdis Mini firmware instead of a 3x5 Charybdis Nano firmware. Although it is functioning perfectly, I am basically using a 3x6 keymap with all of the outer column keys left blank. It is a bit of a hassle to work with, and it would be much more nice to just set it as a 3x5 keyboard in the first place.  
5. The trackball sensor isn't perfectly aligned to the trackball. As I fastened ufan's breakboard by modyfying VOID's pmw-3610 adapter, it is less precisely positioned than the Charybdis pmw-3610 breakboard that is always guaranteed to be in the same height and orientation. Due to this flaw, the track ball sometimes doesn't work, and I have to press on the bottom of the cover and tap it a bit to make it work properly. This can be fixed by modifying VOID's pmw-3610 adapter and bottom cover, but although I am currently working on it right now, it will take a huge amount of trial and error.  

Because of the reasons listed, I do not recommend building this keyboard the way I did.  
Instead, I'd recommend using flexible PCBs, the Charybdis pmw-3610 breakboard, and not using nice!views for the current time.  
And I would also recommend buying [BastardKB's Charybdis kit](https://bastardkb.com/charybdis) as it's a very nice way to get most of the materials.  
Maybe I will update the 3D files in the future, but I am mentally satisfied with what I have accomplished, and it will take a lot of motivation and learning until I muster up the will to fix them.  
