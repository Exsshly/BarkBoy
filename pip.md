# pip

源备查，以下：

官方：

`https://pypi.python.org/simple`

清华：

`https://pypi.tuna.tsinghua.edu.cn/simple/`

北外：

`https://mirrors.bfsu.edu.cn/pypi/web/simple/`

阿里：

`http://mirrors.aliyun.com/pypi/simple/`

豆瓣：

`http://pypi.douban.com/simple/`

网易：
`https://mirrors.163.com/pypi/simple/ `

中科大：

`http://pypi.mirrors.ustc.edu.cn/simple/`

百度：

`https://mirror.baidu.com/pypi/simple/`

华为：

`https://mirrors.huaweicloud.com/repository/pypi/simple/`

腾讯：

`https://mirrors.cloud.tencent.com/pypi/simple/`


查看当前所有源：

```
pip config list
```

## Windows

### 方案〇

临时解决方案

pip时，尾部加入参数 `-i` ，如

```
pip install numpy -i https://pypi.tuna.tsinghua.edu.cn/simple
```

即在本次安装使用清华源。

END.

### 方案一

在`C:\Users\usr`下新建文件夹`pip`，在新建的文件夹下新建文件**pip.ini**。

在ini文件里添加以下内容（清华源）

```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```

END.

### 方案二

在终端执行

```
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

PS：适用于Linux

END.

## Linux

### 方案一

使用vim/vi编辑，路径： `~/.pip/pip.conf`

添加以下内容

```
[global]
index-url =  http://mirrors.aliyun.com/pypi/simple/ 
```

PS：该方法永久换源，临时换源参Windows中方案〇。

END.

### 方案二

同Windows方案二。

END.

## 添加多个源

需要修改**pip.conf**文件

```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple/
extra-index-url =
            https://mirrors.aliyun.com/pypi/simple/
            https://mirror.baidu.com/pypi/simple/
            https://pypi.mirrors.ustc.edu.cn/simple/
            https://mirrors.cloud.tencent.com/pypi/simple

[install]
trusted-host =
    pypi.tuna.tsinghua.edu.cn
    mirrors.aliyun.com
    mirror.baidu.com
    pypi.mirrors.ustc.edu.cn
    mirrors.cloud.tencent.com
```

```
[global]
index-url=https://pypi.tuna.tsinghua.edu.cn/simple/
extra-index-url=http://mirrors.aliyun.com/pypi/simple/
extra-index-url=http://pypi.douban.com/simple
extra-index-url=http://pypi.mirrors.ustc.edu.cn/simple/

[install]
trusted-host=pypi.tuna.tsinghua.edu.cn
trusted-host=mirrors.aliyun.com
trusted-host=pypi.douban.com
trusted-host=pypi.mirrors.ustc.edu.cn
```

END.

## 其他

使用pip安装时，若之前已经下载过，pip会默认使用缓存安装，而不是重新从网络上下载。
