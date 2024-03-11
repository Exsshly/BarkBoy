# YoloV5

### 前置

安装python

下载yolov5代码，解压到工作目录

cd到源码目录下，创建虚拟环境

### 创建虚拟环境

上一步已经cd至代码目录下（虚拟环境位置可任意，能够正确激活即可），执行

`python -m venv yolovenv`

以创建虚拟环境，其中最后yolovenv为虚拟环境名称，可自定义

最后执行

`./Scripts/activate`

激活虚拟环境，成功后每行最前面应出现括号及括号内自定义的虚拟环境名

### 安装pytorch

进入网站https://pytorch.org/

按照实际情况选择，最后在终端执行网站给出的指令以安装pytorch

（若在终端内下载中断可手动下载whl包pip安装）

最后回退至代码根目录，执行

`pip install -r .\requirements.txt`

安装其他依赖

### 测试

终端执行

`python detect.py --weights yolov5s.pt`

执行完后在runs文件夹内会有结果

### 训练

`YOUR_PATH`要换为自己的相应目录，下同

```shell
python train.py
	--weights yolov5s.pt
	此字段使用预设模型，或可使用指定路径的.pt文件开始训练
	
	--cfg ~path~\yolov5s.yaml
	若使用预设模型，则需在代码文件夹models中复制一份对应的.yaml文件，并修改文件中nc值
	
	--data ~path~\data.yaml
	指向数据集的.yaml文件，该文件内需要修改数据集路径和分类
	
	--batch-size 8
	单次训练数据批次大小，越大越快，但是会导致资源不够用，一般选择2~8，值为-1时由系统确定
	
	--epoch 50
	训练轮数，越多训练效果拟合越好，太多会过拟合
	
	--device cpu
	可选，选择cpu或gpu训练，参数0使用gpu，优先使用gpu
```

上述即：`python train.py --weights yolov5s.pt --cfg YOUR_PATH\yolov5s.yaml --data YOUR_PATH\data.yaml --batch-size 8 --epoch 50`

### 检测
```shell
python detect.py
	--source YOUR_PATH
	指定检测的数据目录，可以说目录、单张图片或视频
	
	--weights YOUR_PATH\runs\train\exp(n)\weights\best.pt
	指定使用的模型，路径如上，~path~为代码根目录，n取决于训练完成后给出的文件夹；
	其中best是最好的模型；或者指定路径以使用从第三方获得的更好的模型
```

上述即：`python detect.py --weights YOUR_PATH\runs\train\exp(n)\weights\best.pt --source YOUR_PATH`

### 断点训练

用以解决由于突发情况训练过程突然中断，而重新训练费时的问题

1. 在train.py文件中找到函数`parse_opt`，修改-–resume的default参数为Ture
2. 确认上一次运行的exp(n)文件夹中有`last.pt`这个最后的权重文件，重新使用指令加载即可
3. 以下指令中的权重文件不再是**yolov5s.pt**，而应换成**last.pt**，其余保持不变。
`python train.py --weights YOUR_PATH/last.pt --cfg YOUR_PATH/yolov5s.yaml --data YOUR_PATH/data.yaml --batch-size 8 --epoch 50`

### 导出onnx

为了可跨平台使用权重，这里导出为onnx格式的模型文件，也是在yolo自带的代码文件中，如果之前没有onnx包，可能要pip一下

`pip install onnx`

然后执行

`python export.py --include torchscript onnx --weights YOUR_PATH/best.pt`

这里的pt文件由你指定的pytorch权重，转换的onnx在同目录下