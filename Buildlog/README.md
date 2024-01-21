
   
## Planning
After being inspired to build this keyboard, the first goal I wanted to achieve was using capacitive touch to automatically switch to mouse layer.  
I knew this was possible as I saw ufan mock up a test build with a stainless steel ball bearing in the ZMK Discord server, so I naturally decided to use one as well.  
With the constraint of having a stainless steel trackball, I thought wood and metal would create an intriguing vintage-furniture-like design.  
  
Regarding functionality, I wanted it to be wireless, have a button switch to save battery, add magnets to the original tents to attach/detach them conveniently and install nice!view displays to know the pairing status and battery level.  
I knew the first two goals were possible, but I've never seen someone using both a trackball and display on the same keyboard as pointing devices are currently experimental on ZMK.  
With these challenges in mind, I proceeded to the building process.


## Modeling
(Photo of multiple nice!view variations)  
I have practically no knowledge in Fusion360, but as the changes I was about to make were minimal, it fortunately didn't deter the process too much.  
Firstly, I just simply added two holes on the side for the button switch and covered up the TRRS hole on the case. I also changed the MCU holder for handwiring so that it didn't hold the TRRS conenector, grabbed on millmax hotswap sockets, and used a 3x6 button switch. 
(tent 3d model)
For the tents, I just had to make some holes, and for the keyboard cases, I just had to make a hole for the button switch and a holder for the nice!view.  
Everything except for the nice!view part was easy, as there was nothing to hold the nice!view.  
So I followed BastardKB's original Charybdis design video(put link) to make some walls on the side the exact way he did, and then I made a rectangular hole big enough to fit the nice!view flush.  
If I had expertise in Fusion360, I would have added a latch or any other mechanism to hold the nice!view in place. However, as I was limited by the fact that I don't know what I am doing, I simply stopped and decided to glue it in place.  


## Printing, Sanding, and Staining
(Photo of unsanded 3D model)  
After the modeling process was finished, I 3D printed the cases and tents with wood PLA.  
The reason I used wood PLA was because I wanted the keyboard to feel like actual wood, and I saw some guides online that suggested sanding and staining.  
However, I later learned that just painting regular PLA like wood was way simpler, offered much more control, and achieved better results.  
If I were to rebuild this keyboard the same way, I think I would do that instead.  

(sanded 3D model)  
I roughly sanded the printed 3D models with an 80 grit sandpaper to make it absorb the wood stain more easily.  
I could have used 160 or 200 grit sandpaper instead, but I expected the coarse 80 grit sandpaper to shorten the sanding process and produce a more unrefined, natural look opposed to the smooth, layered surface you get 3D printing.  

(stained 3d model comparison)  
Once the cases and tents were ready, I stained them with three coats of some generic wood stain and finished the surface with a matte varnish.  
The final product turned out a bit too bright and red than I intended, but it was acceptable so I moved on.  

## Wiring and Electronics

As I have little to no knowledge about electronics, and all I am doing is guesswork based on pre-existing builds. This acted as a major obstacle for handwiring this keyboard as it meant I couldn't just install the firmware and had to figure out which wires were connected to which pin on the MCU. So I dug up VOID's zmk folder to find out how everything had to be wired.  
(photo of row2col and row pinout and such)
Based on -insert file name-, I found three keywords: row2col, pins, and pins.  

(photo of keyboard matrix)  
row2col : This meant electricity flowed from rows to columns for keyboard scanning. It is very important to know this detail, as this indicates which direction we must wire the diodes so that we ensure the electricity doesn't flow the other way around.  
Both the row pins and column pins indicated told me where each row and column must be wired to, so I just had to connect the wires accordingly.  

(photo of my pinout)  

I did the same thing with the trackball sensor, and I organized everything into this neat image file so I could just solder the wires without going through every single document.  

(trackball sensor positioning)  
I used ufan's original pmw-3610 breakboard opposed to the Charybdis pmw-3610 breakboard because it was smaller, and since I am forced to buy 5 of these at least when ordered from JLCPCB, I planned to use the leftover ones for different keyboard projects.  
However, this meant the pmw-3610 doesn't have a way to be positioned correctly, so I had to change VOID's trackball sensor adapter to hold the pmw-3610 in place. I have failed in fine-tuning the position, and I worked around this problem by adjusting how tightly the bottom screws are turned.   
The trackball position must be in the exact configuration shown in the photo to work with my settings, and I strongly recommend using the Charybdis breakboard as it is very finicky to work and hard to callibrate.  

(nice!view malfunctuoning)  

Nobody by far wired a nice!view to a keyboard with a pointing device, so I didn't know how their SPIs would interact, let alone what an SPI even is. 
I added -corresponding lines- to make the nice!view work as a native shield, and as result the nice!view started malfunctioning as shown in the photo.  
I believe this happenend because both the nice!view and trackball's irpt, sck, mosi pins were wired to the same MCU pins, and they were both set to use spi0. It seemed that whatever signals sent by the trackball interferred with the nice!view.  
To solve this issue, I set the trackball to use spi3, wired the trackball and nice!view to different pins, and everything worked flawlessly.  I suspect that maybe the problem was only the two devices being wired to the same pins and using the same spi might not have affected the interference, but I was fed up with desoldering and resoldering everything at this point and wasn't willing to verify if that was the case.  


The Ogre zinc alloy keycaps are roughly $48 for 72 caps, making them far cheaper than aluminum or stainless steel keycaps.  
However, as zinc alloy keycaps are notoriously subseptible to discoloration, I might have to replace them after a couple months or years later.  
<Photo>  
I've installed the R4 keycaps upside down in row one and R2 and R3 keycaps in rows two and three, thus creating a somewhat palatable keywell structure. It would have been better to use other keycaps, but as these were the only metal keycaps I were willing to afford, I had to make use of what I could.  


(actual pinout photo)  
  This is my pinout, and the trackball/nice!view sck/mosi/cs pins each can be interchanged with their corresponding positions. Due to trial and error and miswriting pin numbers, I have resulted in the above mess, but I would rather use the pinout below for easier wiring.  
  (Desired pinout photo)  
