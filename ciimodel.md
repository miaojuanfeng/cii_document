# \*CII\_Model 伪基类

伪基类，该类在PHP内部不存在，由 CII 内核在使用 CII\_Loader::model\(\) 加载指定的模型时，向模型注入 CII\_Model 伪基类的成员变量与成员方法，使得控制器像是继承了 CII\_Model 类。

