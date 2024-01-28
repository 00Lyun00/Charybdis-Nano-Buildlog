해당 제작기는 독자가 핸드와이어링으로 키보드를 만든 적이 있음을 상정하고 해당 부분은 건너뛰었습니다. 전체 내용은 작성자가 ZMK로 키보드를 빌드한 경험이 없어서 헤멘 경험을 바탕으로 같은 조건에 있는 사람들을 돕기 위해 작성되었습니다.  
   
## 계획하기
이 키보드를 만들기로 결정하면서 가장 우선적으로 달성하고자 한 목표는 정전식 터치 센서를 사용해서 마우스 레이어로 자동으로 전환하게 만드는 것이었습니다.  
ZMK 디스코드에서 ufan 이라는 사용자가 스테인레스 볼 베어링을 써서 구현한 것을 본 적이 있기 때문에 이게 가능하다는 걸 알았고, 그래서 저도 자연스럽게 스테인레스 베어링을 쓰기로 결정했습니다.  
일단 쇠공을 트랙볼로 쓰는 게 결정되었으니, 저는 목재와 금속을 같이 쓰면 뭔가 빈티지 목공예품 느낌으로 인상적인 디자인이 나올 거 같았어요.   
그래서 비록 제작 도중에 정전식 터치가 굳이 필요가 없다는 걸 배워서 해당 기능은 포기했으나, 디자인 방향 자체는 마음에 들어서 계속 진행하기로 했습니다.  
  
기능 면에 있어서는 저는 키보드가 무선으로 동작하고, 버튼 스위치로 켜고 끌 수 있게 만들어서 배터리를 절약하고, 텐트에 자석을 달아서 탈부착하기 쉽게 만들며, nice!view 디스플레이를 달아서 스플릿 연결 상태와 배터리 잔량을 쉽게 알 수 있도록 만들고자 했습니다.  
처음 세 목표는 달성이 가능하다는 걸 알았지만 제작 시점에서는 트랙볼과 디스플레이를 동시에 사용하는 사람을 본 적이 없고 ZMK에서 마우스 기능은 제한적이라서 불확실했습니다.  
앞으로 키보드를 만들기 위해 뭘 해야 할 지 확실해지자 저는 제작 단계로 넘어갔습니다.  
  
제작할 때 유튜브 채널 [EIGAtech의 무선 카리브디스 키보드 제작 영상,](https://www.youtube.com/watch?v=Mks7QDxFreY&t)이 크게 도움이 되었고, 관심이 있으신 분께서는 이를 시청하실 것을 권고합니다.  

## 모델링
![정측면 각도에서 본 수정한 모델링](Images/16.jpg)  
저는 퓨전360 기능을 거의 모르지만 어차피 제가 수정하는 거는 매우 간단한 것들에 불과해서 제작 과정이 크게 지체되지 않았습니다.  
처음에는 케이스 옆면에 버튼 스위치가 들어갈 구멍을 하나 뚫고, 앞면에 TRRS 커넥터가 꽂히는 구멍을 메웠습니다.  
핸드와이어링할 때 쓰는 MCU 홀더도 모양을 좀 수정해서 TRRS 커넥터 지탱하는 부분을 없애고, 밀맥스 소켓을 꽂을 수 있게 만들고, 3x6 리셋 버튼을 쓰게 만들었습니다.  
여기까지는 다 쉬웠는데, 이제 nice!view 를 다는 곳을 만들려 하다 보니 애초에 이걸 붙잡을 수 있는 벽 자체가 없었습니다.  
그래서 원 제작자인 [BastardKB가 키보드 디자인 과정을 보여주는 유튜브 영상을](https://youtu.be/scoX8NZv4MI?si=uietOpE2jdQoaGku&t=1031) 참고해서 똑같은 방법으로 측면에 벽을 만들었고, 그 다음에 사각형 모양 구멍을 뚫어서 nice!view가 딱 맞게 들어가도록 만들었어요.  
![실력부족을 보여주는 nice!view 지지대 하자품들](Images/14.jpg)  
만약 제가 퓨전을 제대로 쓸 줄 알았다면 무슨 걸쇠나 기타 지지 부품을 만들어서 nice!view가 제자리에 고정되게 만들었을 건데  
저는 제가 뭘 하는지도 잘 모르는 상태였기 때문에 그냥 여기서 멈추고 글루건 써서 고정하기로 했습니다.    
  
![스켈레틸 결함](Images/26.jpg)  
  
스켈레틸 케이스는 벽 부분이 위쪽으로 돌출되는 결함을 지녔습니다.  
제 능력으로는 이걸 고칠 수가 없어서 그냥 3D프린팅을 한 뒤 사포로 갈아서 없앴습니다.  
  
![텐트 모델링](Images/17.jpg)  
키보드 텐트에도 지름이 6cm인 자석을 달 수 있게 구멍을 네 개 뚫었습니다.  
앞쪽은 3x6 자석을 두 개씩 넣을 수 있을 정도로 높았고, 뒤쪽은 높이가 워낙 낮아서 2x6 자석을 하나씩만 겨우 넣을 수 있었습니다.  
자석을 이 정도로는 써야 키보드가 미끄러지지 않고 제자리에 고정되었습니다.  
  
## 3D 프린팅, 사포질, 우드 스테이닝
![사포질이 안된 텐트](Images/07.jpg)  
모델링 단계가 끝난 뒤 저는 우드 PLA 필라멘트를 써서 케이스와 텐트를 프린팅했습니다.  
우드 필라멘트를 쓴 이유는 키보드를 최대한 진짜 목공예품처럼 느껴지게 하고 싶어서 그랬고, 온라인에서 찾아보니 우드 필라멘트를 사포질하고 스테이닝 하는 게 좋은 결과를 가져온다는 글을 찾았기 때문입니다.  
허나 제작 도중에 그냥 일반 필라멘트로 뽑은 뒤 나무 느낌으로 도색하는 거가 훨씬 절차가 쉽고, 더 세세적으로 조절하기 편하며, 결과물도 더 좋다는 걸 배웠습니다.  
만약 제가 이 키보드를 다시 만든다면 그때는 그냥 일반 필라멘트로 도색을 할 것 같습니다.  
  
![사포질이 끝난 텐트](Images/08.jpg)  
저는 80방 사포를 써서 키보드 표면을 사포질해서 우드 스테인을 더 잘 흡수할 수 있게 만들었습니다.  
이때 160방이나 200방을 쓸 수도 있는데, 저는 80방 쓰는 게 전체 사포질 과정을 단축시키고, 원래의 미끈하고 층층이 쌓인 3D프린팅 표면보다 더 거칠고 자연스러운 나무 느낌을 내는 것을 기대했습니다.  
또한 사포질하면서 계단현상이 안 보이게 표면을 최대한 미끈하게 만들었습니다.  
  
![케이스 스테이닝 전후 비교](Images/09.jpg)  
![완성된 케이스](Images/10.jpg)  
키보드 케이스와 텐트를 전부 사포질한 뒤, 대충 싸구려 우드 스테인으로 두 세 번 정도 코팅해서 칠하고 무광 바니쉬를 마무리로 발라줬습니다.  
최종 결과물은 제가 원했던 것보다 너무 밝은 붉은색이 되었지만 그럭저럭 받아들일 만해서 다음 단계로 넘어갔습니다.  

## 와이어링과 펌웨어
![Messy handwiring](Images/11.jpg)  
I handwired the keyboard because I happened to have everything I needed, and I wanted to save some money. I deeply regret this decision as the inner height of the Charybdis Nano is so low that the wire and hotswap sockets could touch the floor beneath the metal plate and potentially cause shorts. Due to this reason, I strongly recommend using flexible PCBs if you were to build a Charybdis Nano yourself.  
As I have little to no knowledge about electronics, all I am doing is guesswork based on pre-existing builds. This acted as a major obstacle for handwiring this keyboard as it meant I couldn't just install the firmware and had to figure out which wires were connected to which pin on the MCU.  
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

Now I just had to learn how to add a nice!view to the keyboard, so I searched online to find ZMK configs that had nice!view added to their keyboards.  
  
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
Please note that column 1 isn't used for my keyboard, and it represents the sixth and outermost column you press with your pinky.  
The trackball/nice!view SCK/MOSI/CS pins each can be interchanged with their corresponding positions.  
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


## 마무리
With the keyboard now functioning properly, I just had to get keyswitches and keycaps to finish the build.  
I got Gazzew Boba U4 keyswitches as I prefer having no noise, and I got a set of Ogre zinc alloy keycaps to further push the metal-wood aesthetics.  
They feel cold to touch for the first couple minutes, but they'll warm up eventually. Sometimes they make a metallic clank sound when I type, which I think is cool.  
The Ogre keycaps are sold in Korea for roughly $48 for 72 caps, making them far more affordable than aluminum or stainless steel keycaps.  
However, as zinc alloy keycaps are notoriously subseptible to discoloration, I might have to replace them after a couple months or years later.  
![Pseudo-keywell](Images/04.jpg)  
I've installed the R4 keycaps upside down on row one and R2 and R3 keycaps on rows two and three, thus creating a pseudo-keywell structure.  
It would have been better to use other keycaps, but as these were the only metal keycaps I was willing to afford, I had to make use of what I could.  
The pseudo-keywell had a surprisingly satisfying curvature, although the bottom row felt a bit flat. To me, it is not inferior to uniform DSA keycaps, albeit having strengths and shortcomings in different areas.  
![Captain's chair](Images/05.jpg)  
I mainly use the keyboard clamped to my chair with MagSafe adapters and 141cm magic arms.  
It is very convenient to type with, and the 100mah battery lasts about 5 days.  
When I don't use the keyboard, I detach both halves and place them on the magnetic alien tents as display.    

## 한계점
Now with the keyboard finished, there are some huge flaws that must be fixed.  
![nice!view hotglued in place](Images/06.jpg)    
1. The nice!view must have a non-destructive way to install. I just hotglued mine and they work fine to me, but this is not a reliable way to manufacture a keyboard, and I will have a huge problem replacing them when they eventually break down.  
2. The right half resets sometimes when I detach it from the chair. I believe this is happening due to a short, but it is practically impossible to address as I did a messy job handwiring the keyboard.  
3. My ZMK config is outdated. Whenever I turn off the keyboards, the peripheral left half loses connection to the right half and fails pairing. This was fixed by adding CONFIG_ZMK_BLE_EXPERIMENTAL_CONN=y in charybdis.conf, but it in turn drains the left half's battery extremely fast, so it also only lasts about 5 days and not the expected one month. I can actually fix this easily by using the most recent ZMK pointer branch, so it isn't as critical as the other flaws. 
4. I am using a 3x6 Charybdis Mini firmware instead of a 3x5 Charybdis Nano firmware. Although it is functioning perfectly, I am basically using a 3x6 keymap with all of the outer column keys left blank. It is a bit of a hassle to work with, and it would be much more nice to just set it as a 3x5 keyboard in the first place.  
5. The trackball sensor isn't perfectly aligned to the trackball. As I fastened ufan's breakboard by modifying VOID's pmw-3610 adapter, it is less precisely positioned than the Charybdis pmw-3610 breakboard that is always guaranteed to be in the same height and orientation. Due to this flaw, the track ball sometimes doesn't work, and I have to press on the bottom of the cover and tap it a bit to make it work properly. This can be fixed by modifying VOID's pmw-3610 adapter and the trackball sensor bottom cover, but although I am currently working on it right now, it will take a huge amount of trial and error.  

Because of the reasons listed, I do not recommend building this keyboard the way I did.  
Instead, I'd recommend using flexible PCBs, the Charybdis pmw-3610 breakboard, and not using nice!views for the current time.  
And I would also recommend buying [BastardKB's Charybdis kit](https://bastardkb.com/charybdis) as it's a very nice way to get most of the materials.  
Maybe I will update the 3D files in the future, but I am mentally satisfied with what I have accomplished, and it will take a lot of motivation and learning until I muster up the will to fix them.  
