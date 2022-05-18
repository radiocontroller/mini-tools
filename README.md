# 工具小程序

### 1. 提供短视频去水印功能
* 提供tip1.png和tip2.png图片
* nginx反向代理下载视频地址绕过微信下载限制

```
resolver 8.8.8.8; #必须
    location ~/download {
        if ($query_string ~*  ^(.*)url=(.*)$){
            set $url $2;
            proxy_pass $url;
        }
    }

  location ~ .*\.(jpg|png)$  {
  	root /etc/nginx/images;
  	#expires	7d;
  }
```
