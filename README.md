# SmartOnmyoji

> 为了解放双手，特意学了python，虽然已经有很多大佬写了类似的脚本，但自己主要是利用这个项目学习python，所以有很多被注释的代码片段和注释啥的（大部分代码都可以删除，其实100行左右就能实现），写完之后，基本了解了opencv的目标检测方法和一些图像处理的方法，以及图像处理的一些原理，包括期间还看了神经网络和深度学习的一些知识（虽然没用上，不过以后可以用在砸百鬼上）

### 依赖库
进入根目录下，安装 requirements.txt 里的依赖库：pywin32、opencv-python、PyQt5、PyAutoGUI
``` 
pip install -r requirements.txt
```

### 使用方法
- 先安装python3.7（基于 python3.7.6 开发）, 再安装上述依赖库
- 【管理员身份运行IDE或CMD或powershell】, 执行 python smart_onmyoji_start.py
- 阴阳师电脑版使用模板匹配时，不要调分辨率，如果要调分辨率，需要重新截图，然后放到/img目录的对应文件夹下面
- 如果发现总是匹配失败，可能是/img模板图片大小问题，可以重新截图，或使用特征点匹配方法，或切换为 **兼容模式** ，也可自行调试代码看截图是否成功，找看看是哪儿的问题
- **支持后台点击**，但不支持部分窗体（如网易MuMu、网易云游戏），可以切换为 **兼容模式** 以兼容这些窗体，兼容模式下不能后台点击
- 支持安卓手机，需用USB连上电脑，并打开手机调试模式，使用 安卓-ADB 模式时，可以使用特征点匹配方式，不过有点慢，要不就重新截图替换/img目录下的全部图片
- 特征点匹配方法适用窗体中没有多个相同的待检测目标，而且待检测目标与周围差异比较大，否则会不准确
- 压缩率设置在0.6左右时，准确率和速度能兼顾，如果对匹配速度可以忍受，不建议修改压缩率（压缩率越低，准确度越低）
- 原理是定时截图，然后找到图片坐标，然后随机延迟并点击附近随机坐标
- 除了阴阳师，也可以其他点点点的游戏，比如连手机抢微信红包啥的~
- 只要每天不刷满300次，理论上不会收到鬼使黑的信

### 功能预览

- UI界面、可配置参数：可修改执行时间、间隔时间、匹配方式、压缩率、执行完成后的操作等

![image](https://user-images.githubusercontent.com/39365915/160130249-62554943-f746-4a56-91f9-9898f4267685.png)



- 模板匹配方法：不能随意调整窗体分辨率，模板图片与窗体中的部分必须一致

![image](https://user-images.githubusercontent.com/39365915/158008385-6d661a3f-51a7-44c0-9b8b-b872cfed60eb.png)



- 特征点匹配方法：可以随便调整窗体分辨率，也可以对目标图片旋转、缩放，都可以匹配到

![image](https://user-images.githubusercontent.com/39365915/158009257-97dbc188-aa5a-4eb6-a559-03cae7e0a5d1.png)



### 计划
- [x] 支持abd模式，电脑连手机自动截图
- [x] 支持切换选择匹配模式，特征点匹配（自适应分辨率，不用重新截图，但速度略慢，且不太准确）、模板匹配（速度更快，更精确，但麻烦，不能改分辨率）
- [x] 加载图片时记录所有图片的特征信息，优化识别速度
- [x] 支持压缩图片以提升脚本识别速度，默认为1不压缩
- [x] 所有图片转灰度图，并保存在内存里，识别速度快多了
- [x] 修复中文路径报错的问题
- [x] 兼容所有windows窗体的截图和点击
- [x] 使用QT5重构UI界面
- [ ] 增加选择自定义匹配图片文件夹的功能
- [ ] 优化百鬼夜行的选式神和砸豆子逻辑（yolov5）
- [ ] 增加御灵、地域鬼王、逢魔、秘闻副本等默认场景

### 更新记录
- 2022年3月31日 移除重复的依赖，运行时检测是否使用管理员身份运行，脚本默认包含adb程序，为代码增加部分注释
- 2022年3月25日 使用PYQT5重构GUI，使用pyautogui替换pymouse库
- 2022年3月12日 增加兼容模式，支持在所有的 windows窗体 截图和点击，包括模拟器、云游戏、scrcpy 等， 兼容模式下 **窗体会自动置顶，不再支持后台点击**
- 2022年3月10日 增加鼠标点击选择窗体的功能，（窗口标题名称 - 下拉选择 “开始后鼠标点击选择窗体”，5秒内点击要匹配窗体）
- 2022年1月27日 修复opencv在中文路径下报错的问题
- 2022年1月26日 重新加入模板匹配方法，并设为默认方法，因为发现匹配速度有点慢，准确率不太高
- 2022年1月19日 优化匹配速度，截图和读取模板图片时先转灰度，支持对截图设置压缩率，进一步优化匹配速度；更换全部匹配方法为sift匹配；增加对安卓设备的支持，通过ADB实现；
- 2022年1月15日 首次提交，自动截图、匹配、点击

### 其他说明
仅作学习用途，请勿用于其他非法途径！
