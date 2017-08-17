# CII\_Config

配置类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $config | Public | 保存配置项的数组 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Config::\_\_construct\(\) | 构造函数 |
| CII\_Config::item\(\) | 获取一个配置项的值 |
| CII\_Config::slash\_item\(\) | 忘记了。。。 |
| CII\_Config::site\_url\(\) | 忘记了。。。 |
| CII\_Config::base\_url\(\) | 返回网页根路径 |
| CII\_Config::set\_item\(\) | 新增或更新一个配置项 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* Sets the $config data from the primary config.php file as a class variable.
*
* @return    void
*/
public function __construct()
```

#### item\(\)

```
/**
* Fetch a config item
*
* @param    string         $item     Config item name
* @param    string         $index    Index name
*
* @return   string|null    The configuration item or NULL if the item doesn't exist
*/
public function item($item, $index = '')
```

#### slash\_item\(\)

```
/**
* Fetch a config item with slash appended (if not empty)
*
* @param     string         $item    Config item name
*
* @return    string|null    The configuration item or NULL if the item doesn't exist
*/
public function slash_item($item)
```

#### site\_url\(\)

```
/**
* Site URL
*
* Returns base_url . index_page [. uri_string]
*
* @param     string|string[]    $uri    URI string or an array of segments
*
* @return    string
*/
public function site_url($uri = '')
```

#### base\_url\(\)

```
/**
* Base URL
*
* Returns base_url [. uri_string]
*
* @param     string|string[]    $uri    URI string or an array of segments
*
* @return    string
*/
public function base_url($uri = '')
```

#### set\_item\(\)



