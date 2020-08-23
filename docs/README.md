# 产品简介

## PasteMe 是什么

PasteMe 是一个无需注册的文本分享平台，针对代码提供了额外的高亮功能。

## 产品背景

+ 如果你要发布一个脚本，可以把 `Bash` 或者 `Python` 等脚本上传至 `PasteMe` ，然后通过 `curl` 和管道机制来进行优雅的发布，比如：`curl api.pasteme.cn/8219 | python3`

+ 如果你要发给某人一些私密的信息，比如一段 `token`，但是通过 QQ 、微信等聊天工具可能会被 “查水表”，你可以将私密信息以阅后即焚形式上传至 `PasteMe` ，将一次性链接分享给别人，别人查看一次之后这个链接就会失效

+ 想要向服务器内粘贴一段代码，但是苦于字符集，复制、上传上去之后有其它的字符，此时你可以上传至 `pasteme` ，然后通过 `wget api.pasteme.cn/<key> -O file_name` 来进行优雅的拉取

+ 新装了一台没有图形化界面的服务器，没开 `sshd` 服务，没有可用的编辑器去编辑 `sources.list` 文件，直接用默认源安装一个编辑器又太慢，此时可以用 `curl api.pasteme.cn/<key> > /etc/apt/sources.list` 或 `wget api.pasteme.cn/<key> -O /etc/apt/sources.list` 来更新 `apt` 源，然后进行优雅的 `apt update`

+ 阅后即焚的链接是可以自定义的，比如 [pasteme.cn/example](https://pasteme.cn/example) ，更多详情请查看 [使用文档](documentation.md)

## 产品功能

+ 在存储内容时，**设置密码**和**阅后即焚**可以高度保证用户内容的安全性和私密性。

+ 在将自己的内容分享给别人时，提供了一键复制链接和二维码分享等多种途径。

+ 在查看别人的内容时，可以一键复制所有文本。如果查看的是阅后即焚的内容，那么在网页加载完成之前，实体数据就已经不存在了。
