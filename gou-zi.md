# 钩子

CII 的钩子特性提供了一种方法来修改框架的内部运作流程。CII 的运行遵循着一个特定的流程，你可以参考 CodeIgniter 的应用程序流程图 。但是，有些时候你可能希望在执行流程中的某些阶段添加一些动作，例如在控制器加载之前或之后执行一段脚本，或者在其他的某些位置触发你的脚本。

#### 1. 启用钩子

钩子特性可以在 config/config.php 文件中全局的启用或禁用，设置下面这个参数：

```
$config['enable_hooks'] = TRUE;
```

#### 2. 定义钩子

钩子是在 application/config/hooks.php 文件中被定义的，每个钩子可以定义为下面这样的数组格式:

```
$hook['pre_controller'] = array(
    'class'    => 'MyClass',
    'function' => 'Myfunction',
    'filename' => 'Myclass.php',
    'filepath' => '',
    'initparams' => array('a', 'b', 'c'),
    'funcparams' => array('beer', 'wine', 'snacks')
);
```

数组的索引为你想使用的挂钩点名称，譬如上例中挂钩点为 pre\_controller ， 下面会列出所有可用的挂钩点。钩子数组是一个关联数组，数组的键值以是下面这些：

* `class`
  你希望调用的类名，如果你更喜欢使用过程式的函数的话，这一项可以留空。
* `function`
  你希望调用的方法或函数的名称。
* `filename`
  包含你的类或函数的文件名。
* `filepath`
  包含你的脚本文件的目录名。 注意： 你的脚本必须放在 hooks/ 目录里面，所以 filepath 是相对 hooks/ 目录的路径，举例来说，如果你的脚本位于 hooks/myhooks/ ，那么 filepath 可以简单的设置为 'myhooks/' ，如果你的脚本位于 hooks/utilities/myhooks/ ， 那么 filepath 可以设置为 'utilities/myhooks/' ，路径后需要加斜线。如果你的脚本位于 hooks/ ，那么 filepath 可留空或省略此项。
* `initparams`
  你希望传递给你脚本类的构造函数的任何参数，为数组形式，可选。
* `funcparams`
  你希望传递给你脚本函数或方法的任何参数，为数组形式，可选。

#### 3. 多次调用同一个挂钩点

如果你想在同一个挂钩点处添加多个脚本，只需要将钩子数组变成二维数组即可，像这样:

```
$hook['pre_controller'][] = array(
    'class'    => 'MyClass',
    'function' => 'MyMethod',
    'filename' => 'Myclass.php',
    'filepath' => '',
    'initparams' => array('a', 'b', 'c'),
    'funcparams' => array('beer', 'wine', 'snacks')
);
$hook['pre_controller'][] = array(
    'class'    => 'MyOtherClass',
    'function' => 'MyOtherMethod',
    'filename' => 'Myotherclass.php',
    'filepath' => '',
    'initparams' => array('a', 'b', 'c'),
    'funcparams'   => array('red', 'yellow', 'blue')
);
```

注意数组索引后面多了个中括号:

```
$hook['pre_controller'][]
```

这可以让你在同一个挂钩点处执行多个脚本，多个脚本执行顺序就是你定义数组的顺序。

#### 4. 挂钩点

以下是所有可用挂钩点的一份列表：

* `pre_system`
  在系统执行的早期调用，这个时候只有 基准测试类 和 钩子类 被加载了， 还没有执行到路由或其他的流程。
* `pre_controller`
  在你的控制器调用之前执行，所有的基础类都已加载，路由和安全检查也已经完成。
* `post_controller_constructor`
  在你的控制器实例化之后立即执行，控制器的任何方法都还尚未调用。
* `post_controller`  
  在你的控制器完全运行结束时执行。  
  display\_override 覆盖 \_display\(\) 方法，该方法用于在系统执行结束时向浏览器发送最终的页面结果。 这可以让你有自己的显示页面的方法。注意你可能需要使用 `$this->CII = &cii_get_instance()` 方法来获取 CII 超级对象，以及使用 `$this->CII->output->get_output()` 方法来 获取最终的显示数据。
* `cache_override`  
  使用你自己的方法来替代 输出类 中的 \_display\_cache\(\) 方法，这让你有自己的缓存显示机制。
* `post_system`
  在最终的页面发送到浏览器之后、在系统的最后期被调用。



