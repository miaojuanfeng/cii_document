# CII\_DB\_result

数据库结果类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $conn\_id | Public | Mysqli类实例化后的数据库链接对象 |
| $result\_id | Public | Mysqli\_result类实例化后的数据库查询结果对象 |
| $result\_array | Public | 数组形式保存的查询结果 |
| $row\_array | Public | 数组形式保存的一行结果 |
| $num\_rows | Public | 查询结果的行数 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_DB\_result::\_\_construct\(\) | 构造函数 |
| CII\_DB\_result::result\(\) | 以对象数组形式返回查询结果 |
| CII\_DB\_result::result\_array\(\) | 以一个纯粹的数组形式返回查询结果 |
| CII\_DB\_result::row\_array\(\) | 返回单独一行结果。如果你的查询不止一行结果，它只返回第一行。返回的结果是数组形式 |
| CII\_DB\_result::num\_rows\(\) | 返回查询结果的行数 |

#### \_\_construct\(\)

```
/**
* Constructor
*
* @return    void
*/
public function __construct()
```

#### result\(\)

```
/**
* Query result. Acts as a wrapper function for the following functions.
*
* @param     string    $type    'object', 'array' or a custom class name
* @return    array
*/
```

#### result\_array\(\)

#### row\_array\(\)

#### num\_rows\(\)



