# Week 1 · Git 学习笔记

> 本仓库路径：`D:\Projects\Notes`
> 图片统一存放于仓库内 `./assets/` 目录（请用相对路径引用，保证 push 到 GitHub 后图片不丢失）

------

## Day 1 · Git 安装与首次 commit

### 1. 查看版本，确认安装成功

```bash
git --version
```

### 2. 建立目录 + 初始化仓库

```bash
mkdir Notes
cd Notes
git init
```

**注意：** `git init` 会在目录里生成一个名为 `.git` 的隐藏文件夹（名字前面带一个英文句点）。
它是整个仓库的核心，所有版本数据都存在这里。Windows 资源管理器默认不显示隐藏文件夹，
用 PowerShell `ls -Force` 或设置"显示隐藏文件"才能看到。

### 3. 用 .md 文件记录笔记

初始化仓库后，可以在该目录里新建一个以 `.md` 结尾的文件（Markdown 格式）来记笔记，
例如本次的 `W1-Git笔记.md`。Markdown 用 `#` 分级标题、用反引号包裹代码，VSCode 可直接预览。

------

## 核心命令含义

| 命令                   | 作用                                        |
| ---------------------- | ------------------------------------------- |
| `git init`             | 把普通文件夹变成 Git 仓库                   |
| `git add`              | 把文件放进暂存区，告诉 Git "这个文件要存档" |
| `git commit -m "说明"` | 把暂存区的内容正式打包，生成一条提交记录    |
| `git log`              | 查看提交历史                                |

------

## 三板斧：add → commit → log

```bash
git add W1-Git笔记.md
git commit -m "W1 Git笔记 | 首次提交"
git log
```

**新增或修改内容后，重复上一过程即可。**（改一次 → add → commit，攒出一条条历史记录）

------

## Git 知识：仓库的三个区域

Git 仓库分为 **工作区、暂存区、版本库** 三部分：

![Git三区结构](./assets/msedge_LkLCg0nTBo.png)

- **工作区**：类似我们当前的项目文件夹，是你日常编辑文件的地方。
- **暂存区**：执行 `git add` 后文件进入的区域，相当于"准备提交的草稿箱"。
- **版本库**：执行 `git commit` 后的内容正式存档的位置，里面保存着所有的**提交历史**。

当项目里有多个文件时，用 `git add` 把需要提交的文件放进暂存区；
等暂存区的文件全部整理好，再用 `git commit` 统一提交，作为一个修改的整体版本。

------

## 提交过程图解

### 状态检查：待提交文件已进入暂存区

![暂存区标识](./assets/QvzjyjiqQa.png)

此时还没有 commit，待提交的文件已经"进入暂存区"并被标识出来。

### 提交前先配置身份（用户名 + 邮箱）

![配置身份](./assets/WthfHTYWDU.png)

提交前告诉 Git 自己的用户名和邮箱，供 commit 时记录作者。
**Git 不做真实性校验**，只是把它写进提交记录里。

```bash
git config --global user.name "AutumnBeginer"
git config --global user.email "1325693821@qq.com"
```

### 执行提交

![提交命令](./assets/wYC7BYcsk1.png)

使用 `git commit -m "说明"`，其中 `-m` 代表 message，
用来标注这次 commit 做了什么、改了什么，方便日后查看历史。

### 查看历史

![提交历史](./assets/dgGaXcbGdC.png)

紧接着输入 `git log` 查看 commit 历史：

- 顶部**黄色字符串**是 commit 编号（哈希值），每个 commit 都有唯一的编号；
- 下面是提交人和邮箱以及提交时间；
- 再往下是本次提交的说明文字。