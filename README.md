XX-Net-mini 4.5.2 Mini version of [XX-Net](https://github.com/XX-net/XX-Net).

XX-Net-mini 4.5.2 在Linux和Windows环境下正常运行(其他环境未作测试) 

Windows环境下运行截图:

![](https://user-images.githubusercontent.com/6849681/104595478-a3100880-56ad-11eb-838c-a15fd79abf00.png)

Linux环境下运行截图:

![](https://user-images.githubusercontent.com/6849681/92320577-08dfea00-f055-11ea-9314-b43a1ad0a0ae.png)

Mini版XX-Net特点:

1. 使用最新版的XX-Net和相关模块hpack, hyper, hyper-h2, hyperframe, dnslib, PySocks
2. 去掉X-tunnel, pac_server, web_control
3. 去掉自动更新和下载
4. 去掉扫描和删除ip的功能, 直接持久使用707个固定ip, 解决ip骤降的问题
5. 统一配置文件: XX-Net/data/config.json
6. 去掉pyOpenSSL, 使用Python调用系统命令生成、导入和管理证书


使用说明:

   Windows: 
   
        [XX-Net-mini-win10_x64.zip](https://github.com/miketwes/miketwes.github.io/blob/main/file/XX-Net-mini-win10_x64.zip) 集成了最新版本的Python 和 openssl

        Win10_x64用户解压后运行start.bat 

   Linux:  
   
        下载或克隆XX-Net-mini

        [XX-Net-mini 4.5.2 zip](https://github.com/miketwes/XX-Net-mini/archive/4.5.2.zip)      
        git clone https://github.com/miketwes/XX-Net-mini.git
		
        cd XX-Net-mini/code/default/launcher && python start.py

        Linux用户使用前请确保系统已经安装了最新版本的Python 和 openssl
        在命令行运行 python --version 和 openssl version查看是否已经安装, 
        如果没有安装 sudo aptitude install python3 openssl  

运行时如果提示 Press Enter to continue..., 说明有错误出现, 可修改 XX-Net-mini/code/default/lib/noarch/xlog.py中的self.min_level = FATAL为self.min_level = NOTSET, 以显示详细错误信息, 欢迎提交错误报告, 提交报告时, 请尽可能附上详细错误信息
如果不出现 Network is ok, you can start to surf the internet! 的提示,  说明有Ipv6网络有问题

Chromium, chrome浏览器代理设置:

        chromium --proxy-server="http://127.0.0.1:8087" --ignore-certificate-errors
    
Firefox浏览器代理设置: 
    
        about:config
        network.proxy.type 1     
        network.proxy.http 127.0.0.1
        network.proxy.http_port 8087
   
使用自己的appid:
    
   编辑XX-Net-mini/data/config.json
    
        "gaeappids": [
            "yourappid1",
            "yourappid2"
        ],
