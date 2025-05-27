# clash-for-linux
## 背景
在本机已有 clash ，但需要在 linux 服务器上需要使用代理访问GitHub、 openai、huggingface 等
## 简易教程
### 准备工作
1. 由于某些原因，clash 原作者跑路了，这里使用我的GitHub 仓库作为替代下载。
2. 将文件放到服务器后，运行`tar -zxvf clash-for-linux.tar.gz`解压文件，运行`cd clash-for-linux`进入文件夹
3. 从本机 clash 的配置文件夹中找到 config.yaml 文件，直接复制到 clash-for-linux 文件夹中
### 配置
1. 在终端执行 `chmod +x clash` 赋予 Clash 执行权限
2. 运行`vim ~/.bashrc` 在最后面插入如下配置代码
(不会用 vim 的看：运行上述代码后，切换到英文输入法，按i进入输出模式，按方向键到最后粘贴下面的配置代码，随后按 Esc 退出输入模式再输入:wq保存并退出)
```bash
export http_proxy=http://127.0.0.1:7890
export https_proxy=http://127.0.0.1:7890
export all_proxy=socks5://127.0.0.1:7890
```
3. 运行`source ~/.bashrc`更新一下修改配置
4. 运行`env | grep proxy`查看是否成功
5. 在终端执行 `./clash -d .` 即可启动 Clash
6. 新开一个终端运行`curl https://www.google.com`，有一大串输出则成功！
## 参考教程
该教程有更详细的其余操作 [Linux 服务器安装 Clash代理](https://blog.myxuechao.com/post/36)
## 机场
[低价机场推荐](https://github.com/DiningFactory/panda-vpn-pro)
