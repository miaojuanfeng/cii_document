#### 编译安装方式 {#21-在linux-mac下编译安装}

编译安装 PHP 扩展有两种方式：

1. 一种是静态编译，在编译 PHP 时将扩展一起编译进 PHP 程序中。因为扩展编译进了 PHP 中，所以这种编译方式的优点是加载更快，同样缺点也很明显，扩展更新后需要连同 PHP 一起重新编译。
2. 另外一种是动态编译，也就是将扩展编译成动态链接库，在 PHP 启动后再加载。这种编译方式的优点是，更新了扩展后，只需要重新编译扩展，并且编译成动态链接库可以多进程共享内存，减少内存使用，缺点仅仅是加载慢一点点而已。

推荐采用动态编译，需要先编译安装好 PHP 才能采用这种编译方式。

#### 在Linux / Mac下编译安装 {#21-在linux-mac下编译安装}

使用命令行进入 CII 框架源码目录：

```
cd cii_framework
```

使用 phpize 工具生成编译环境：

```
path_to_php/bin/phpize
```

使用 configure 工具配置编译环境：

```
./configure --with-php-config=path_to_php/bin/php-config
```

编译：

```
sudo make
```

安装：

```
sudo make install
```

运行成功后便会自动将编译好的扩展文件复制到 PHP 扩展文件夹下。

#### 在Windows下编译安装 {#22-在windows下编译安装}

编写中...

#### 配置 php.ini 文件

扩展编译完成，并且动态链接库文件已经位于 PHP 扩展文件下，接下来就是配置 PHP 启动时加载扩展，编辑 PHP 的配置文件 php.ini，添加：

```
extension=cii.so
```

之后便可检查一下 PHP 是否成功加载了 CII 扩展，在命令行中运行 PHP 程序：

```
path_to_php/bin/php -m
```

命令运行后如果在输出的列表中看到有 cii 表示扩展成功加载，如果没有成功加载，请检查 php.ini 配置中的 extension\_dir 路径及该路径下是否存在 cii.so 文件。



  




