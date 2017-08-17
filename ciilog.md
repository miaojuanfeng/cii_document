# CII\_Log

日志类。

#### Member Variables

| 无 |
| :---: |


#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Log::\_\_construct\(\) | 构造函数 |
| CII\_Log::write\_log\(\) | 写日志 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* @return    void
*/
public function __construct()
```

#### write\_log\(\)

```
/**
* Write Log File
*
* Generally this function will be called using the global log_message() function
*
* @param	string	the error level: 'error', 'debug' or 'info'
* @param	string	the error message
* @return	bool
*/
public function write_log($level, $msg)
```



