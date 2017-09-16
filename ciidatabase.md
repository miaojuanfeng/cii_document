# CII\_Database

数据库类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $conn\_id | Public | Mysqli类实例化后的数据库链接对象 |
| $result\_id | Public | Mysqli\_result类实例化后的数据库查询结果对象 |
| $hostname | Public | 数据库地址 |
| $username | Public | 数据库用户名 |
| $password | Public | 数据库密码 |
| $database | Public | 数据库名称 |
| $affected\_rows | Public | 执行sql后受影响的数据条数 |
| $insert\_id | Public | 新插入数据的id |
| $last\_query | Public | 最后一次查询语句 |
| $select | Protected | select查询条件 |
| $from | Protected | from查询条件 |
| $where | Protected | where查询条件 |
| $order\_by | Protected | order by查询条件 |
| $limit | Protected | limit查询条件 |
| $group\_start | Protected | \(查询条件 |
| $group\_end | Protected | \)查询条件 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Database::\_\_construct\(\) | 构造函数，初始化数据库链接 |
| CII\_Database::query\(\) | 执行一条sql查询 |
| CII\_Database::affected\_rows\(\) | 返回执行sql后受影响的数据条数 |
| CII\_Database::select\(\) | 构造select查询条件 |
| CII\_Database::from\(\) | 构造from查询条件 |
| CII\_Database::where\(\) | 构造where查询条件 |
| CII\_Database::order\_by\(\) | 构造order by查询条件 |
| CII\_Database::limit\(\) | 构造limit查询条件 |
| CII\_Database::get\(\) | 组合查询条件，执行一条sql查询 |
| CII\_Database::insert\(\) | 插入数据 |
| CII\_Database::update\(\) | 更新数据 |
| CII\_Database::delete\(\) | 删除数据 |
| CII\_Database::last\_query\(\) | 返回最后一次查询语句 |
| CII\_Database::insert\_id\(\) | 返回新插入数据的id |
| CII\_Database::group\_start\(\) | 构造查询条件\( |
| CII\_Database::group\_end\(\) | 构造查询条件\) |
| CII\_Database::or\_where\(\) | 构造where ... or ... 查询条件 |
| CII\_Database::escape\_str\(\) | 字符串转义 |

#### \_\_construct\(\)

```
/**
* Constructor
*
* @return    void
*/
public function __construct()
```

#### query\(\)

```
/**
* Execute the query
*
* Accepts an SQL string as input and returns a result object upon
* successful execution of a "read" type query. Returns boolean TRUE
* upon successful execution of a "write" type query. Returns boolean
* FALSE upon failure.
*
* @param    string    $sql
*
* @return    mixed
*/
public function query($sql)
```

#### affected\_rows\(\)

```
/**
* Affected Rows
*
* @return    int
*/
public function affected_rows()
```

#### select\(\)

```
/**
* Select
*
* Generates the SELECT portion of the query
*
* @param    string
* 
* @return    CI_DB_query_builder
*/
public function select($select = '*')
```

#### where\(\)

```
/**
* WHERE
*
* Generates the WHERE portion of the query.
* Separates multiple calls with 'AND'.
*
* @param    mixed
* @param    mixed
* @param    bool
*
* @return   CI_DB_query_builder
*/
public function where($key, $value = NULL)
```

#### order\_by\(\)

```
/**
* ORDER BY
*
* @param    string    $orderby
* @param    string    $direction    ASC, DESC or RANDOM
*
* @return    CI_DB_query_builder
*/
public function order_by($orderby, $direction = '')
```

#### limit\(\)

```
/**
* LIMIT
*
* @param    int    $value    LIMIT value
* @param    int    $offset    OFFSET value
*
* @return   void
*/
public function limit($value, $offset = 0)
```

#### get\(\)

```
/**
* Get
*
* Compiles the select statement based on the other functions called
* and runs the query
*
* @param    string    the table
* @param    string    the limit clause
* @param    string    the offset clause
*
* @return    object
*/
public function get($table = '', $limit = NULL, $offset = NULL)
```

#### insert\(\)

```
/**
* Insert
*
* Compiles an insert string and runs the query
*
* @param    string    the table to insert data into
* @param    array     an associative array of insert values
*
* @return    object
*/
public function insert($table = '', $set = NULL)
```

#### update\(\)

```
/**
* UPDATE
*
* Compiles an update string and runs the query.
*
* @param    string    $table
* @param    array     $set    An associative array of update values
* @param    mixed     $where
* @param    int       $limit
*
* @return    object
*/
public function update($table = '', $set = NULL, $where = NULL, $limit = NULL)
```

#### delete\(\)

```
/**
* Delete
*
* Compiles a delete string and runs the query
*
* @param    mixed    the table(s) to delete from. String or array
* @param    mixed    the where clause
* @param    mixed    the limit clause
*
* @return    mixed
*/
public function delete($table = '', $where = '', $limit = NULL)
```

#### last\_query\(\)

```
/**
* Returns the last query that was executed
*
* @return    string
*/
public function last_query()
```

#### insert\_id\(\)

```
/**
* Insert ID
*
* @return    int
*/
public function insert_id()
```

#### group\_start\(\)

```
/**
* Starts a query group.
*
* @return    void
*/
public function group_start()
```

#### group\_end\(\)

```
/**
* Ends a query group
*
* @return    void
*/
public function group_end()
```

#### or\_where\(\)

```
/**
* OR WHERE
*
* Generates the WHERE portion of the query.
* Separates multiple calls with 'OR'.
*
* @param    mixed
* @param    mixed
*
* @return    void
*/
public function or_where($key, $value = NULL)
```

#### escape\_str\(\)

```
/**
* Escape string
*
* Escape string in SQL
*
* @param    string
*
* @return    string
*/
public function escape_str($str)
```



