
   
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
For the tents, I just had to make some holes, and for the keyboard cases, I just had to make a hole for the button switch and a holder for the nice!view.  
Everything except for the nice!view part was easy, as there was nothing to hold the nice!view.  
So I followed BastardKB's original Charybdis design video(put link) to make some walls on the side the exact way he did, and then I made a rectangular hole big enough to fit the nice!view flush.  
If I were a knowledgable man, I would have added a latch or any other mechanism to hold the nice!view in place. However, as I was limited by the fact that I don't know what I am doing, I simply stopped and decided to glue it in place.  


## Printing, Sanding, and Staining
(Photo of unsanded 3D model)  
After the modeling was finished, I 3D printed the cases and tents with wood PLA.  
The reason I used wood PLA was because I wanted the keyboard to feel like actual wood, and I saw some guides online that suggested sanding and staining.  
However, I later learned that just painting regular PLA like wood was way simpler, offered much more control, and achieved better results.  
If I were to rebuild this keyboard the same way, I think I would do that instead.  

(sanded 3D model)  
I roughly sanded the printed 3D models with an 80 grit sandpaper to make it absorb the wood stain more easily.  
I could have used 160 or 200 grit sandpaper instead, but I expected the coarse 80 grit sandpaper to shorten the sanding process and produce a more unrefined, natural look opposed to the smooth, layered surface you get 3D printing.  

## Wiring and Electronics


The Ogre zinc alloy keycaps are roughly $48 for 72 caps, making them far cheaper than aluminum or stainless steel keycaps.  
However, as zinc alloy keycaps are notoriously subseptible to discoloration, I might have to replace them after a couple months or years later.  
<Photo>  
I've installed the R4 keycaps upside down in row one and R2 and R3 keycaps in rows two and three, thus creating a somewhat palatable keywell structure. It would have been better to use other keycaps, but as these were the only metal keycaps I were willing to afford, I had to make use of what I could.  


(actual pinout photo)  
  This is my pinout, and the trackball/nice!view sck/mosi/cs pins each can be interchanged with their corresponding positions. Due to trial and error and miswriting pin numbers, I have resulted in the above mess, but I would rather use the pinout below for easier wiring.  
  (Desired pinout photo)  
