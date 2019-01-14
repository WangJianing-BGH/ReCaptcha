<p align =“center”>：警告：此代码适用于最新版本的ReCaptcha。仅限用于您出于教育目的而控制的网站。 ：警告：</ p>

项目创建于2017年4月，`[WangJianing-Blog]`（https://www.bytedd.com"王嘉宁的博客"）的准确率达到了85％，击败了Google的ReCaptcha。在这项工作发布后，Google发布了ReCaptcha的更新，其中包含以下主要更改：
*更好的浏览器自动检测
*口语短语而不是数字

这些变化最初成功地防止了原来的unCaptcha攻击。但是，截至2018年6月，这些挑战已经解决。我们已经与ReCaptcha团队联系了六个多月，他们完全了解这次袭击事件。尽管目前取得了成功，但该团队已允许我们发布代码。

＃介绍unCaptcha2

由于音频挑战的变化，通过ReCaptcha比以往更容易。现在，代码只需向一个免费的，公开发布的语音文本API发出单一请求，即可在所有验证码上实现约90％的准确率*。

由于对ReCaptcha的更改阻止了浏览器自动化引擎Selenium，因此unCaptcha2使用屏幕点击器移动到屏幕上的某些像素，并像人一样在页面上移动。这里肯定有工作要做 - 需要为每个新用户更新坐标，而且不是最强大的。

＃ 该方法

unCaptcha2的方法很简单：
1.导航到Google的ReCaptcha演示网站
2.导航到ReCaptcha的音频挑战
3.下载音频挑战
4.将语音提示提交到语音到文本
5.解析响应并输入答案
6.按提交并检查是否成功

#演示

！[VID]（https://user-images.githubusercontent.com/14065974/45004579-df021180-afbb-11e8-8598-177159ed09b4.gif）

＃ 如何使用

由于unCaptcha2必须转到屏幕上的特定坐标，因此您需要根据您的设置更新坐标。这些坐标位于run.py的顶部。在Linux上，使用命令`xdotool getmouselocation --shell`来查找鼠标的坐标可能会有所帮助。

您还需要为您选择的任何语音到文本API设置凭据。由于谷歌，微软和IBM的语音到文本系统看起来效果最好，因此这些系统已包含在queryAPI.py中。您必须根据需要设置用户名和密码;对于Google的API，您必须使用包含Google应用程序凭据的文件设置环境变量（GOOGLE_APPLICATION_CREDENTIALS）。

最后，使用`pip install -r dependencies.txt`安装依赖项。

＃负责任的披露

本项目破解团队在2018年6月联系了Recaptcha团队，提醒他们Recaptcha系统的更新使其安全性降低，正式问题于2018年6月27日开始。我们很快就展示了这次攻击的全功能版本。他们选择在初次披露后等待6个月，让Recaptcha团队有时间解决Recaptcha系统中的基础架构问题。 Recaptcha团队知道这个攻击媒介，并且已经确认他们对我们发布此代码是好的，尽管它目前的成功率。

这个攻击媒介被认为超出了bug赏金计划的范围。

＃免责声明

与原始版本一样，unCaptcha2旨在成为概念证明。当Google更新其服务时，此存储库将不会*更新。因此，预计它不会在未来发挥作用，并且可能随时中断。

不幸的是，由于谷歌在浏览器自动化检测方面的工作，这个版本的unCaptcha不使用Selenium。因此，代码必须导航到屏幕的特定部分。要查看unCaptcha为自己工作，您需要更改屏幕分辨率的坐标。

虽然unCaptcha2适用于Google的Demo网站，但它可以更改为适用于任何此类网站 - 击败ReCaptcha的逻辑将是相同的。

此外，我们已从所有必要的查询中删除了我们的API密钥。如果您希望重新创建某些工作或在此区域进行自己的研究，则需要从所使用的六种服务中获取API密钥。这些键在我们的文件中由一长串字符'X'描绘。值得注意的是，防止创建多个API密钥的唯一保护是ReCaptcha  - 因此，通过解析验证码以注册新的API密钥，可以使unCaptcha自给自足。

如有帮助请访问我的网站，接收更过精彩内容！

[WangJianing-Blog]（https://www.bytedd.com"王嘉宁的博客"）

[ReCaptcha开源](https://github.com/WangJianing-BGH/ReCaptcha)

[项目原文](https://github.com/ecthros/uncaptcha2.git)
