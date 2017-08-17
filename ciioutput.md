# CII\_Output

输出类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $final\_output | Public | 缓冲区，保存最终输出字符串 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Output::\_\_construct\(\) | 构造函数 |
| CII\_Output::append\_output\(\) | 追加输出字符串到缓冲区 |
| CII\_Output::display\(\) | 输出缓冲区里的内容 |
| CII\_Output::get\_output\(\) | 返回缓冲区里的字符串 |
| CII\_Output::set\_output\(\) | 设置缓冲区内容 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* Determines whether zLib output compression will be used.
*
* @return    void
*/
public function __construct()
```

#### append\_output\(\)

```
/**
* Append Output
*
* Appends data onto the output string.
*
* @param     string      $output    Data to append
* @return    CI_Output
*/
public function append_output($output)
```

#### display\(\)

#### get\_output\(\)

#### set\_output\(\)



