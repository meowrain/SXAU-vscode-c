[TOC]

# 安装工具链
> Debian系
```bash
sudo apt-get install build-essential
sudo apt-get install cmake
```
> Arch系
```bash
sudo pacman -Sy base-devel
sudo pacman -Sy cmake
```


# 单文件编译

克隆本仓库
`https://github.com/meowrain/SXAU-vscode-c.git`

打开cmake-learn目录，然后执行
```bash
bash run.sh
```
即可

每次新添加了.c文件，只需要重新执行run.sh即可