## 安装

```bash
npm install -g nodeppt
```

## shell使用

### 启动

```bash
# 获取帮助
nodeppt start -h
# 绑定端口
nodeppt start -p <port>
```

```bash
nodeppt start -p 8090 -d path/for/ppts
# 绑定host，默认绑定0.0.0.0
nodeppt start -p 8080 -d path/for/ppts -H 127.0.0.1
# 使用socket通信（按Q键显示/关闭二维码，手机扫描，即可控制）
# socket须知：1、注意手机和pc要可以相互访问，2、防火墙，3、ip
```

#### 启用socket控制

##### 方法一：使用url参数

```bash
http://127.0.0.1:8080/md/demo.md?controller=socket
```

在页面按键【Q】显示控制url的二维码和控制链接（需要隐身窗口打开），手机上可以使用左右touch滑动和摇一摇切换下一页

##### 方法二：使用`start`命令行

```bash
nodeppt start -c socket
```
在页面按键【Q】显示控制url的二维码和控制链接（需要隐身窗口打开），手机上可以使用左右touch滑动和摇一摇切换下一页

#### 启用postMessage控制
默认使用postMessage多窗口控制，打开方法：

```bash
http://127.0.0.1:8080/md/demo.md?_multiscreen=1
```


### 打印/导出ppt
这么高端大气上档次的ppt，怎么能不导出分享给大家呢？？

使用``url?print=1``访问页面，然后选择chrome的系统打印即可


#### html版

```bash
# 获取generate帮助
nodeppt generate -h
# 使用generate命令
nodeppt generate filepath
# 导出全部，包括nodeppt的js、img和css文件夹
# 默认导出在publish文件夹
nodeppt generate ./ppts/demo.md -a
# 指定导出文件夹
nodeppt generate ./ppts/demo.md output/path -a
```
导出目录下所有ppt，并且生成ppt list首页：

```bash
nodeppt path output/path -a
```







