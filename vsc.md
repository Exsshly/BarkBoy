# VSCode + gcc

[下载](https://code.visualstudio.com/)VScode

[下载](https://nuwen.net/mingw.html)gcc/g++

解压gcc/g++到指定目录，将`YOUR_PATH/MinGW/bin`添加到环境变量

在终端中执行`gcc --version`或`g++ --version`显示版本号即成功

打开VScode，下载安装`C/C++ Extension Pack`和拓展

在任意位置新建文件夹，以后的代码文件都在这里编辑编译

在VScode中打开该文件夹，随便新建cpp文件

粘贴下面代码运行

```
#include <iostream>
int main()
{	std::cout<<"hello"<<std::endl;	}
```

在弹出的窗口选择编译器中选择`C++(GDB/LLDB)`

然后选择编译器，选择`g++`开头

会在该文件夹同目录下生成**.vscode**文件夹，里面会有两个配置文件

以下文件参考

`launch.json`
```
{
    // 使用 IntelliSense 了解相关属性。 
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "g++.exe - 生成和调试活动文件",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "miDebuggerPath": "YOUR_PATH\\MinGW\\bin\\gdb.exe",
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "C/C++: g++.exe 生成活动文件"
        }
    ]
}
```

`tasks.json`
```
{
    "tasks": [
        {
            "type": "cppbuild",
            "label": "C/C++: g++.exe 生成活动文件",
            "command": "YOUR_PATH\\MinGW\\bin\\g++.exe",
            "args": [
                "-g",
                "${file}",
                "-o",
                "${fileDirname}\\${fileBasenameNoExtension}.exe"
            ],
            "options": {
                "cwd": "${fileDirname}"
            },
            "problemMatcher": [
                "$gcc"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            },
            "detail": "调试器生成的任务。"
        }
    ],
    "version": "2.0.0"
}
```