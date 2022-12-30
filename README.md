# Access Control System with pi

## Concept Development 動機發想

<!-- Why does your team want to build this idea/project?  -->
有些資料與物品具有非常高的價值，以防內鬼誕生之後沒有人能守護，因此做一個以rasberry-pi執行的門禁系統，以USB camera讀入影像辨識人臉，先以opencv進行訓練並註冊，如果是註冊過的就可以亮led燈表示通過，並透過telegram bot會傳送他的名子說他來了，若是沒有註冊過的則會使蜂鳴器叫並解透過telegram提醒說這是沒註冊的人，並且會顯示畫面裡的人的情緒、年齡。
## Implementation Resources 硬體設備

<!-- e.g., How many Raspberry Pi? How much you spent on these resources? -->
- 1塊Raspberry Pi Model 3B
- 1台webcam
- 1塊麵包版
- 1個蜂鳴器
- 杜邦線至少4條
- 1個LED
- 1個電阻(防LED燒壞)

   
## Existing Library/Software 軟體架構

<!-- Which libraries do you use while you implement the project -->
- python3.9.2
- GPIO module(樹梅派內建就有)
- python-telegram-bot(為了通知在遠端的使用者用telegram做interface)
- opencv(影像辨識)
- deepface(辨識人臉情緒、年齡、人種)

## Implementation Process

<!-- What kind of problems you encounter, and how did you resolve the issue? -->
- 因為樹梅派跑不太動深度學習的人臉辨識，因此使用了cv2取代做人臉辨識與偵測，其實可以先sever端訓練好之後再把model丟到樹梅派裡就好

- 直接`pip install tensorflow`會使樹梅派當機
因此使用了`pip install tflite-runtime`下載tensorflow-lite
## Knowledge from Lecture

<!-- What kind of knowledge did you use on this project? -->


## Installation 預先下載

<!-- How do the user install with your project? -->

- 更新/取得最新版本的軟體資訊及下載文字編輯器vim
```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install vim
```
- 下載python專屬套件(使用pip)
```
$ pip install opencv_python
$ pip install opencv_contrib_python
$ pip install tflite-runtime
$ pip install deepface
```

- 並且去telegram找`@BotFather`申請一個機器人

![](https://github.com/doudou030/Access_Control_System_with_pi/blob/main/img/creatbot.jpg?raw=true)
- 下載人臉追蹤模型(要記好位置)
```
$ wget https://github.com/kipr/opencv/raw/master/data/haarcascades/haarcascade_frontalface_default.xml
```
## Usage 使用方法
<!-- How to use your project -->

- GPIO接線
![](https://github.com/doudou030/Access_Control_System_with_pi/blob/main/img/pin.jpg?raw=true)

- 下載程式碼並增加使用權限
```
$ git clone https://github.com/doudou030/Access_Control_System_with_pi.git
$ cd Access_Control_System_with_pi
$ chmod +755 run
```
- 註冊自己的臉
    - 先多自拍幾張存好並命名成{number}.jpeg 例: 1.jpeg、2.jpeg
    - 並存在**自己知道位置**的資料夾
```
$ vim train.py
```
- 改成自己bot的token與chat id
```
$ vim main.py
```
- 執行
```
$ ./run
```
## Job Assignment 工作分配
- 歐丞言
    - 寫github
    - 建立telegram bot
    - python programming
- 郝健皓
    - python debugging
    - 醬油小老師
- 陳奕宏
    - 英文小達人
    - 醬油顧問
- 陳俊維
    - telegram bot programming
    - 醬油本人

## References

- [Python Telegram Bot  gtihub](https://github.com/python-telegram-bot/python-telegram-bot)
- [Python Telegram Bot Document](https://docs.python-telegram-bot.org/en/stable/index.html)
- [GPIO教學 github](https://github.com/piepie-tw/gpio-game-console)
- [Opencv辨識人臉教學](https://steam.oxxostudio.tw/category/python/ai/ai-face-recognizer.html)
- [deepface情緒辨識](https://steam.oxxostudio.tw/category/python/ai/ai-emotion.html)
- [電路模擬圖tinkercad](https://www.tinkercad.com/dashboard)
