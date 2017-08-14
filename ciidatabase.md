# CII\_Database

数据库类

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $conn\_id | Public | Mysqli类实例化的数据库链接对象 |
| $result\_id | Public |  |

#### Public Methods

| Method | Description |
| :--- | :--- |
| CII\_Database::\_\_construct\(\) | 构造函数，初始化数据库链接 |
| CII\_Database::query\(\) | 执行一条sql查询 |
| CII\_Database::affected\_rows\(\) | 返回执行sql后受影响的数据条数 |
| CII\_Database::select\(\) | 构造select查询条件 |
| CII\_Database::from\(\) | 构造from查询条件 |
| CII\_Database::where\(\) | 构造where查询条件 |
| CII\_Database::order\_by\(\) | 构造order\_by查询条件 |
| CII\_Database::limit\(\) | 构造limit查询条件 |
| CII\_Database::get\(\) | 组合查询条件，执行一条sql查询 |
| CII\_Database::insert\(\) | 插入数据 |
| CII\_Database::update\(\) | 更新数据 |
| CII\_Database::delete\(\) | 删除数据 |
| CII\_Database::last\_query\(\) | 返回最后一次查询语句 |
| CII\_Database::insert\_id\(\) | 返回新插入数据的id |
| CII\_Database::group\_start\(\) | 构造查询条件（ |
| CII\_Database::group\_end\(\) | 构造查询条件  ） |
| CII\_Database::or\_where\(\) | 构造where ... or ... 查询条件 |



