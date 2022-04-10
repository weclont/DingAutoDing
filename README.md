# DingAutoDing
钉钉自动进入直播python脚本，支持Windows服务器

**[博客地址](https://blog.fwder.cn/2022/02/08/%E3%80%90%E6%95%99%E7%A8%8B%E3%80%91%E9%92%89%E9%92%89%E5%A4%9A%E5%BC%80-%E6%8C%82%E7%BD%91%E8%AF%BE%E6%95%99%E7%A8%8B%E5%8F%8A%E6%BA%90%E7%A0%81%E5%88%86%E4%BA%AB)**

## 准备

首先，你要有一台闲置的电脑/Windows服务器，并且可以远程连接。

确保你的远程设备上安装了python，这样你才能执行源码。

在Github上下载源码，放到远程设备的桌面上。

然后在cmd中执行：

`pip install pywin32 numpy pyautogui opencv-python pillow pytesseract`

安装所需的py库。

确保你的设备上安装了Tesseract-OCR，并且成功配置了pytesseract.py文件
如果没有配置，请参考这篇教程：[https://www.imooc.com/article/75351](https://www.imooc.com/article/75351)

如果需要挂钉钉多开，你需要参照 [逼乎上钉钉的多开方法](https://zhuanlan.zhihu.com/p/373245935?ivk_sa=1024320u) 的方法二来完成钉钉多开，具体请看教程。

## 教程

1. 打开钉钉客户端，如果不需要多开，请跳到第5步。
2. 下载 [procexp_Chn64.exe](https://down.fwder.cn/other/procexp_Chn64.exe) 并放到桌面上，以管理员身份运行。![](https://www.fwder.cn/usr/uploads/2022/02/1688890231.jpg)
3. 登陆第一个钉钉后找到最后一个钉钉图标，选中后按下Ctrl+L，在下方的参数列表界面上找到如图示的两个参数，并且右键选择“关闭句柄”：![](https://www.fwder.cn/usr/uploads/2022/02/3786399592.jpg)
4. 此时你可以打开另一个钉钉并登录，如果想开更多个钉钉就重复第3步即可。
5. 将所有登录的钉钉全部打开主页面，全部选择想要自动进直播的群，并且确保所有的钉钉窗口都尽量放在屏幕正中间（钉钉窗口被遮挡时可能影响程序的文本识别），然后最小化所有钉钉窗口。
6. 如果你使用的是闲置电脑（没有使用远程连接），请看第7步-第9步；如果你使用的是Windows服务器（通过使用远程连接运行），请看第10步-第12步。
7. 闲置电脑不能设置自动休眠和屏幕关闭，需要一直常亮，具体设置方法请百度。
8. 双击start.bat开始运行，这时程序会自动遍历一遍钉钉窗口的句柄；
   在程序运行时不能随意关闭钉钉窗口，不要移动鼠标，确保程序正常执行。
9. 确保你的屏幕一直有信号输出，否则程序将无法正常执行
10. Windows服务器需要带UI页面，否则不能执行。
11. 在程序执行时，需要继续保持远程连接且不能最小化远程连接UI窗口，否则程序会报错。
    （最好使用Windows的分桌面功能，为远程连接窗口单独分一个桌面）
12. 双击start.bat开始运行，这时程序会自动遍历一遍钉钉窗口的句柄；
    在程序运行时不能随意关闭钉钉窗口，不要移动鼠标，确保程序正常执行。

经测试，程序在1920x1080 125%dpi的页面下成功运行。
如果你的dpi和我的不匹配，建议自行更改程序代码或者改dpi。
