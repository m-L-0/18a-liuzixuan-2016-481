1.`tf.cond`用来构建（双分支）选择结构，类似于Python中的`if...else...`语句。由于`tf.cond`本身只是一个函数，这会使得构建的选择结构看起来很不直观
#返回某一个分支的执行结果，两个分支返回的Tensor数量必须一样多但形状、类型等可以不一致
#用法：
tf.cond(
    pred,  # `shape=[]`的DT_BOOL类型的Tenor判断条件
    true_fn=None,  # `pred`为True时执行的函数
    false_fn=None,  # `pred`为False时执行的函数
    strict=False,  
    name=None)

2.#tf.maximum：用法tf.maximum(a,b),返回的是a,b之间的最大值
#tf.miniimum：用法tf.miiinimum(a,b),返回的是a,b之间的最小值

3.tf.while_loop(
    cond,  # 循环条件（一个函数或lambda表达式），为`True`则继续执行循环
    body,  # 循环执行的内容
    loop_vars,  # `cond`、`body`函数的参数列表
    shape_invariants=None,  # shape不变性
    parallel_iterations=10,  # 允许并行迭代的次数
    back_prop=True,  # 是否为此循环开启反向传播
    swap_memory=False,  # 是否允许`Tensor`在不同设备之间交换，允许的话，可以使得内存不足的设备将张量放在别的设备中
    name=None, 
    maximum_iterations=None, 
    return_same_structure=False)
`tf.while_loop`的第三个参数即`cond、body`函数的输入参数，可以输入常量、变量，但如果输入变量了，那么
这意味着使用了变量的初始值作为了输入张量，也就是说变量是没有真正输入进去的。
