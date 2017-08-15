# CII\_URI

URI类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $uri\_string | Public | 保存路由字符串 |
| $segments | Public | 保存分割路由后的字符串数组 |
| $rsegments | Public | 保存路由处理完后的字符串数组 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_URI::\_\_construct\(\) | 构造函数 |
| CII\_URI::segment\(\) | 返回segment数组 |
| CII\_URI::rsegment\(\) | 返回rsegment数组 |
| CII\_URI::segment\_array\(\) | 返回segment数组 |
| CII\_URI::rsegment\_array\(\) | 获取rsegment数组 |
| CII\_URI::total\_segments\(\) | 返回segment的数量 |
| CII\_URI::total\_rsegments\(\) | 返回rsegment的数量 |
| CII\_URI::uri\_string\(\) | segment转为字符串 |
| CII\_URI::ruri\_string\(\) | rsegment转为字符串 |
| CII\_URI::slash\_segment\(\) | 返回去掉'/'后的segment数组 |
| CII\_URI::slash\_rsegment\(\) | 返回去掉'/'后的rsegment数组 |
| CII\_URI::assoc\_to\_uri\(\) | 数组转为URI |
| CII\_URI::uri\_to\_assoc\(\) | URI转为数组 |
| CII\_URI::ruri\_to\_assoc\(\) | 数组转为URI |

#### \_\_construct\(\)

```
/**
* 构造函数
* Class constructor
*
* @return    void
*/
public function __construct()
```

#### segment\(\)

```
/**
* Fetch URI Segment
*
* @see		CI_URI::$segments
* @param	int		$n		Index
* @param	mixed		$no_result	What to return if the segment index is not found
* @return	mixed
*
* public function segment($n, $no_result = NULL)
*/
```



