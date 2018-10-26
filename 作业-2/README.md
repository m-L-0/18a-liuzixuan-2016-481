作业总结：
#name_scope的作用：
#1>解决功能近似的节点name可能命名重复的问题
#2>为其作用域中的节点的name添加一个或多个前缀，并使用这些前缀作为划分内部与外部op范围的标记，同时在TensorFlow可
    #视化时可以作为一个整体出现
#3>name_scope可以通过划分操作范围来组织图结构，并能服务于可视化

#name_scope可以给Op的name加前缀，但不包括tf.get_variable()创建的变量

#variable_scope的作用：
#1>主要用于管理变量作用域以及与变量相关的操作
#2>variable_scope也可以像name_scope一样用来给不同操作区域划分范围（添加name前缀）
#3>功能更为丰富，最重要的是可以与tf.get_variable()等配合使用完成对变量的重复使用

#相同点：
#1>都可以用来给不同操作区域划分范围（添加name前缀）
#2>在运行时均可返回一个上下文管理器

#不同点：
#1>name_scope不能给tf.get_variable()创建的变量加前缀，而variabel_scope可以与tf.get_variable()等配合使用
    #完成对变量的重复使用
#2>variable_scope包含了name_scope的全部功能，即在variable_scope下也可以给Op与Tensor加上name_scope
#3>变量作用域是可以嵌套使用的