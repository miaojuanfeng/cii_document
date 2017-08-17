# CII\_Router

路由类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $class | Public | 当前访问的控制器类名 |
| $method | Public | 当前访问的控制器方法 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Router::\_\_construct\(\) | 构造函数 |
| CII\_Router::set\_class\(\) | 设置访问的控制器类名 |
| CII\_Router::fetch\_class\(\) | 获取访问的控制器类名 |
| CII\_Router::set\_method\(\) | 设置访问的控制器方法 |
| CII\_Router::fetch\_method\(\) | 获取访问的控制器方法 |

#### \_\_construct\(\)

```
/**
* 构造函数
* Class constructor
*
* Runs the route mapping function.
*
* @return    void
*/
public function __construct()
```

#### set\_class\(\)

```
/**
* 设置访问的控制器类名
* Set class name
*
* @param    string    $class    Class name
*
* @return    void
*/
public function set_class($class)
```

#### fetch\_class\(\)

```
/**
* 获取访问的控制器类名
* Fetch the current class
*
* @return    string
*/
public function fetch_class()
```

#### set\_method\(\)

```
/**
* 设置访问的控制器方法
* Set method name
*
* @param     string    $method    Method name
*
* @return    void
*/
public function set_method($method)
```

#### fetch\_method\(\)

```
/**
* Fetch the current method
*
* @return    string
*/
```



