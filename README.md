# Access Control System with pi

## Concept Development 動機發想

<!-- Why does your team want to build this idea/project?  -->
有些資料與物品具有非常高的價值，以防內鬼誕生之後沒有人能守護，因此做一個以rasberry-pi執行的門禁系統，以USB camera讀入影像辨識人臉，先以opencv進行訓練並註冊，如果是註冊過的就可以亮led燈表示通過，並透過telegram bot會傳送他的名子說他來了，若是沒有註冊過的則會使蜂鳴器叫並解透過telegram提醒說這是沒註冊的人，並且會顯示畫面裡的人的情緒、年齡、人種、性別。
## Implementation Resources 硬體設備

<!-- e.g., How many Raspberry Pi? How much you spent on these resources? -->
- 1塊Raspberry Pi Model 3B
- 1塊麵包版
- 1個蜂鳴器
- 杜邦線
- 1個LED
- 1個電阻(防LED燒壞)
   
## Existing Library/Software 軟體架構

<!-- Which libraries do you use while you implement the project -->
- python3
- GPIO module(樹梅派內建就有)
- python-telegram-bot(為了通知在遠端的使用者用telegram做interface)
- opencv(影像辨識)
- deepface(辨識人臉情緒、年齡、人種)

## Implementation Process

<!-- What kind of problems you encounter, and how did you resolve the issue? -->
因為樹梅派跑不太動深度學習的人臉辨識，因此使用了cv2取代做人臉辨識與偵測

## Knowledge from Lecture

<!-- What kind of knowledge did you use on this project? -->


## Installation

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
```
- telegram bot 套件下載
```
$ git clone https://github.com/python-telegram-bot/python-telegram-bot
$ cd python-telegram-bot
$ python3 setup.py install
```

- 並且去telegram找`@BotFather`申請一個機器人


## Usage

<!-- How to use your project -->

## Job Assignment
- 歐丞言
    - 寫github
    - 建立telegram bot
    - python programming
- 郝健皓

- 陳奕宏

- 陳俊維
## References

- [Python Telegram Bot  gtihub](https://github.com/python-telegram-bot/python-telegram-bot)
- [Python Telegram Bot Document](https://docs.python-telegram-bot.org/en/stable/index.html)
- [GPIO教學 github](https://github.com/piepie-tw/gpio-game-console)
- [Opencv辨識人臉教學](https://steam.oxxostudio.tw/category/python/ai/ai-face-recognizer.html)
- [deepface情緒辨識](https://steam.oxxostudio.tw/category/python/ai/ai-emotion.html)
