# CII\_Loader

加载类。可在控制器中加载模型，视图，函数，类。并且会将加载的类实例化，注入到控制器中。

#### Member Variables

| 无 |
| :---: |


#### Public Methods

| Method | Description |
| :--- | :--- |
| CII\_Loader::\_\_construct | 构造函数 |
| CII\_Loader::view\(\) | 加载视图 |
| CII\_Loader::model\(\) | 加载模型 |
| CII\_Loader::helper\(\) | 加载函数 |
| CII\_Loader::library\(\) | 加载类 |
| CII\_Loader::database\(\) | 加载数据库 |
| CII\_loader::language\(\) | 加载语言 |

#### view\(\)

```
/*
 * 加载视图
 * View Loader
 *
 * Loads "view" files.
 *
 * @param    string   $view    View name
 * @param    array    $vars    An associative array of data, to be extracted for use in the view
 * @param    bool     $return  Whether to return the view output
 *                or leave it to the Output class
 * @return    object|string
 */
public function view($view, $vars = array(), $return = FALSE)
```



