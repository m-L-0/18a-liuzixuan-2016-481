作业-1总结：
2-图与会话：
tf.Session()——创建会话操作
除可用作业中的方法之外，还可用如下方法创建会话：例：
add = tf.add(3,5)
with tf.Session() as sess:
	print(sess.run(add))
    
#注意加减乘除的运算与普通运算的区别，在此运算的对象需要满足类型匹配，即参与运算的对象需要有相同的数据类型
#在TensorFlow中API的基本用法，均有name参数，如tf.add(x,name=none)，name为操作的名称，一般可省略

3-图的边与节点：
#切片
tf.slice(input,begin,size,name=none)
#拆分
tf.split(value, num_or_size_splits, axis=0, num=None, name='split')

4-常量、变量、占位符
#构建二元线性回归模型
tf.Variable(value,neme=none)#定义变量
tf.placeholder('type')#占位符，参数为类型
随机生成1000个点，围绕在y=0.1x+0.3的直线周围