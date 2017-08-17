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
| CII\_Session::\_\_get\(\) | 魔术方法，从 CII\_Session 类中获取成员变量 |
| CII\_Session::\_\_set\(\) | 魔术方法，设置 CII\_Session 类中成员变量的值 |
| CII\_Session::set\_tempdata\(\) | 设置带有有效时间的 session 数据 |
| CII\_Session::tempdata\(\) | 获取带有有效时间的 session 数据 |
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

#### \_\_get\(\)

```
/**
* 从CII_Session类中获取成员变量
* Magic method 
*
* Fetch member variables from CII_Session no mater it's defined or not.
*
* @return    mixed
*/
public function __get()
```

#### \_\_set\(\)

```
/**
* 设置CII_Session类中成员变量的值
* Magic method 
*
* Set member variables's value no mater it's defined or not.
*
* @return    void
*/
public function __set()
```



