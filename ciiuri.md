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
| CII\_URI::segment\(\) | 获取路由分段 |
| CII\_URI::rsegment\(\) | 获取路由后分段 |
| CII\_URI::segment\_array\(\) | 获取路由数组 |
| CII\_URI::rsegment\_array\(\) | 获取路由后数组 |
| CII\_URI::total\_segments\(\) | 获取路由分段数量 |
| CII\_URI::total\_rsegments\(\) | 获取路由后分段数量 |
| CII\_URI::uri\_string\(\) | 获取路由字符串 |
| CII\_URI::ruri\_string\(\) | 获取路由后字符串 |
| CII\_URI::slash\_segment\(\) |  |
| CII\_URI::slash\_rsegment\(\) |  |
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
* 获取路由分段
* Fetch URI Segment
*
* @see        CII_URI::$segments
* @param      int          $n            Index
* @param      mixed        $no_result    What to return if the segment index is not found
*
* @return     mixed
*/
public function segment($n, $no_result = NULL)
```

#### rsegment\(\)

```
/**
* 获取路由后的分段
* Fetch URI "routed" Segment
*
* Returns the re-routed URI segment (assuming routing rules are used)
* based on the index provided. If there is no routing, will return
* the same result as CI_URI::segment().
*
* @see        CII_URI::$rsegments
* @see        CII_URI::segment()
* @param      int        $n            Index
* @param      mixed      $no_result    What to return if the segment index is not found
*
* @return     mixed
*/
public function rsegment($n, $no_result = NULL)
```

#### segment\_array\(\)

```
/**
* 获取路由数组
* Segment Array
*
* @return    array    CII_URI::$segments
*/
public function segment_array()
```

#### rsegment\_array\(\)

```
/**
* 获取路由后数组
* Routed Segment Array
*
* @return    array    CII_URI::$rsegments
*/
public function rsegment_array()
```

#### total\_segments\(\)

```
/**
* 获取路由分段数量
* Total number of segments
*
* @return    int
*/
public function total_segments()
```

#### total\_rsegments\(\)

```
/**
* 获取路由后分段数量
* Total number of routed segments
*
* @return    int
*/
public function total_rsegments()
```

#### uri\_string\(\)

```
/**
* 获取路由字符串
* Fetch URI string
*
* @return    string    CII_URI::$uri_string
*/
public function uri_string()
```

#### ruri\_string\(\)

```
/**
* 获取路由后字符串
* Fetch Re-routed URI string
*
* @return    string
*/
public function ruri_string()
```

#### slash\_segment\(\)

```
/**
* 返回末尾加'/'的路由分段
* Slash segment
*
* Fetches an URI segment with a slash.
*
* @param     int        $n        Index
* @param     string     $where    Where to add the slash ('t' == 'trailing' or 'l' == 'leading')
*
* @return    string
*/
public function slash_segment($n, $where = 't')
```

#### slash\_rsegment\(\)

```
/**
* 返回末尾加'/'的路由后分段
* Slash routed segment
*
* Fetches an URI routed segment with a slash.
*
* @param     int        $n        Index
* @param     string     $where    Where to add the slash ('t' == 'trailing' or 'l' == 'leading')
*
* @return    string 
*/
public function slash_rsegment($n, $where = 't')
```

#### assoc\_to\_uri\(\)

```
/**
* 数组转成uri字符串
* Assoc to URI
*
* Generates a URI string from an associative array.
*
* @param     array     $array    Input array of key/value pairs
*
* @return    string    URI string
*/
public function assoc_to_uri($array)
```

#### uri\_to\_assoc\(\)

```
/**
* URI to assoc
*
* Generates an associative array of URI data starting at the supplied
* segment index. For example, if this is your URI:
*
* example.com/user/search/name/joe/location/UK/gender/male
*
* You can use this method to generate an array with this prototype:
*
*    array (
*        name => joe
*        location => UK
*        gender => male
*     )
*
* @param    int    $n        Index (default: 3)
* @param    array    $default    Default values
*
* @return    array
*/
public function uri_to_assoc($n = 3, $default = array())
```

#### ruri\_to\_assoc\(\)

```
/**
* Routed URI to assoc
*
* Identical to CI_URI::uri_to_assoc(), only it uses the re-routed
* segment array.
*
* @see		CI_URI::uri_to_assoc()
* @param 	int	$n		Index (default: 3)
* @param 	array	$default	Default values
*
* @return 	array
*/
public function ruri_to_assoc($n = 3, $default = array())
```



