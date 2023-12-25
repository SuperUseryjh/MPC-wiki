# MPC-wiki
 数理化wiki mathematical physical chemical wiki

采用[mkdocs+mkdocs-material主题](https://github.com/OI-wiki/mkdocs-material)部署


## 部署

```cmd
# windows
# 自行安装python3，大多数机器自带了
# 在一个你喜欢的地方打开cmd（win+r输入cmd回车，弹出的窗口里面输入cd /d 你的路径（必须存在））
curl https://download.njuu.cf/git-for-windows/git/releases/download/v2.43.0.windows.1/Git-2.43.0-32-bit.exe
Git-2.43.0-32-bit.exe
# 参照https://zhuanlan.zhihu.com/p/443527549?utm_id=0  安装指南进行安装
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

`docs`文件夹存放的是所有wiki文件（markdown格式）

`mkdocs-material`为依赖库

`mkdocs.yml`为配置文件

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
