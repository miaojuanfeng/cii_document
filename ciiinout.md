# CII\_Input

输入类。

#### Member Variables

| 无 |
| :---: |


#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Input::\_\_construct\(\) | 构造方法 |
| CII\_Input::post\(\) | 返回$\_POST数组 |
| CII\_Input::get\(\) | 返回$\_GET数组 |
| CII\_Input::post\_get\(\) | 获取提交的变量。先查找$\_POST数组，查找不到后再查找$\_GET数组 |
| CII\_Input::get\_post\(\) | 获取提交的变量。先查找$\_GET数组，查找不到后再查找$\_POST数组 |
| CII\_Input::num\_post\(\) | 返回$\_POST获取的数据个数 |
| CII\_Input::num\_get\(\) | 返回$\_GET获取的数据个数 |
| CII\_Input::server\(\) | 返回$\_SERVER数组 |
| CII\_Input::is\_post\(\) | 判断表单是否以$\_POST方式提交 |
| CII\_Input::is\_get\(\) | 判断表单是否以$\_GET方式提交 |
| CII\_Input::user\_agent\(\) | 返回客户端操作系统、浏览器等信息 |
| CII\_Input::method\(\) | 返回表单提交的方法，$\_POST或$\_GET |
| CII\_Input::ip\_address\(\) | 返回客户端IP地址 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* Determines whether to globally enable the XSS processing
* and whether to allow the $_GET array.
*
* @return    void
*/
public function __construct()
```

#### post\(\)

```
/**
* Fetch an item from the POST array
*
* @param     mixed    $index        Index for item to be fetched from $_POST
*
* @return    mixed
*/
public function post($index = NULL)
```

#### get\(\)

```
/**
* Fetch an item from the GET array
*
* @param    mixed    $index        Index for item to be fetched from $_GET
*
* @return    mixed
*/
public function get($index = NULL)
```

#### post\_get\(\)

```
/**
* Fetch an item from POST data with fallback to GET
*
* @param     string    $index        Index for item to be fetched from $_POST or $_GET
*
* @return    mixed
*/
public function post_get($index)
```

#### get\_post\(\)

```
/**
* Fetch an item from GET data with fallback to POST
*
* @param    string    $index        Index for item to be fetched from $_GET or $_POST
*
* @return    mixed
*/
public function get_post($index)
```

#### num\_post\(\)

```
/**
* Fetch POST data total 
*
* @return    int
*/
public function num_post()
```

#### num\_get\(\)

```
/**
* Fetch GET data total 
*
* @return    int
*/
public function num_get()
```

#### server\(\)

```
/**
* Fetch an item from the SERVER array
*
* @param    mixed    $index        Index for item to be fetched from $_SERVER
*
* @return   mixed
*/
public function server($index)
```

#### is\_post\(\)

```
/**
* Check is it POST method
*
* @return   bool
*/
public function is_post()
```

#### is\_get\(\)

```
/**
* Check is it GET method
*
* @return   bool
*/
public function is_get()
```

#### user\_agent\(\)

```
/**
* Fetch User Agent string
*
* @return    string|null    User Agent string or NULL if it doesn't exist
*/
public function user_agent()
```

#### method\(\)

```
/**
* Get Request Method
*
* Return the request method
*
* @param      bool    $upper    Whether to return in upper or lower case. (default: FALSE)
*
* @return     string
*/
public function method($upper = FALSE)
```

#### ip\_address\(\)

```
/**
* Fetch the IP Address
*
* Determines and validates the visitor's IP address.
*
* @return    string    IP address
*/
public function ip_address()
```



