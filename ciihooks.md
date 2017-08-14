# CII\_Hooks

钩子类。

#### Member Variables

| Name | Access | Description |
| :--- | :--- | :--- |
| $enabled | Public | 是否启用钩子 |
| $hooks | Public | 定义的钩子数组 |
| $objects | Public | 钩子类实例化对象数组 |
| $\_in\_progress | Protected | 防止死循环调用 |

#### Member Methods

| Method | Description |
| :--- | :--- |
| CII\_Hooks::\_\_construct\(\) | 构造函数 |
| CII\_Hooks::call\_hook\(\) | 调用钩子 |



