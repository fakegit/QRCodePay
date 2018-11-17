# QRCodePay
ONE qrcode for alipay、wxpay and qqpay, which can be pushed on github pages.

# Demo
https://vcheckzen.github.io/customized/pay/

# How to use
1. 下载整个项目并解压

2. 替换以下 3 张图片和 index.html 文件 35 行的支付宝付款码对应的链接

```
static/img/qrcode/wxpay.png //微信付款码
static/img/qrcode/qqpay.png //QQ 钱包付款码
static/img/qrcode/other.png //该页面部署后 URL 对应的二维码
Url: "HTTPS://QR.ALIPAY.COM/FKX09613RWE3ROTNTVR362", //支付宝付款码扫描后的链接
```

3. 部署到 Github Pages 或其他服务器


# References
https://github.com/mengkunsoft/OneQRCode
<br>
https://segmentfault.com/a/1190000013301132

