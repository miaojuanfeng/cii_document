# CII\_Session

Session类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $session | Public | 保存$\_SESSION数组 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Session::\_\_construct\(\) | 构造函数 |
| CII\_Session::\_\_get\(\) | 支持未定义成员变量，设置成员变量的值 |
| CII\_Session::\_\_set\(\) | 支持未定义成员变量，获取成员变量的值 |
| CII\_Session::set\_tempdata\(\) | 设置临时数据 |
| CII\_Session::tempdata\(\) | 获取临时数据 |
| CII\_Session::set\_userdata\(\) | 设置用户数据 |
| CII\_Session::userdata\(\) | 获取用户数据 |
| CII\_Session::unset\_userdata\(\) | 删除用户数据 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* @return    void
*/
public function __construct()
```

\_\_get\(\)

```
/**
* 从CII_Session类中获取成员变量
* Magic method 
*
* Fetch member variables from Controller if it's not defined in CII_Loader.
*
* @return    object
*/
public function __get()
```



