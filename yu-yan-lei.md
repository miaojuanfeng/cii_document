# 语言类

语言类提供了一些方法用于获取语言文件和不同语言的文本来实现国际化。

在你的 CII 目录，有一个 language 子目录， 它用于存放一系列的语言文件。你可以创建属于你自己的语言文件，用于提供应用程序的错误消息和其他消息。你另加的消息应该放在 `language/` 目录下，每种不同的语言都有相应的一个子目录（例如， `english` 或者 `chinese`）。

每个语言都应该有它自己的目录，例如，英语语言文件位于：`language/english` ，中文语言文件位于：`language/chinese`。

#### 1. 处理多语言

如果你想让你的应用程序支持多语言，你就需要在 language/ 目录下提供不同语言的文件， 然后在 `config/config.php` 配置文件中指定默认语言。

语言文件名需要加上 `_lang` ，语言文件夹的例子：

```
language/
  english/
      error_messages_lang.php
  chinese/
      ...
      email_lang.php
      error_messages_lang.php
      form_validation_lang.php
      ...
```

#### 2. 切换语言

你应该将你正在使用的语言保存到一个会话变量中。

```
$idiom = $this->session->get_userdata('language');
$this->lang->load('error_messages', $idiom);
$oops = $this->lang->line('message_key');
```

#### 3. 国际化

CII 的语言类给你的应用程序提供了一种简单轻便的方式来实现多语言， 它并不是通常我们所说的 国际化与本地化 的完整实现。

我们可以给每一种语言一个别名，一个更通用的名字，而不是使用诸如 "en"、 "en-US"、"en-CA-x-ca" 这种国际标准的缩写名字。当然，你完全可以在你的程序中使用国际标准的缩写名字。

#### 4. 使用语言类

* 创建语言文件：

语言文件的命名可以任意，例如，你想创建一个包含错误消息的文件， 你可以把它命名为：`error_lang.php` 。

在此文件中，你可以在每行把一个字符串赋值给名为 `$lang` 的数组，例如:

```
$lang['language_key'] = 'The actual message to be shown';
```

在每个文件中使用一个通用的前缀来避免和其他文件中的相似名称冲突是个好方法。 例如，如果你在创建错误消息你可以使用 `error_` 前缀。

```
$lang['error_email_missing'] = 'You must submit an email address';
$lang['error_url_missing'] = 'You must submit a URL';
$lang['error_username_missing'] = 'You must submit a username';
```

* 加载语言文件：

在使用语言文件之前，你必须先加载它。可以使用下面的代码:

```
$this->lang->load('filename', 'language');
```

其中 `filename` 是你要加载的语言文件名，`language` 是要加载哪种语言（比如，英语）。如果没有第二个参数，将会使用 `config/config.php` 中设置的默认语言。

你也可以通过传一个语言文件的数组给第一个参数来同时加载多个语言文件。

```
$this->lang->load(array('filename1', 'filename2'), 'chinese');
```

`language` 参数只能包含字母。

* 读取语言文本：

当你的语言文件已经加载，你就可以通过下面的方法来访问任何一行语言文本:

```
$this->lang->line('language_key');
```

其中 `language_key` 参数是你想显示的文本行所对应的数组的键名。

该方法只是简单的返回文本行，而不是显示出它。

* 返回语言文本：

如果需要返回语言文本而不是加载它，使用第三个参数 `is_return`，将返回读取的语言文本：

```
$lang = $this->lang->load(array('filename1', 'filename2'), 'chinese', 1);
```

变量 $lang 将会是包含了语言文本的数组。

* 自动加载语言文件：

如果你发现你需要在整个应用程序中使用某个语言文件，你可以让 CII 在系统初始化的时候自动加载该语言文件。 可以打开 `config/autoload.php` 文件，把语言放在 `autoload` 数组中。

