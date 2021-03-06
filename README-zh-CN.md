## 介绍

Codeforces Contest Helper 是一个基于 HTML/JS/CSS 开发的自动监测 Codeforces 比赛数据的项目，目前可以经过 NW.js 运行。它拥有以下特性：

- 项目文件本身非常小，**不到 1.5M 的空间** 使其可以被快速下载
- 在经过 NW.js 运行后 **可以放在桌面角落**
- 在比赛和测试阶段每 30s 更新一次数据，做到 **实时**
- 对于虚拟比赛和比赛排名回馈等无法获取的排名信息，使用 **独立开发的比赛排名预测系统** ，可以比较准确的预测排名信息
- 可以通过预测系统生成已结束比赛的 **排名图像**
- 可以任意切换 **深浅色主题**

## 图示

![](https://cdn.luogu.com.cn/upload/image_hosting/msni3fvj.png)

---

![](https://cdn.luogu.com.cn/upload/image_hosting/jqbee3jd.png)

---

![](https://cdn.luogu.com.cn/upload/image_hosting/fn9he0jm.png)


## 下载和运行

你可以通过 EXE 文件运行，但是 EXE 文件文件较大且当前并没有更新，所以为了适配全平台并且避免 Github 的慢速下载，你可以通过下载 NW.js 达到运行的目的。

1. 在 [NW.js 镜像站](http://npm.taobao.org/mirrors/nwjs/) 中下载适配系统的最新版 NW.js 并解压（多平台适应和高速下载）

2. 从 [Github 项目地址](https://github.com/tiger2005/CodeforcesContestHelper) 下载项目 ZIP 文件 （由于文件本身很小，可以快速下载）

3. 在解压项目后将项目文件夹拖到前面下载好的 nw.exe 中，稍等片刻即可开启 （可以前往 NW.js 教程进行命令行启动程序的教学）

4. 可以通过 NW.js 本身的功能将其打包为可执行文件

## 使用方法

输入你的 Codeforces 名字和比赛 ID（比赛的 ID 可以从地址栏得到，例如 https://codeforces.com/**1234**/standings），随后按下“发送”按钮，稍等片刻即可加载信息。

**注意：任何对属性的修改都需要按下发送按钮进行确认，防止误按。**

如果你想得到非官方参赛者信息（例如你在运行虚拟比赛，或者你想知道练习情况），请按下“用户”按钮，待切换为“多个用户”按钮后发送。获取的比赛信息将在 Time 所在单选框展现，在选择后发送即可。

**注意：CF 不会将没有操作的虚拟比赛作为比赛算入，所以你需要提交一次才能获取虚拟赛信息。**

如果你不想不小心修改输入的信息，可以按下“锁”按钮，这个按钮可以将你的名字、比赛 ID 和比赛时间锁上。

按下“太阳/月亮”按钮可以切换背景。

按下“向下”按钮切换到小型窗口。这里你将只能获取一些基本信息，而无法修改比赛的属性。你仍然可以修改主题或者退出，以及回到大型窗口。

当你正在获取一场正在进行的虚拟赛或是一场已经结束的比赛的信息，在菜单栏将会多出一个“数据库”按钮。这个按钮可以切换排名的获取方式。按下后再次发送，程序将使用排名预测器进行排名预测。程序将会从 Codeforces 获取这场比赛的所有排名，并且自动生成排名曲线。否则，程序会以 Codeforces 发来的排名为准。虚拟赛的排名将会只增不降，比赛结束后也不会生成相关信息。

**注意：选择排名预判器需要所有的排名列表并且会每隔 1 分钟生成一个排名数据，一次获取可能会消耗大约 20MB 的内存。**

按下“退出”按钮以退出。在锁定状态下，这个按钮将会失效。

在每次获取后将会获取以下数据：

- 比赛 ID 、比赛名称和比赛类型。前两个将会显示出来，最后一个将会传入预判器进行预判处理。

- 比赛起始时间和状态。这个将会用来进行逻辑的判断。

- 比赛题目列表以及（可能存在的）提交状态。你可以通过鼠标滚轮滚动控制题目列表。如果你是一个参赛者或者虚拟赛参赛者，在最后一处将会显示罚时、hack 信息和总得分。

- 当前排名。当前排名将会显示在最上方，随后推入曲线图中。曲线图可以被收起。

## 说明

所有的获取功能均通过 Codeforces 官方的 API，而不是捕获网页。所以在 codeforces.com 无法登录的时候，该工具将会失效（镜像站失效无影响）。

图表绘制使用 Highcharts，图标来自 Font Awesome，JS 代码编写有 jQuery 和 JSON3 的辅助。

想试一下它的功能吗？你可以开始一场虚拟比赛，或者捕获之前比赛的排名数据。

该项目仍然在开发和编写过程当中。如果大家发现了任何 bug，欢迎反馈。