# xp_CAPTCHA V4.2(瞎跑-白嫖版)

* 若要准确率更高，请用 https://github.com/smxiazi/xp_CAPTCHA （这个调用别人商业成熟的验证码识别接口）

## 注意
* 默认使用jdk1.8编译
* 在最新版的burp2.x中jdk为1x,会导致插件不可用,,使用jdk8编译到不行，请下载jdk16版本试试,若还不行，请自行下载源码使用当前电脑的jdk1x进行编译,谢谢。
* 爆破时，记得把线程设置为1。

**********

### 更新4.2 2022-9-5

* 新增支持从验证码反回包中获取内容填充到请求包中（该功能可以支持uuid验证码格式以及其他类似模式）
* 如果下载我打包好的环境的，请替换掉对应的server.py脚本，本次更新有涉及到该脚本的更新。

<img width="1404" alt="image" src="https://user-images.githubusercontent.com/30351807/188346185-917da8a5-62a1-4095-97ce-ff9896b558ea.png">


*********

### 说明
xp_CAPTCHA (白嫖版)
* 验证码识别
* burp插件
* 支持验证码返回包为json格式

*********
### 使用
* 用python3 启动server.py服务
* 把对应的关键字写在填写验证码处即可

<img width="1255" alt="image" src="https://user-images.githubusercontent.com/30351807/175557148-b6b7fa0f-5f7a-49fd-9a2a-4c51eda7e0bf.png">

<img width="1250" alt="image" src="https://user-images.githubusercontent.com/30351807/175553590-9702d872-26a3-4b87-8b3c-0b6a6831e4ab.png">

<img width="1204" alt="image" src="https://user-images.githubusercontent.com/30351807/175553779-103f90f5-2283-4022-ad32-87eee8443086.png">

<img width="1214" alt="image" src="https://user-images.githubusercontent.com/30351807/175557360-8a4b976c-6e73-42f0-9053-d087c3bbc442.png">

<img width="665" alt="image" src="https://user-images.githubusercontent.com/30351807/175557566-66e46ff9-4bcc-40de-82ad-fed3ff8bc37d.png">

### 高级设置使用

* 验证码响应体模式

每次获取验证码，他返回包为json格式，其中包含了一个字段为uuid，每次登录时都会要求账户密码验证码和uuid一起请求。
<img width="1397" alt="image" src="https://user-images.githubusercontent.com/30351807/188490525-c69cabf9-68aa-4c75-874a-1fb22ea37ebc.png">

正常使用正则即可
<img width="1418" alt="image" src="https://user-images.githubusercontent.com/30351807/188490926-fe351131-f1f9-4a25-8612-3dc5d7b5180d.png">

<img width="1392" alt="image" src="https://user-images.githubusercontent.com/30351807/188491180-c6da6d0b-fbc5-4094-b35c-7d118755b7fd.png">




* 验证码响应头模式

该站每次请求获取验证码，都会重新设置cookie。
<img width="1410" alt="image" src="https://user-images.githubusercontent.com/30351807/188486933-e086f07a-2aaa-49e5-832a-8d83d4abcb63.png">

响应头部的正则参数语法：
响应头对应的参数名|对应参数值的正则匹配。如我这个站是从 `Set-Cookie`里面获取`kaptchaId`的值，那么正则为`Set-Cookie|kaptchaId=(.*?);`
<img width="1435" alt="image" src="https://user-images.githubusercontent.com/30351807/188487200-468ff302-977b-4ea5-96f8-2fdca126261d.png">

<img width="1413" alt="image" src="https://user-images.githubusercontent.com/30351807/188487344-91b40601-d704-484f-a148-e8241647d15e.png">


### 安装

* 需要python3 小于3.7的版本（3.6.6版本请测没问题）
* 如果是用win系统可以直接下载打包好的环境,内置python3.6.6版本以及下载好对应的模块 `NEW_xp_CAPTCHA win64 python环境完整版.rar`
* 链接: https://pan.baidu.com/s/1U0ZRjtxdqmNYF0b_O-6B1Q 提取码: tfi5

也可以自己安装对应的模块：

* 安装 文件比较大，可能需要一点时间。
```
python3 -m pip install requests
python3 -m pip install -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com muggle-ocr
python3 -m pip install ddddocr -i https://pypi.tuna.tsinghua.edu.cn/simple
```


![image](https://user-images.githubusercontent.com/30351807/115872316-3f4b6780-a474-11eb-8f25-a2de13274510.png)


运行 server.py 


![image](https://user-images.githubusercontent.com/30351807/115872339-470b0c00-a474-11eb-8339-109b82f464eb.png)


等待显示出 Starting server, listen at: 0.0.0.0:8899 访问 http://127.0.0.1:8899/ 显示下面界面即为正常。

![image](https://user-images.githubusercontent.com/30351807/115872365-4ffbdd80-a474-11eb-8be6-cd4150242d66.png)

linux 下安装可能会需要

![image](https://user-images.githubusercontent.com/30351807/115872401-58ecaf00-a474-11eb-9a1a-e933173585a7.png)

安装即可
```
yum install libglvnd-glx-1.0.1-0.8.git5baa1e5.el7.x86_64
```


### Star

[![Stargazers over time](https://starchart.cc/smxiazi/NEW_xp_CAPTCHA.svg)](https://starchart.cc/smxiazi/NEW_xp_CAPTCHA)

**********

### 更新4.1 2022-6-24

* 大改版，强烈安装新版本
