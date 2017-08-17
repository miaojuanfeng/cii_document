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
| CII\_Session::set\_userdata\(\) | 遗留方法。设置用户数据。 |
| CII\_Session::userdata\(\) | 遗留方法。从 $\_SESSION 数组中获取指定的项。 |
| CII\_Session::unset\_userdata\(\) | 遗留方法。从 $\_SESSION 全局变量中删除某个值。 |

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

set\_tempdata\(\)

```
/**
 * Set tempdata
 *
 * Legacy CII_Session compatibility method
 *
 * @param	mixed	$key	Session data key
 * @param	mixed	$value	Value to store
 * @param	int	$ttl	Time-to-live in seconds
 * @return	void
 */
 public function set_tempdata($key, $value = NULL, $ttl = 300)
```



