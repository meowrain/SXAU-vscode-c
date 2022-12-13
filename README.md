[TOC]

>  搞不明白的可以加这个QQ群：==**887940241**==

# 1.安装VSCODE

[Visual Studio Code - Code Editing. Redefined](https://code.visualstudio.com/)

上面是vscode的官网，下载就可以了

![](.\image\01.png)

# 2.配置C/C++语言环境

参考下面的文章进行环境配置

https://blog.csdn.net/XQC_KKK/article/details/124611111

> 搞不明白的可以加这个QQ群：==**887940241**==

# 3. 安装插件

## 安装中文语言

![](.\image\02.png)

搜索`Chinese`，安装中文语言

![](.\image\03.png)



## 安装C/C++插件

![](.\image\04.png)



# 4.配置launch.json和task.json

在你的项目文件夹中新建 `.vscode` 文件夹，在这个文件夹下创建 `launch.json`和`tasks.json`文件

![](.\image\05.png)



下面是`launch.json`和`tasks.json`的配置内容

也可以从github直接下载咱们已经配置好的文件

---

> 注意： 填写你的gdb.exe等程序位置的时候，要用\\来分割目录

launch.json

```json
{
    "configurations": [
        {
            "name": "C语言编译调试",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "miDebuggerPath": "D:\\environment\\mingw\\mingw64\\bin\\gdb.exe", //这里填你配置好的mingw环境中gdb.exe的位置，我放在了d盘
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
                {
                    "description": "将反汇编风格设置为 Intel",
                    "text": "-gdb-set disassembly-flavor intel",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "clang"
        },
        {
            "name": "C++编译调试",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "miDebuggerPath": "D:\\environment\\mingw\\mingw64\\bin\\gdb.exe",
 //这里填你配置好的mingw环境中gdb.exe的位置，我放在了d盘
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
                {
                    "description": "将反汇编风格设置为 Intel",
                    "text": "-gdb-set disassembly-flavor intel",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "cpplang"
        }
    ],
    "version": "2.0.0"
}
```

tasks.json

```json
{
    "tasks": [
        {
            "type": "cppbuild",
            "label": "clang",
            "command": "D:\\environment\\mingw\\mingw64\\bin\\gcc.exe",//这里是你配置的环境里面的gcc.exe的位置
            "args": [
                "-fdiagnostics-color=always",
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
            "group": "build",
            "detail": "调试器生成的任务。"
        },
        {
            "type": "cppbuild",
            "label": "cpplang",
            "command": "D:\\environment\\mingw\\mingw64\\bin\\g++.exe",//这里是你配置的环境里面的gcc.exe的位置
            "args": [
                "-fdiagnostics-color=always",
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
            "group": "build",
            "detail": "调试器生成的任务。"
        }
    ],
    "version": "2.0.0"
}
```

![06](.\image\06.png)



---

# 5.使用

![07](.\image\07.png)

![08](.\image\08.png)

![09](.\image\09.png)

![10](.\image\10.png)