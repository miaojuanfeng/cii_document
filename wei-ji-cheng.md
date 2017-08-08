# 伪继承

出于性能考虑，控制器与模型，不采用继承的方式，避免了多次哈希表合并操作。

控制器，模型类自动伪继承基类 CII\_Controller 、CII\_Model，不需要在控制器或模型脚本中显式继承，继承的工作由 CII 内核完成。PHP脚本位于控制器目录下那它就是一个控制器文件，PHP脚本位于模型目录下那它就是一个模型文件，换句话说就是不再根据继承的基类来区分PHP脚本文件是控制器文件还是模型文件，而是根据文件所在的目录来判断。

> 实际上 CII\_Controller、CII\_Model 基类是不存在的，CII 内核在控制器初始化过程中向控制器、模型注入了一些成员变量与方法，使得看起来控制器、模型像是继承了某个基类。这就是伪继承的含义。

例如，在控制器目录下编写一个类 home.php :

```php
class Home{
    public $name;
    public $addr;
    public function __construct(){
        $this->name = "myhome";
        $this->addr = "anywhere";
    }
    public function getaddr(){
        return $this->addr;
    }
}
```

在访问请求到来时，CII 根据路由读取 Home 类，并向 Home 类中添加 CII 框架所需的成员变量与成员函数，然后实例化 Home 类。上面的 Home 类在被 CII 读取后会变为：

```php
class Home{
    /*
    *   Home 定义的成员变量
    */
    public $name;
    public $addr;
    /*
    *   CII 添加的成员变量
    */
    public $benchmark;
    public $hooks;
    public $config;
    public $log;
    public $uri;
    public $router;
    public $output;
    public $input;
    public $lang;
    public $load;
    /*
    *   Home 定义的成员函数
    */
    public function __construct(){
        $this->name = "myhome";
        $this->addr = "anywhere";
    }
    public function getaddr(){
        return $this->addr;
    }
    /*
    *   CII 添加的成员函数
    */
    public function &get_instance(){...}
}
```

CII 添加的成员变量会在 Home 构造函数调用前实例化：

```php
$benchmark = new CII_Benchmark();
$hooks     = new CII_Hooks();
$config    = new CII_Config();
$log       = new CII_Log();
$uri       = new CII_URI();
$router    = new CII_Router();
$output    = new CII_Output();
$input     = new CII_Input();
$lang      = new CII_Lang();
$load      = new CII_Load();
```

所以，你可以在控制器 Home 中正常使用这成员变量而不用担心它们未定义：

```php
class Home{
    public $name;
    public $addr;
    public function __construct(){
        $this->name = "myhome";
        $this->addr = "anywhere";
        /*
        *   不会报错，因为 lang 在 Home 加载过程中定义了
        */
        $this->lang->load('cii');
    }
    public function getaddr(){
        return $this->addr;
        /*
        *   不会报错，因为 lang 在 Home 加载过程中定义了
        */
        $this->lang->line('cii_name');
    }
}
```

在定义类时注意不要重载了伪父类的成员属性与方法，如：

```php
class Home{
    public $name;
    public $addr;
    public $lang;
    public function __construct(){
        $this->name = "myhome";
        $this->addr = "anywhere";
    }
    public function getaddr(){
        return $this->addr;
    }
}
```

在控制器 Home 中声明一个同名成员变量 lang，CII 会认为你想重载这个变量，将不会对它进行实例化为 CII\_Lang 对象的操作。当然如果你正想重载 lang，这么做是极好的。

> 所有的成员变量与成员函数的注入过程都是在 CII 内核控制器初始化过程中完成的。

控制器伪基类定义：

```php
class CII_Controller{
    public $benchmark;
    public $hooks;
    public $config;
    public $log;
    public $uri;
    public $router;
    public $output;
    public $input;
    public $lang;
    public $load;
    public function &get_instance(){...}
}
```

模型伪基类定义：

```php
class CII_Model{
      public function __construct(){...}
      public function __get(){...}
}
```



