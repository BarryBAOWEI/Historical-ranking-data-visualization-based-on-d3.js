# 动态排名数据可视化
这是一个数据可视化项目，基于D3.js。能够将历史数据排名转化为动态柱状图图表。

这个项目旨在降低此类视频的使用门槛与提高生产效率，使得没有编程经验的用户也能无痛制作排名可视化动画。

----

# 一句话用法

只需打开dist目录下的bargraph.html。然后点击页面中间的选择文件按钮，接着选择csv格式的数据文件，便可以看到可视化的结果。

# 数据格式

本项目能够读取csv格式的数据。

具体的格式如下：

name|type|value|date
--|--|--|--
名称1|类型1|值1|日期1
名称2|类型2|值2|日期2

其中“名称”会出现在柱状图的左侧作为Y轴，而“类型-名称”会作为附加信息出现在柱状图上。

类型与柱状图的颜色相关，建议命名为不包含空格或者特殊符号的中英文字符。

值与柱状图的长度绑定，必须是整数或浮点数。

日期建议使用的格式为"YYYY-MM-DD"。

# 配置

本项目能够进行一些简单的定制。

使用记事本或者其他文本编辑器，打开config.js的文件即可进行一些参数的修改。

---
# 更新日志

## 2018-07-19

- 现在可以在配置文件里控制每日最大的显示条目数了。
- 现在在配置文件里配置成不显示type能够移除柱状图上的类型了。
- 现在能够在配置文件中选择自定义颜色了。
- 使用更加合理的随机颜色。
- speed属性更名为interval_time。

## 2018-07-20

- 现在可以关闭自动排序了。
- 现在能选择条状图进入时是从零开始还是从当前的数值开始了。

## 2018-07-21

- 修复了上色机制，并且现在可以选择按照类型还是按照名称上色了。

## 2018-07-22

- 修复了自定义颜色时，无法按照名称来上色的BUG。
- 修复了自定义颜色时，名称和数值没有正确上色的BUG。

## 2018-07-23

- 添加了数据都很大时的坐标轴策略，如果所有数字都很大，导致拉不开差距则开启此项使得坐标原点变换为（最小值）*2-（最大值）。
- 添加了当数字量级差距巨大时的坐标轴策略（开启半对数坐标）。
- 修复了时间的排序方式。
- 添加了reverse配置，使得使得最短的bar位于最上方。

## 2018-07-31

- 修复了中途修改type不会改变类型的问题。
- 删除了运行不正常的dividing_line，改为使用allow_up属性，该属性使得高于平均值的条目能够上浮退出。

---

# TODO：

- 平滑类型改变时的颜色过渡。