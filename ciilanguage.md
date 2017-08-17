# CII\_Lang

语言类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $language | Public | 语言列表 |
| $is\_loaded | Public | 已载入的语言 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Lang::\_\_construct\(\) | 构造函数 |
| CII\_Lang::load\(\) | 加载一种语言 |
| CII\_Lang::line\(\) | 获取一个词汇在当前语言下的翻译 |

#### \_\_construct\(\)

```
/**
* Class constructor
*
* @return    void
*/
public function __construct()
```

#### load\(\)

```
/**
* Load a language file
*
* @param    mixed     $langfile      Language file name
* @param    string    $idiom         Language name (english, etc.)
* @param    bool      $return        Whether to return the loaded array of translations
*
* @return    true|false|array    Array containing translations, if $return is set to TRUE
*/
public function load($langfile, $idiom = '', $is_return)
```

#### line\(\)



