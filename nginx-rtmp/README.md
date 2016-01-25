## 官方
* 项目地址: <https://github.com/arut/nginx-rtmp-module>
* 文档: <https://github.com/arut/nginx-rtmp-module/wiki/Getting-started-with-nginx-rtmp>

## 编译
* 下载 `nginx-rtmp-module` : <https://github.com/arut/nginx-rtmp-module/archive/v1.1.7.tar.gz>
* 下载 `nginx` : <http://nginx.org/download/nginx-1.9.9.tar.gz>
* `tar xvf v1.1.7.tar.gz` -> `nginx-rtmp-module-1.1.7`
* `tar xvf nginx-1.9.9.tar.gz` -> `nginx-1.9.9`
* `cd nginx-1.9.9`
* `./configure --add-module=/root/aktest/nginx-rtmp-module-1.1.7 --with-http_ssl_module --without-http_rewrite_module`
* `make`
* `make install`

## 配置
* 配置文件目录: `/usr/local/nginx/conf`
* 修改配置文件: `/usr/local/nginx/conf/nginx.conf`
* `mkdir /usr/local/nginx/html/myapp`

## 测试
* 推流: `ffmpeg -re -i time.flv -c copy -f flv rtmp://10.0.5.134/myapp/mystream`
* 播放rtmp: `rtmp://10.0.5.134/myapp/mystream`
* 播放hls: `http://10.0.5.134/myapp/mystream.m3u8`
