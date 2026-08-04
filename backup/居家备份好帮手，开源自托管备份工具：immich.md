你用过多少备份软件，x度网盘？阿x云盘？黑x晖？xxx助手？可能太多，那有没有考虑过部署一个自己的备份服务呢？

今天我们推荐一款开源替代的备份工具：immich。它适合拥有自己服务器，希望构建自托管备份服务的同学，在GitHub已超过23K Star。

[https://immich.app/](https://immich.app/)

immich是什么？
Immich 是一个直接从 iPhone、Android 手机上备份照片与视频的开源解决方案，通过部署在自己的电脑、NAS、服务器中，使用 App 进行备份。界面酷似 Google Photos，支持多用户、照片和相册分享、好友上传、地理位置、机器学习识别事件等功能。



Immich的作者在介绍里也写了自己创建这个工具的初衷，一开始就是希望可以实现一个免费的、自主的、备份宝宝照片的工具。

项目在GitHub上也一直保持着稳定的star增长。


安装 immich
首先是在线demo环境，访问以下地址可以直接使用：

[https://app.affine.pro/](https://link.zhihu.com/?target=https%3A//app.affine.pro/)

demo账号和密码：

email: demo@immich.app
password: demo
项目给出了很多的安装方式，推荐使用 Docker来安装 Immich ，需要下载docker compose 和 env文件

wget <https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml>
wget -O .env <https://github.com/immich-app/immich/releases/latest/download/example.env>
实际上，只需要修改里面的 UPLOAD_LOCATION 部分，使用绝对路径，这是保存照片的路径。如果需要的话，可以修改一下[数据库](https://zhida.zhihu.com/search?content_id=237777161&content_type=Article&match_order=1&q=%E6%95%B0%E6%8D%AE%E5%BA%93&zhida_source=entity)密码。

其它设置保持默认，之后启动docker：