# 基准测试类

CII 有一个一直都是启用状态的基准测试类，用于计算两个标记点之间的时间差。该类是由系统自动加载，无需手动加载。

另外，基准测试总是在框架被调用的那一刻开始，在输出类向浏览器发送最终的视图之前结束。这样可以显示出整个系统执行的精确时间。

#### 1. 使用基准测试类

基准测试类可以在你的 控制器、视图 以及 模型 中使用。

使用流程如下：

> 1. 标记一个起始点
> 2. 标记一个结束点
> 3. 使用 elapsed\_time 函数计算时间差。

这里是个真实的代码示例:

```php
$this->benchmark->mark('code_start');
// 一些程序代码...
$this->benchmark->mark('code_end');
echo $this->benchmark->elapsed_time('code_start', 'code_end');
```

`code_start` 和 `code_end` 这两个单词是随意的，它们只是两个用于标记的单词而已，你可以任意使用其他你想使用的单词，另外，你也可以设置多个标记点。

看如下示例:

```php
$this->benchmark->mark('dog');
// 一些程序代码...
$this->benchmark->mark('cat');
// 更多的程序代码...
$this->benchmark->mark('bird');
echo $this->benchmark->elapsed_time('dog', 'cat');
echo $this->benchmark->elapsed_time('cat', 'bird');
echo $this->benchmark->elapsed_time('dog', 'bird');
```

#### 2. 在性能分析器中使用基准测试点

如果你希望你的基准测试数据显示在性能分析器中， 那么你的标记点就需要成对出现，而且标记点名称需要以 `_start` 和 `_end` 结束， 每一对的标记点名称应该一致。例如:

```php
$this->benchmark->mark('my_mark_start');
// 一些程序代码...
$this->benchmark->mark('my_mark_end');
$this->benchmark->mark('another_mark_start');
// 更多的程序代码...
$this->benchmark->mark('another_mark_end');
```

#### 3. 显示总执行时间

如果你想显示从 CII 运行开始到最终结果输出到浏览器之间花费的总时间，只需简单的将下面这行代码放入你的视图文件中:

```
<?php echo $this->benchmark->elapsed_time();?>
```

你大概也注意到了，这个方法和上面例子中的介绍的那个计算两个标记点之间时间差的方法是一样的，只是不带任何参数。当不设参数时，CII 在向浏览器输出最终结果之前不会停止计时，所以无论你在哪里使用该方法，输出的计时结果都是总执行时间。

这个方法不带参数时返回字符串 `{elapsed_time}`，需要echo出来或赋值给变量，字符串将在视图输出前被替换成具体的时间。

不能在视图中直接输出字符串 `{elapsed_time}` 的方式来显示总执行时间:

```
<?php echo "{elapsed_time}"; ?>
```

这样做字符串不会被替换。

如果你想在你的控制器方法中进行基准测试，你需要设置你自己的标记起始点和结束点。

#### 4. 显示内存占用

如果你的 PHP 在安装时使用了 `--enable-memory-limit` 参数进行编译，你就可以在你的视图文件中使用下面这行代码来显示整个系统所占用的内存大小:

```
<?php echo $this->benchmark->memory_usage();?>
```

这个方法返回字符串 `{memory_usage}`，需要echo出来或赋值给变量，字符串将在视图输出前被替换成具体的内存大小。

这个方法只能在视图文件中使用，显示的结果代表整个应用所占用的内存大小。

不能在视图中直接输出字符串 `{memory_usage}` 的方式来显示内存大小:

```
<?php echo "{memory_usage}"; ?>
```

这样做字符串不会被替换。

#### 5. 显示内存峰值

你可以在你的视图文件中使用下面这行代码来显示整个系统所占用的内存峰值大小:

```
<?php echo $this->benchmark->memory_peak();?>
```

这个方法返回字符串 “{memory\_peak}”，需要echo出来或赋值给变量，字符串将在视图输出前被替换成具体的内存峰值大小。

这个方法只能在视图文件中使用，显示的结果代表整个应用所占用的内存峰值大小。

不能在视图中直接输出字符串 “{memory\_peak}” 的方式来显示内存峰值大小:

```
<?php echo "{memory_peak}"; ?>
```

这样做字符串不会被替换。

#### 6. 为什么不能在视图中直接输出字符串

上面说道，不能在视图中直接输出字符串 “{elapsed\_time}” 的方式来显示总执行时间，不能在视图中直接输出字符串 “{memory\_usage}” 的方式来显示内存大小，不能在视图中直接输出字符串 “{memory\_peak}” 的方式来显示内存峰值大小。

直接在视图中输出字符串固然很方便，但是 CII 无法判断视图中是否有字符串需要替换，如果在视图中没有字符串需要替换，在视图输出前依旧遍历输出字符串来查找要替换的字符串是很浪费时间并且没意义的，所以 CII 对此进行了性能优化，每次调用 benchmark 对象的方法，要替换字符串的次数加1，调用多少次方法，就替换多少次字符串。调用方法的次数为0，视图输出前不进行查找替换。

```
<?php echo $this->benchmark->elapsed_time();?>
{elapsed_time}
<?php echo $this->benchmark->elapsed_time();?>
```

上面的脚本在视图输出前将替换2次 “{elapsed\_time}” 字符串，结果如下：

```
0.0012
0.0012
{elapsed_time}
```

最后一次不会被替换。

仅做了这一项优化，在视图没有字符串需要替换时，性能提高了7倍。需要替换一次字符串时，性能提高了1倍。这是一种空间换时间的做法，稍稍增加了空间复杂度（需要内存记录替换次数，共12字节），大大降低了时间复杂度。

