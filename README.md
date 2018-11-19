# WHAT
ONE qrcode for alipay、wxpay and qqpay, which can be pushed on github pages.

# DEMO
- <https://vcheckzen.github.io/customized/pay/>
- <https://vcheckzen.github.io/customized/pay/requirements/>

# WHY
声明：该项目思路并非原创，只是发现诸多类似项目中要么是 PHP 版本，需要服务器支持，要么因个人喜好原因，对界面不太满意，在此声明并非觉得他们好或不好。另一个问题是他们都依赖接口和外链。所以我参考两个项目，取其中一个的样式，另一个的跳转，并去除所有接口和外链，改为部署前手动生成，将页面静态化，无依赖，在此十分感谢两位作者

注意：经测，部署在 coding pages，跳转时会被官方拦截，提示滥用；若域名未备案或网址带有端口号会被微信拦截，需手动确定；github pages 无以上问题，但国内速度较慢，虽然多数情况下可在 2s 内加载，但仍建议部署在国内已备案的服务器上

兼容性：因为使用了 webp 格式素材，PC 端仅 Chrome 完美兼容，但考虑到国产浏览器大多为 Chromium 内核，并且国内移动端大都跟进了 webp，所以并不打算更换素材，实测微信、QQ、支付宝都是完美兼容的。若想获得更好的兼容性，请自行更换 png、jpg 等格式素材

WEBP 兼容性检测代码：

```
// F12 控制台粘贴回车
window.isSupportWebp = false;
void function(){
    var webpTestsUri = 'data:image/webp;base64,UklGRiQAAABXRUJQVlA4IBgAAAAwAQCdASoBAAEAAwA0JaQAA3AA/vuUAAA=';
    var image = new Image();
    function addResult(event) {
        window.isSupportWebp = event && event.type === 'load' ? image.width == 1 : false;
    }
    image.onerror = addResult;
    image.onload = addResult;
    image.src = webpTestsUri;
}();
setTimeout(function (){console.log(window.isSupportWebp);}, 1000);
```

# HOW
1. 下载整个项目并解压
- https://github.com/vcheckzen/QRCodePay/releases/download/1.0/pay.zip

2. 从手机分别导出支付宝、微信和 QQ 收款码，并确定部署 URL，例如
- https://vcheckzen.github.io/customized/pay/

3. 通过以下网页上传付款码和页面小标签 favicon 并填写部署 URL，以生成 4 张 WEBP 图片
- https://vcheckzen.github.io/customized/pay/requirements/

4. 用生成的 4 张图片覆盖以下目录中的同名文件

```
static/img/icon/favicon.webp //页面 TAB 上的小图标
static/img/qrcode/wxpay.webp //微信收款码
static/img/qrcode/qqpay.webp //QQ 钱包收款码
static/img/qrcode/other.webp //该页面部署后 URL 对应的二维码
```

5. 复制生成的支付宝付款码链接，粘贴到 index.html 文件 35 行对应位置

```
"ali": "HTTPS://QR.ALIPAY.COM/FKX09613RWE3ROTNTVR362" //支付宝收款码链接
```

6. 部署到 Github Pages 或其他服务器

# REFERENCES
- https://github.com/mengkunsoft/OneQRCode
- https://segmentfault.com/a/1190000013301132

