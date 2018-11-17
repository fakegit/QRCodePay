# QRCodePay
ONE qrcode for alipay、wxpay and qqpay, which can be pushed on github pages.

# Demo
https://vcheckzen.github.io/customized/pay/

# Why this
声明：该项目思路并非原创，只是发现诸多类似项目中要么是 PHP 版本，需要服务器支持，要么应个人喜好原因，对界面不太满意，在此声明并非觉得他们好或不好。另一个问题是他们都依赖接口和外链。所以我参考两个项目，取其中一个的样式，另一个的跳转，并去除所有接口和外链，改为部署前手动生成，将页面静态化，无依赖，在此十分感谢两位作者

注意：经测，coding.net 部署跳转时会被官方拦截，提示为滥用问题；若域名未备案会被微信拦截，需手动点击一步才可继续，有端口号同样会被微信拦截；github pages 无以上问题，但国内速度较慢

# How to use
1. 下载整个项目并解压

2. 替换以下 4 张图片和 index.html 文件 35 行的支付宝付款码对应的链接

```
static/img/icon/favicon.ico //页面 TAB 上的小图标
static/img/qrcode/wxpay.png //微信付款码
static/img/qrcode/qqpay.png //QQ 钱包付款码
static/img/qrcode/other.png //该页面部署后 URL 对应的二维码
Url: "HTTPS://QR.ALIPAY.COM/FKX09613RWE3ROTNTVR362", //支付宝付款码扫描后的链接
```

3. 部署到 Github Pages 或其他服务器

# Tools
可以使用以下工具得到项目所需的二维码和支付宝付款码链接

1. 使用二维码扫描器将支付宝、微信和 QQ 付款码全部转成对应 URL

```
https://cli.im/deqr
```

2. 使用以下工具将微信和 QQ 付款码对应的 URL 编码

```
http://tool.oschina.net/encode?type=4
```

3. 使用以下接口将编码后的 URL 生成指定样式的新二维码

```
http://qr.liantu.com/api.php?text=编码后的 URL
```
4. 同样使用上述接口对部署后的 URL 生成二维码

# References
https://github.com/mengkunsoft/OneQRCode
<br>
https://segmentfault.com/a/1190000013301132

