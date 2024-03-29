해당 제작기는 독자가 핸드와이어링으로 키보드를 만든 적이 있음을 상정하고 해당 부분은 건너뛰었습니다. 전체 내용은 작성자가 ZMK로 키보드를 빌드한 경험이 없어서 헤멘 경험을 바탕으로 같은 조건에 있는 사람들을 돕기 위해 작성되었습니다.  
   
## 계획하기
이 키보드를 만들기로 결정하면서 가장 우선적으로 달성하고자 한 목표는 정전식 터치 센서를 사용해서 마우스 레이어로 자동으로 전환하게 만드는 것이었습니다.  
ZMK 디스코드에서 ufan 이라는 사용자가 스테인레스 볼 베어링을 써서 구현한 것을 본 적이 있기 때문에 이게 가능하다는 걸 알았고, 그래서 저도 자연스럽게 스테인레스 베어링을 쓰기로 결정했습니다.  
일단 쇠공을 트랙볼로 쓰는 게 결정되었으니, 저는 목재와 금속을 같이 쓰면 뭔가 빈티지 목공예품 느낌으로 인상적인 디자인이 나올 거 같았어요.   
그래서 비록 제작 도중에 정전식 터치가 굳이 필요가 없다는 걸 배워서 해당 기능은 포기했으나, 디자인 방향 자체는 마음에 들어서 계속 진행하기로 했습니다.  
  
기능 면에 있어서는 저는 키보드가 무선으로 동작하고, 버튼 스위치로 켜고 끌 수 있게 만들어서 배터리를 절약하고, 텐트에 자석을 달아서 탈부착하기 쉽게 만들며, nice!view 디스플레이를 달아서 스플릿 연결 상태와 배터리 잔량을 쉽게 알 수 있도록 만들고자 했습니다.  
처음 세 목표는 달성이 가능하다는 걸 알았지만 제작 시점에서는 트랙볼과 디스플레이를 동시에 사용하는 사람을 본 적이 없고 ZMK에서 마우스 기능은 제한적이라서 불확실했습니다.  
앞으로 키보드를 만들기 위해 뭘 해야 할 지 확실해지자 저는 제작 단계로 넘어갔습니다.  
  
제작할 때 유튜브 채널 [EIGAtech의 무선 카리브디스 키보드 제작 영상이](https://www.youtube.com/watch?v=Mks7QDxFreY&t) 크게 도움이 되었고, 관심이 있으신 분께서는 이를 시청하실 것을 권고합니다.  

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
![조잡한 핸드와이어링](Images/11.jpg)  
저는 이 키보드를 핸드와이어링으로 만들었는데, 그 이유는 마침 집에 재료가 다 있었고 돈을 아끼고 싶었기 때문입니다. 이 결정은 나중에 가서 깊이 후회하게 되었는데, 왜냐하면 카리브디스 나노 키보드는 높이가 엄청 낮아서 내부의 전선이랑 핫스왑 소켓이 철판 밑에 있는 바닥에 닿아서 자칫하면 쇼트를 낼 수 있기 때문입니다. 이런 이유로 만약 카리브디스 나노를 제작할 거면 플렉서블 PCB를 쓸 것을 강력하게 권고합니다.  
저는 ZMK 펌웨어를 코딩하는 법을 거의 모르기 때문에 이미 존재하는 펌웨어를 막 뒤져가며 대충 어떻게 돌아가는 거구나 하고 추측을 하는 게 전부였습니다. 키보드를 핸드와이어링하는 게 그래서 엄청 큰 문제가 되었는데, 얘는 제가 MCU에서 어떤 핀에다 전선을 연결하는지 모르니까 PCB를 납땜하듯 그냥 대충 만들고선 펌웨어 설치한다고 해서 저절로 작동하는 게 아니기 때문이에요.  
그래서 만약 이 키보드를 만들 거라면 플렉서블 PCB와 함께 이미 펌웨어에 맞춰서 모든 핀이 다 제대로 설정이 된 [VOID가 만든 nice!nano 홀더를](https://github.com/victorlucachi/Elite-C-holder) 쓰는 게 좋습니다.  
저는 어떤 핀에 와이어링을 해야 하는지 알아내기 위해 [EIGAtech 의 ZMK 펌웨어에](https://github.com/eigatech/zmk-config/tree/charybdis) 들어가서 파일을 전부 뒤져봤고, 그 결과 중요 파일 세 개를 찾았습니다.  

![row2col과 row-gpios](Images/18.jpg)  
  
charybdis.dsti : 이 파일 내에서는 row2col 와 row-gpios 을 찾아 볼 수 있습니다. 
row2col 은 무슨 뜻이냐면 키보드 매트릭스를 스캔할 때 전류가 행에서 출발해서 열로 나간다는 뜻입니다.  
이는 매우 중요한 디테일인데, 전류가 어떤 방향으로 흐르는지 알아야 다이오드를 올바른 방향으로 납땜해서 전류가 반대 방향으로 안 흐르고 정상적으로 작동하게 만들 수 있습니다.  
row-gpios 는 어떤 행이 어떤 핀에 연결되는지 보여줘서 저거에 맞게 와이어링을 하면 됩니다.  
아니면 굳이 똑같은 핀에 고집할 필요 없이 핀 번호를 수정해서 딴 핀에 와이어링하게 만들 수도 있어요.  
이건 일부 예외를 제외하고 모든 핀에 적용되는 사항이니 알아두는 것이 좋습니다.  
  
![col-gpios](Images/19.jpg)  
  
charybdis_left.overlay : 여기서는 col-gpios 를 찾아냈는데, 얘는 어떤 열을 와이어링해야 하는지 보여줘요.  
이때 한 가지 문제가 있었는데, 이 펌웨어는 3x6 배열인 카리브디스 미니 용으로 제작되었는데 문제는 제가 만드는 건 3x5 배열인 카리브디스 나노라는 겁니다.  
즉 이 키보드에는 제가 사용하지 않는 열이 하나 존재하나, 그게 정확히 몇번 열인지를 펌웨어만 보고서는 알 방법이 없었습니다.  
이를 해결하기 위해 저는 일단 2번열을 핀에 연결한 다음에 눌러서 얘의 상대적인 위치를 파악했고, 그래서 키보드에 1번열이 없는 건지 6번열이 없는 건지 확인했습니다.  
1번열이 없는 거였고, 그래서 이 핀은 아무것도 연결하지 않았어요.  
  
![트랙볼 핀](Images/20.jpg)  
  
charybdis_right.overlay : 여기서는 &pinctrl 하고 &spi1 을 찾았습니다. 얘네는 트랙볼 센서를 어떻게 연결해야 하는지 알려줬어요.  

이제 키보드에 nice!view를 달기만 하면 되어서 온라인에 딴 사람들 ZMK 펌웨어를 찾아봐서 이걸 어떻게 추가하는 건지 알아봤습니다.  
  
![niceview charybdis.conf](Images/25.jpg)  
  
Charybdis.conf 파일에는 위에 보이는 대로 CONFIG_ZMK_DISPLAY=y, 그리고 CONFIG_SSD1306=n 를 추가해야 합니다.  
  
![niceview charybdis.dtsi](Images/22.jpg)  
  
charybdis.dtsi 파일에는 &pinctrl 이랑 nice_view_spi 섹션 전체를 위에 보이는 대로 추가해야 합니다.  
  
![niceview charybdis.zmk.yml](Images/23.jpg)  
  
charybdis.zmk.yml 에는 features 라고 쓰인 거 밑에 - display 라고 추가해야 합니다.  
  
![niceview build.yamy](Images/24.jpg)  

그리고 이게 가장 중요한 부분인데, build.yami 파일에는 nice_view 라는 문구를 shield: charybdis_left 하고 shield: charybdis_right 둘 다 뒤쪽에다 붙여써야 합니다.  
요 설정들을 전부 다 해야 nice!view가 작동하는 건지 아닌지는 모르겠는데, 적어도 저는 저걸 다 한 상태에서 nice!view 가 정상 작동했습니다.  
여기서 키보드 이름은 꼭 charybdis 일 필요가 없고 자기 키보드 이름을 쓰기만 하면 됩니다.  
  
![핀아웃](Images/21.png)  
이제 핸드와이어링을 하기 위한 정보를 전부 취합했으니, 저는 위에 보이는 대로 핀아웃을 구성했습니다.  
제 키보드는 1번열을 안 쓰고, 여기서 1번열은 카리브디스 미니에서 새끼손가락으로 누르는 키보드 최외곽열이라는 점을 명심하세요.  
트랙볼이랑 nice!view 가 쓰는 SCK/MOSI/CS 핀들은 서로 위치를 바꿀 수 있습니다.  
비록 제 핀아웃은 엄청 조잡하게 완성되었지만, 만약 이걸 직접 만들 거라면 좀 정리해서 더 깔끔하게 만드는 것을 권고합니다.  
다만 nice!view 랑 트랙볼 센서는 원할히 작동하기 위해 high-freuquency 핀을 써서 연결하는 게 좋습니다.  

![트랙볼 센서 위치 조정](Images/12.jpg)  
트랙볼 센서로 저는 [카리브디스용 pmw-3610 보드](https://github.com/Bastardkb/charybdis-pmw3610-breakout) 대신에 [ufan의 원조 pmw-3610 보드를](https://github.com/ufan/pmw3610_breakout) 썼는데, 그 이유는 이게 더 작고, 어차피 JLCPCB에서 최소 주문량인 5개를 주문해야 하니까 나머지 보드를 써서 다른 키보드를 만들고자 했기 때문입니다.  
하지만 이러면 pmw-3610 센서를 정확한 위치에 고정할 방법이 사라지기 때문에 저는 VOID가 만든 트랙볼 센서 어댑터 파일을 개조해서 pmw-3610 센서를 제자리에 고정할 수 있게 만들었습니다.  
결론적으로는 저는 센서 위치를 완벽하게 맞추는 거는 실패했고, 트랙볼 센서 고정 나사를 대충 조금씩 조이는 방식으로 떼웠습니다.  
제 설정대로 트랙볼을 정상적으로 쓰려면 센서는 반드시 위에 보이는 대로 고정되어야 하며, 이게 엄청 쓰기가 힘들기 때문에 그냥 카리브디스용 보드를 쓰는 걸 강력추천합니다.  

![nice!view 오작동](Images/15.jpg)  

제가 아는 한 아무도 트랙볼이 달린 ZMK 키보드에 nice!view 를 추가한 적이 없어서, 저는 얘네들의 SPI 장치가 어떻게 상호작용할지, SPI 자체가 뭔지도 몰랐습니다. 
처음에는 얘네 둘이 똑같은 SPI 장치를 쓸 수 있다고 생각해서 똑같은 핀에다 연결했고, 그렇게 연결하니까 nice!view가 위에 보이는 것처럼 오작동했습니다.  
지금 와서 생각하면 이는 매우 멍청한 판단이었으나, 해당 분야에 저는 지식이 없다 보니 제가 얼마나 어리석었는지 알 방법이 없었습니다.  
트랙볼에서 보내는 신호가 전부 nice!view 쪽으로 간섭을 해서 이게 문제가 된 거고, 이제는 얘네가 서로 다른 핀을 써야 한다는 걸 알았습니다.  
저는 트랙볼이 spi1, nice!view는 spi3 를 쓰게 설정했고, 트랙볼과 nice!view를 각각 다른 핀에다 연결하니 그제서야 모든 게 정상작동했습니다.  
이 다음에 혹시 얘네가 똑같은 SPI 장치를 쓸 수 있나 테스트하려고 둘 다 spi1을 쓰게 해봤는데, 이때는 nice!view 화면은 정상적으로 떴지만 트랙볼은 전혀 동작하지 않았습니다.  
어쩌면 제가 뭘 잘못 한 걸 수도 있는데, 적어도 자체 테스트 결과 트랙볼 센서와 nice!view 는 서로 다른 핀과 서로 다른 SPI 장치를 써야 한다고 결론을 내렸습니다.  


## 마무리
이제 키보드는 제대로 작동하게 되었으니, 키스위치랑 키캡을 달기만 하면 제작이 끝나게 됩니다.  
저는 시끄러운 키보드는 싫어서 Gazzew 보바 U4 저소음축을 구했고, 빈티지 가구 느낌을 더 끌어내기 위해 오우거 아연합금 메탈 키캡을 구했습니다.  
메탈 키캡은 처음 몇 분은 차갑게 느껴지나 나중 가면 손가락 온기로 데워지고, 가끔 세게 칠 때 금속음이 나는 게 뭔가 간지가 납니다.  
오우거 메탈키캡은 OEM 프로파일을 지녔고 72개에 6만원 하는데, 수십 만원은 깨질 각오를 해야 하는 알루미늄이나 스테인레스 스틸 키캡보다는 훨씬 저렴합니다.  
허나 아연 키캡은 손가락에 있는 땀하고 기름과 반응해서 변색하기로 유명하니, 어쩌면 몇 달이나 몇 년 후에 교체해야 할 수 있습니다.  
![유사 키웰](Images/04.jpg)  
얘는 OEM 키캡이라서 1번행은 R4 키캡을 거꾸로, 2번행과 3번행은 각각 R2 와 R3 키캡을 정방향으로 꽂아서 유사 키웰 구조를 만들었습니다.  
어쩌면 다른 키캡을 쓰는 게 나을 수 있었으나, 제가 구할 수 있는 메탈 키캡은 얘 말고 선택지가 없어서 이게 최선이었습니다.  
유사 키웰은 예상과는 다르게 오목한 구조가 매우 쓰기 편했으나 맨 아래행은 오목하지 않고 좀 평평하다는 인상을 받았습니다.
최소한 저에게 있어서 얘는 DSA 키캡과 비교했을 때 나름의 장단점을 가지고 있을 뿐, 꿀리다고 생각하지 않습니다.  
  
![의자 마운트](Images/05.jpg)  
평소에 저는 맥세이프 어댑터와 141cm 카메라 매직암을 써서 키보드를 의자에 연결해서 씁니다.  
이러면 타이핑하기 편하고, 110mah 배터리로 약 5일 정도 쓸 수 있습니다.  
키보드를 안 쓸 때는 의자에서 탈착한 뒤 텐트에다 올려서 전시합니다.  
  
## 한계점
이걸로 키보드는 완성되었으나 추후에 고쳐야 할 결점이 몇 개 존재합니다.  
![글루건을 써서 고정한 niceview](Images/06.jpg)    
1. nice!view를 비파괴적으로 설치하는 방법이 필요합니다. 저는 그냥 글루건을 써서 고정했는데, 이런 방식으로는 키보드를 일관성있게 제작할 수 없고, 언젠간 nice!view가 망가져서 교체할 때는 매우 골치가 아플 겁니다.  
2. 우측 스플릿을 의자에서 탈착할 때 가끔 키보드가 리셋됩니다. 어딘가에서 전선이 쇼트를 일으켜서 이러는 거 같은데, 제 와이어링이 엉망이라서 현실적으로 이걸 고칠 방법이 없습니다.  
3. ZMK 펌웨어가 구식입니다. 키보드를 켜고 끌 때마다 좌측 슬레이브가 우측 마스터와 연결하지 못하는데, 이거는 당장 CONFIG_ZMK_BLE_EXPERIMENTAL_CONN=y 를 charybdis.conf 파일에 추가하는 걸로 해결했습니다. 그러나 부작용으로 좌측 스플릿 건전지도 우측만큼 빨리 닳아서 원래 사용시간인 한 달만큼 쓰지 못하고 5일만에 거의 방전이 됩니다. 이건 최신 ZMK 포인터 브랜치 펌웨어를 쓰는 걸로 상대적으로 쉽게 해결할 수 있습니다.  
4. 3x5 카리브디스 나노 펌웨어가 아니라 3x6 카리브디스 미니 펌웨어를 쓰고 있습니다. 비록 기능상 문제는 없긴 하지만 키맵이 3x6 배열이라서 안 쓰는 최외곽열이 계속 있는 게 헷갈립니다. 이는 펌웨어에서 3x5 배열이라고 애초부터 설정하는 게 더 낫습니다.  
5. 트랙볼 센서는 완벽하게 정렬되지 못했습니다. 이게 VOID 의 pmw-3610 어댑터를 써서 ufan의 보드를 고정하는 방식이다 보니, 언제나 똑같은 위치와 높이에 고정되는 카리브디스용 pmw-3610 보드에 비해 위치가 덜 정확합니다. 이렇다 보니 가끔 트랙볼이 작동하지 않을 때가 있는데, 그럴 때마다 트랙볼 센서 고정부 바닥을 꾸욱 누르고 트랙볼을 몇 번 두들겨야 다시 작동합니다. 이를 고치려면 VOID의 pmw-3610 어댑터랑 트랙볼 센서 바닥 모델링을 더 개조해야 하는데, 지금 그걸 하고 있긴 한데 제대로 결과가 나올 때까지는 시행착오를 엄청 겪어야 합니다.  

위에 나열된 한계점을 이유로 저는 이 키보드를 제가 제작한 방식대로 만드는 것을 추천하지 않습니다.  
대신에 플렉서블 PCB, 카리브디스용 pmw-3610 보드, [VOID가 만든 nice!nano 홀더를](https://github.com/victorlucachi/Elite-C-holder)를 쓰고, nice!view 는 일단 안 쓰는 걸 권고합니다.  
한 번에 필요한 재료를 사는 데 있어서 [BastardKB에서 파는 카리브디스 키트를](https://bastardkb.com/charybdis) 구매하는 것도 좋습니다.  
아마 미래에는 3D 모델링 파일을 업데이트할 수도 있는데, 일단은 지금 쓰는 거에 만족해서 이걸 개선하기 위해서는 저한테 매우 큰 동기와 학습이 필요할 겁니다.
