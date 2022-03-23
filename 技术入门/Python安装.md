# Python安装

1. 安装python3

   1. MacOS环境默认Python2.7版本，需安装Python3后，用pip3安装virtualenv。

   2. 如需将Python3设置为默认版本

      `ln -s -f /usr/local/bin/python3.10 /usr/local/bin/python`

2. 安装virtualenv

`pip install virtualenv`

4. 创建python虚拟环境

`virtualenv 项目文件夹名称`

5. 进入python虚拟环境

`source 项目文件夹名称/bin/activate`

6. Pip install 需要的packages

`pip install pandas`