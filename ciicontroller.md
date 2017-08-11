# \*CII\_Controller 伪基类

伪基类，该类在PHP内部不存在，由 CII 内核在框架初始化时根据 URI 路由获取指定的控制器后，向控制器注入 CII\_Controller 伪基类的成员变量与成员方法，使得控制器像是继承了 CII\_Controller 类。





