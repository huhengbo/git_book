## Gitbook搭建写作环境
---
### 0x01 简介
Gitbook.com是一个写作和出版的平台，他们使用的系统是开源的。支持Markdown和AsciiDoc格式，最后输出的是静态网页。还可以通过calibre把书转成pdf、epub、mobi等常用格式，方便在各种设备上阅读。

### 0x02 前置条件
- 安装npm框架
- git依赖

### 0x03 安装
- 安装 `npm install gitbook-cli -g `
- 选择目录初始化一本书 `gitbook init`
- 启动本地web服务器默认地址 默认端口4000 `gitbook serve`
- 编译成静态页面`gitbook build`

### 0x04 生成其他格式
gitbook生成其他格式的书是借助calibre的转换功能实现的(ebook-convert)

- 安装calibre ` vi ~/.bash_profile`
- 打开配置文件（创建配置文件） vi ~/.bash_profile
- 追加信息 `export PATH=$PATH:/Applications/calibre.app/Contents/MacOS/ `
- 使得命令生效`source ~/.bash_profile`
- 生成对应格式文件
	1. gitbook pdf ./ mybook.pdf
	2. gitbook epub ./ mybook.epub
	3. gitbook mobi ./ mybook.mobi

### 0x05 其他问题
	1. 待定