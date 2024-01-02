# MPC-wiki
 数理化wiki mathematical physical chemical wiki

采用[mkdocs+mkdocs-material主题](https://github.com/OI-wiki/mkdocs-material)部署

## 如何修改/新建内容并提交更新到本仓库

1、打开[https://github.com/funoi-dev/MPC-wiki](https://github.com/funoi-dev/MPC-wiki)  如果打不开可以看[https://kkgithub.com/funoi-dev/MPC-wiki](https://kkgithub.com/funoi-dev/MPC-wiki)

2、下载并安装[git](https://download.njuu.cf/git-for-windows/git/releases/download/v2.43.0.windows.1/Git-2.43.0-32-bit.exe)和[python(已经安装的可以跳过)](https://www.python.org/ftp/python/3.10.11/python-3.10.11.exe)。其中git的安装教程可以参考[https://zhuanlan.zhihu.com/p/443527549](https://zhuanlan.zhihu.com/p/443527549)，一般改个路径后一路`next`就好了。Python的话打开第一步点`Customize installation`，再点`next`，接着勾选`Add Python to environment varibles`，点击底下的`Browse`按钮选择安装路径，最后点`Install`就好了。

3、测试你的`git`和`python`：按下`win`+`r`，输入`cmd`回车，在弹出的黑框框中分别输入：

```bash
git -v
pip -V
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
#第3行为设置镜像源，加速用的
```

如果弹出内容是类似以下内容的，那么说明你安装成功了。

```bash
git version xxxxx.xxxxx.xxxxx.xxxxx.xxx
pip xx.xx.xx from xxxxxxx (python xxxxx)
```

如果后面那一行（`pip -V`）出现了类似找不到pip或者不是内部或外部命令，也不是可运行的程序的报错，请运行以下代码（也是在刚才的黑框框里面）：

```python
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
```

然后重试检查安装。

4. 执行以下部署操作

5. 按照后文进行修改

6. 按照后文提交

## 部署

```cmd
# windows
# win+r输入cmd回车
cd /d 你想要把项目部署到的位置（例如D:\c++\dev\）
git clone https://hub.njuu.cf/funoi-dev/MPC-wiki
cd MPC-wiki
ins.bat
run.bat
# 程序成功在127.0.0.1:5566运行，可以进入查看
```


## 贡献

### 贡献部分

数学、物理、化学全部。

### 如何贡献&&代码讲解

所有wiki都存放在docs文件夹下，以`.md`(markdown)格式撰写，同时

当需要新建时：

1、在`docs/对应学科/对应部分/对应分类/对应模块`（路径不存在需要自行创建）中创建一个名为`xxx.md`的`markdown`文档，其中`xxx`为标题

2、撰写`markdown`

3、在`mkdocs.yml`中`nav`项下编写好路径，具体如下：

例如我需要在`数学`-`小学奥数`-`几何`-`等高模型`创建一个名为`等高模型例题.md`的文档，需要在`mkdocs.yml`写入对应位置和名称和路径。（如下）

```yml
nav:
  - 主页: index.md
  - 数学:
    - 小学奥数:
      - 主页: 数学/小学奥数/main.md
      - 几何: #分类需要加英文冒号，文档这不需要
        - 等高模型: #子项需要加两个空格
          - 等高模型例题: xxx/xxx/xxx/xxx.md #路径填写文件相对docs文件夹的路径（这里没有冒号）
    - 初中课内:
      - 主页: 数学/初中课内/main.md
    - 初中竞赛:
      - 主页: 数学/初中竞赛/main.md
```

（实在不懂问WTX）

需要修改时：

直接修改后pr即可。
