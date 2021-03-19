# eb1-script
<br/>说明：此法来源于：
</p><pre><code>https://neko.re/archives/208.html</code></pre>
<br/>1.打开 shadowrocket  APP -> 配置 -> default.conf -> 编辑纯文本
<br><img src="https://raw.githubusercontent.com/nikleechan/eb1-script/master/sd.png"><br>
<br/>2. 在最下面添加如下文本并保存
<br/>脚本1：<br/>
</p><pre><code>[Script]
unlock_emby = type=http-response,script-path=https://raw.githubusercontent.com/nikleechan/eb1-script/master/unlock_emby.js,pattern=^http(s?):\/\/(www\.|)mb3admin\.com\/.*$,max-size=131072,requires-body=true,timeout=10,debug=false,enable=true
[MITM]
hostname = mb3admin.com,www.mb3admin.com</code></pre>

<br/>脚本2：<br/>
</p><pre><code>[Script]
EmbyPremiere = type=http-response,script-path=https://raw.githubusercontent.com/nikleechan/eb1-script/master/EmbyPremiere.js,pattern=^https?:\/\/mb3admin.com\/admin\/service\/registration\/validateDevice,max-size=131072,requires-body=true,timeout=10,enable=true

[MITM]
hostname = mb3admin.com</code></pre>
<br/>脚本2若打不开，则换备用地址：<br/>
</p><pre><code>[Script]
EmbyPremiere = type=http-response,script-path=https://gitlab.com/iptv-org/embypublic/-/raw/master/Script/EmbyPremiere.js,pattern=^https?:\/\/mb3admin.com\/admin\/service\/registration\/validateDevice,max-size=131072,requires-body=true,timeout=10,enable=true

[MITM]
hostname = mb3admin.com</code></pre>
<br/>输完点保存后，再次点击 default.conf -> 编辑配置 -> 开启 HTTPS 解密 -> 生成新的 CA 证书 -> 安装 CA 证书 -> 同意安装描述文件
<br><img src="https://raw.githubusercontent.com/nikleechan/eb1-script/master/https.png"><br>
<br/>4. 然后去手机设置 -> 点右边的描述文件已下载 -> 查看描述文件 ->安装
<br><img src="https://raw.githubusercontent.com/nikleechan/eb1-script/master/cert.png"><br>
<br/>5. 然后返回 ShadowRocket，首页的全局路由选择为配置（根据配置文件转发流量），再开启即可。
<br/>6. 尝试访问 Emby，这时会有证书接受提示，点击接受即可。
<br><img src="https://raw.githubusercontent.com/nikleechan/eb1-script/master/emby.png"><br>
<br/>7. 然后设置页面会有小金标提示.
<br/>   在Emby Premiere 随意输入密钥点确定，也会有“你有一个 Lifetime Emby Premiere 订阅，你的设备使用在最大数量限制之内”的提示。
<br><img src="https://raw.githubusercontent.com/nikleechan/eb1-script/master/embypremiere.png"><br>