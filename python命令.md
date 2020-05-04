# python 命令
## pip更新源
### 临时使用
```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```
*注意，simple 不能少, 是 https 而不是 http*

### 设为默认
* 升级 pip 到最新的版本 (>=10.0.0) 后进行配置：
```
pip install pip -U
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```
* 如果您到 pip 默认源的网络连接较差，临时使用本镜像站来升级 pip：
```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U
```

## pyinstaller 打包成exe
### 安装pyinstaller
如果你的网络稳定，通常直接使用下面的命令安装即可：

pip install pyinstaller


### 检查pyinstaller安装成功与否：

> 只需要执行如下命令其中一个即可：
pyinstaller --version
pyinstaller -v


### pyinstaller参数作用
* -F 表示生成单个可执行文件
* -D –onedir 创建一个目录，包含exe文件，但会依赖很多文件（默认选项）
* -w 表示去掉控制台窗口，这在GUI界面时非常有用。不过如果是命令行程序的话那就把这个选项删除吧
* -c –console, –nowindowed 使用控制台，无界面(默认)
* -p 表示你自己自定义需要加载的类路径，一般情况下用不到
* -i 表示可执行文件的图标
其他参数，可以通过pyinstaller --help查看
### 开始打包
进入python需要打包的脚本所在目录，然后执行下面的命令即可：

python -F -i favicon.ico nhdz.py

### pyinstaller 如何引入Pycharm项目中的第三方库
> 使用Pycharm作为IDE的项目，引用的第三方库一般放在项目所在目录的venv\Lib\site-packages下，因此可使用以下语句引入第三方库
```
pyinstaller -p venv\Lib\site-packages -F xxx.py
```
### 打包结果
打包完成后，进入到当前目录下，会发现多了__pycache__、build、dist、nhdz.spec这四个文件夹或者文件，其中打包好的exe应用在dist目录下面，进入即可看到，可以把他拷贝到其他地方直接使用，如下图所示，是打包完成后的目录：



### ICO图标制作
前面需要用到ICO图标，大家可以网上搜索“ICO 在线生成”，可以直接点击ICO图标制作在上面制作、然后保存也行

最后
大家有什么疑问或者想法，都可以直接和我交流，谢谢！