# 短视频去水印小程序

![qrcode](https://mini.rcer666.cn/wechat_qrcode.jpg)

### nginx反向代理下载视频地址绕过wechat下载限制

```
resolver 8.8.8.8; #必须
    location ~/download {
        if ($query_string ~*  ^(.*)url=(.*)$){
            set $url $2;
            proxy_pass $url;
        }
    }
```
