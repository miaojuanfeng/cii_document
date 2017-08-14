# CII\_Input

输入类。

#### Member Variables

| 无 |
| :---: |


#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Input::\_\_construct\(\) | 构造方法 |
| CII\_Input::post\(\) | 返回$\_POST数组 |
| CII\_Input::get\(\) | 返回$\_GET数组 |
| CII\_Input::post\_get\(\) | 获取提交的变量。先查找$\_POST数组，查找不到后再查找$\_GET数组 |
| CII\_Input::get\_post\(\) | 获取提交的变量。先查找$\_GET数组，查找不到后再查找$\_POST数组 |
| CII\_Input::num\_post\(\) | 返回$\_POST获取的数据个数 |
| CII\_Input::num\_get\(\) | 返回$\_GET获取的数据个数 |
| CII\_Input::server\(\) | 返回$\_SERVER数组 |
| CII\_Input::is\_post\(\) | 判断表单是否以$\_POST方式提交 |
| CII\_Input::is\_get\(\) | 判断表单是否以$\_GET方式提交 |
| CII\_Input::user\_agent\(\) | 返回客户端操作系统、浏览器等信息 |
| CII\_Input::method\(\) | 返回表单提交的方法，$\_POST或$\_GET |
| CII\_Input::ip\_address\(\) | 返回客户端IP地址 |


