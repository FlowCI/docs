# 触发器设置

除手动触发外，flowci 支持使用者精确控制触发条件。
默认所有分支的 push 请求都会触发新的 Build，可在 flow “工作流设置” 中修改触发条件。

<img src="https://images-cdn.shimo.im/UTfS0rPa7T8JXrop/flowconfig.jpg" style="zoom:20%">

**如何关闭 push 请求触发 Build？**

在 flow “工作流设置” 触发器设置中点击关闭 Git Push。

**如何设置部分分支的 push 请求触发 Build？**

点击 "正则匹配",在输入框中输入需要触发 Build 的分支，支持精确匹配 ，和通配符（*）模糊匹配两种方式，编辑完成后点击保存分支设置。

**如何设置定时触发？**

在 flow “工作流设置” 定时任务设置中选择要定时触发的分支，填写 crontab 命令。

如何在 flowci 中使用 crontab 命令:

<img src="https://images-cdn.shimo.im/QNf3YRr1Cagn54ZQ/linuxcontab.png" style="zoom:90%">

在以上各个字段中，还可以使用以下特殊字符：

星号（*）：代表所有可能的值，例如month字段如果是星号，则表示在满足其它字段的制约条件后每月都执行该命令操作。

逗号（,）：可以用逗号隔开的值指定一个列表范围，例如，“1,2,5,7,8,9”

中杠（-）：可以用整数之间的中杠表示一个整数范围，例如“2-6”表示“2,3,4,5,6”

正斜线（/）：可以用正斜线指定时间的间隔频率，例如“0-23/2”表示每两小时执行一次。同时正斜线可以和星号一起使用，例如*/10，如果用在minute字段，表示每十分钟执行一次。

在 flowci 中我们只需要输入命令的执行时间即可，例：

**每一分钟执行一次 Build：**

```.
* * * * *
```

**每两个小时执行一次 Build：**

```.
0 */2 * * *
```

**每天早上7点执行一次 Build：**

```.
0 7 * * *
```

**每天早上6点10分执行一次 Build：**

```.
10 6 * * *
```

**每晚的21:30执行一次 Build：**

```.
30 21 * * *
```

**周一到周五每天下午 5:00 执行一次 Build：**

```.
0 17 * * 1-5
```



<br/><br/><br/>

<div id="bom">
<a href="./quick_iosBuild.md">上一节： iOS 项目构建 </a> | 
<a href="./quick_envir.md">下一节： 环境变量设置 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/>



















