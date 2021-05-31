宝塔面板部署 Vue-mmPlayer
部署后台 API 服务
下载和上传
git clone https://github.com/Binaryify/NeteaseCloudMusicApi.git
将下载好的 NeteaseCloudMusicApi 文件直接上传至宝塔面板的 /www/wwwroot 目录下

1

启动服务
安装 PM2 管理器（软件管理 - 运行环境）

启动服务

点击PM2 管理器

选择刚刚上传的 NeteaseCloudMusicApi 项目的目录

输入 app.js 和 项目名称 NeteaseCloudMusicApi

点击添加

放行端口：安全，添加 api 服务的端口默认 3000

绑定域名并设置HTTPS

启动服务后点击映射，输入当前服务需要绑定的域名（不需要可直接跳过后续步骤）

点击侧边栏网站，找到刚刚输入的域名依次点击设置 - SSL

如果宝塔有进行实名认证可以选择宝塔SSL，未实名可以去阿里云申请SSL证书（本教程使用阿里云SSL证书为例，申请地址 选择免费版（个人）DV）

申请好阿里云SSL证书后，下载证书（选择其他）

将下载后的文件解压，去宝塔分别填写密钥(KEY)和证书(PEM格式) 再点击保存即可

2

3

4

使用宝塔SSL

5

部署 Vue-mmPlayer 服务
下载和编译
git clone https://github.com/maomao1996/Vue-mmPlayer.git

# 进入项目目录
cd Vue-mmPlayer

# 安装依赖
npm install

# 将 .env 文件的 VUE_APP_BASE_API_URL 地址修改为上一步 API 服务的地址

# 编译打包
npm run build
将编译打包好的 NeteaseCloudMusicApi 文件直接上传至宝塔面板的 /www/wwwroot 目录下

上传到宝塔面板
6

点击侧边栏网站 - 添加站点，然后输入为 Vue-mmPlayer 准备好的域名

点击刚创建网站的根目录，将刚刚编译打包生成的 dist 文件夹中的所有文件上传当前目录

最后可以根据需要是否进行 HTTPS 设置
