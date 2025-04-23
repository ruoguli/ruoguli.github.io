---
title: 运行Jekyll本地服务器
date:   2025-01-10 12:00:00 +0800
categories: [Jekyll]
tags: [jekyll]
description: 仅供参考
---


1. [下载](https://rubyinstaller.org/downloads/)并安装Ruby+Devkit的x64版本，安装完成后重启终端检查：
```
ruby -v
```

2. 注意检查c:/users/your_name/appdata/local/microsoft/windowsapps是否在系统变量中

3. 终端输入：
```
gem install bundler jekyll
```

4. 检查：
```
jekyll -v
```

```
bundle -v
```

5. 进入你项目所在路径，安装依赖：
```
bundle install
```

提示：身处中国大陆**可能**需要更换镜像源：
```
bundle config mirror.https://rubygems.org https://gems.ruby-china.com
```

6. 使用命令启动本地服务器
```
bundle exec jekyll serve
```

7. 在浏览器中打开：
```
http://127.0.0.1:4000/
```
