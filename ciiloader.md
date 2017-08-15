# CII\_Loader

加载类。可在控制器中加载模型，视图，函数，类。并且会将加载的类实例化，注入到控制器中。

#### Member Variables

| 无 |
| :---: |


#### Public Methods

| Method | Description |
| :--- | :--- |
| CII\_Loader::\_\_construct | 构造函数 |
| CII\_Loader::\_\_get\(\) | 从控制器中获取成员变量 |
| CII\_Loader::view\(\) | 加载视图 |
| CII\_Loader::model\(\) | 加载模型 |
| CII\_Loader::helper\(\) | 加载函数 |
| CII\_Loader::library\(\) | 加载类 |
| CII\_Loader::database\(\) | 加载数据库 |
| CII\_Loader::language\(\) | 加载语言 |

#### \_\_construct\(\)

```
/**
* 构造函数
* Class constructor
*
* Runs the route mapping function.
*
* @return    void
*/
public function __construct()
```

#### \_\_get\(\)

```
/**
* 从控制器中获取成员变量
* Magic method 
*
* Fetch member variables from Controller if it's not defined in CII_Loader.
*
* @return    object
*/
public function __get()
```

#### view\(\)

```
/**
 * 加载视图
 * View Loader
 * 
 * Loads "view" files.
 *
 * @param    string    $view      View name
 * @param    array     $vars      An associative array of data, to be extracted for use in the view
 * @param    bool      $return    Whether to return the view output, or leave it to the Output class
 *
 * @return    object|string
 */
public function view($view, $vars = array(), $return = FALSE)
```

#### model\(\)

```
/**
 * 加载并实例化模型
 * Model Loader
 *
 * Loads and instantiates models.
 *
 * @param    string    $model    Model name
 * @param    string    $name     An optional object name to assign to
 *
 * @return   object
*/
public function model($model, $name = '')
```

#### helper\(\)

```
/**
* 加载函数
* Helper Loader
*
* @param     string|string[]    $helpers    Helper name(s)
*
* @return    object
*/
public function helper($helpers)
```

#### library\(\)

```
/**
* 加载并实例化类
* Library Loader
*
* Loads and instantiates libraries.
* Designed to be called from application controllers.
*
* @param    string    $library        Library name
* @param    array     $params         Optional parameters to pass to the library class constructor
* @param    string    $object_name    An optional object name to assign to
*
* @return   object
*/
public function library($library, $params = NULL, $object_name = NULL)
```

#### database\(\)

```
/**
* 加载并实例化数据库类
* Database Loader
*
* @return   object
*/
public function database()
```

#### language\(\)

```
//未实现
```



