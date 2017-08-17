# CII\_Benchmark

基准测试类。记录页面加载时间，计算程序性能。

#### Member Variables

| Name | Access | Description$ |
| :--- | :--- | :--- |
| $marker | Public | 记录点数组 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Benchmark::\_\_construct\(\) | 构造函数 |
| CII\_Benchmark::mark\(\) | 设置一个记录点 |
| CII\_Benchmark::elapsed\_time\(\) | 计算两个记录点之间的时间 |
| CII\_Benchmark::memory\_usage\(\) | 返回内存使用量 |
| CII\_Benchmark::memory\_peak\(\) | 返回内存使用峰值 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* @return    void
*/
public function __construct()
```

#### mark\(\)

```
/**
* Set a benchmark marker
*
* Multiple calls to this function can be made so that several
* execution points can be timed.
*
* @param     string    $name    Marker name
*
* @return    void
*/
public function mark($name)
```

#### elapsed\_time\(\)

```
/**
* Elapsed time
*
* Calculates the time difference between two marked points.
*
* If the first parameter is empty this function instead returns the
* {elapsed_time} pseudo-variable. This permits the full system
* execution time to be shown in a template. The output class will
* swap the real value for this variable.
*
* @param     string    $point1        A particular marked point
* @param     string    $point2        A particular marked point
* @param     int       $decimals      Number of decimal places
*
* @return    string    Calculated elapsed time on success,
*            an '{elapsed_string}' if $point1 is empty
*            or an empty string if $point1 is not found.
*/
public function elapsed_time($point1 = '', $point2 = '', $decimals = 4)
```

#### memory\_usage\(\)

```
/**
* Memory Usage
*
* Simply returns the {memory_usage} marker.
*
* This permits it to be put it anywhere in a template
* without the memory being calculated until the end.
* The output class will swap the real value for this variable.
*
* @return	string	'{memory_usage}'
*/
public function memory_usage()
```

#### memory\_peak\(\)



