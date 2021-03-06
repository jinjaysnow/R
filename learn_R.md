### 学习R语言之路
> Author: Jin Jay  
> Created On: 2014-05-09

---

#### 记录学到的一些函数
安装包 install.packages(packageName)

使用包require()/libarary()

list() 列表类型，访问使用$ 或 [[]] 

data.frame(a, b, c) 数据帧，长度相同的向量的列表； 访问data.frame中的元素使用[[]]双中括号，或者使用 frameName$elementName 访问, 与list不同的是data.frame 是一种类似数据库存储的结构，每一行代表一个数据项。

new.env(hash = TRUE, parent = parent.frame(), size = 29L) environment 与 list 的区别主要在两个方面：

> environment只能通过子变量名来访问（使用operator $ or [[），它的子变量没有排序，所以不能通过id来访问。
> environment在做为参数传入程序时，并不进行拷贝，而是传递一个地址。这就意味着我们在编写程序时可以使用environment来实现以形参的形式来对数据进行修改。

``` R
f <- function();
enviroment(f);
mget(c(...), envir = env, ifnotfound=NA);# 获取所有的环境值
```
contour(matrix): 绘制矩阵的等高线图

persp(matrix, expand = 0.2): 矩阵透视图, expand参数可选，表示z轴放大比例

image(matrix): 矩阵彩色热图

barplot(x): 绘制条形图

abline(h=?,v=?): 绘制一条参考的直线，h代表水平线，v代表垂直线

mean(): 平均值 median(): 众数 sd(): 方差 

legend(): 在图的某一个位置做标记对图进行说明

``` R
legend("topright", c("gems", "gold", "silver"), pch=1:3)
```

读取文件中的数据 csv格式： read.csv(filename) 返回一个frame对象

通用读取文件的方法

``` R
read.table(file, header = FALSE, sep = "", quote = "\"'",
           dec = ".", row.names, col.names,
           as.is = !stringsAsFactors,
           na.strings = "NA", colClasses = NA, nrows = -1,
           skip = 0, check.names = TRUE, fill = !blank.lines.skip,
           strip.white = FALSE, blank.lines.skip = TRUE,
           comment.char = "#",
           allowEscapes = FALSE, flush = FALSE,
           stringsAsFactors = default.stringsAsFactors(),
           fileEncoding = "", encoding = "unknown", text, skipNul = FALSE)
           # header表示是否包含数据的标题， sep表示数据间隔的字符（一般为\t）
```

