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
| CII\_Lang::load\(\) | 加载语言文件 |
| CII\_Lang::line\(\) | 获取一个词汇在当前语言下的翻译 |

#### \_\_construct\(\)

```
/**
* 构造函数
* Class constructor
*
* @return    void
*/
public function __construct()
```

#### load\(\)

```
/**
* 加载语言文件
* Load a language file
*
* @param    mixed     $langfile      Language file name
* @param    string    $idiom         Language name (english, etc.)
* @param    bool      $return        Whether to return the loaded array of translations
*
* @return   true|false|array         Array containing translations, if $return is set to TRUE
*/
public function load($langfile, $idiom = '', $is_return)
```

#### line\(\)

```
/**
* 获取一个词汇在当前语言下的翻译
* Language line
*
* Fetches a single line of text from the language array
*
* @param     string    $line        Language line key
*
* @return    string    Translation
*/
public function line($line)
```



