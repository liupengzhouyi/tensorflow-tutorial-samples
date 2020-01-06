# CNN实现手写数字识别

## 准备原材料

-   输入张量 28 * 28 = 784个像素的图片一维向量
    
    -   self.x = tf.placeholder(tf.float32, [None, 784])
        
-   标签值，即图像对应的结果，如果对应数字是8，则对应label是 [0,0,0,0,0,0,0,0,1,0]
    
    -   self.label = tf.placeholder(tf.float32, [None, 10])
        

## 初始化

-   权重，初始化全 0
    
    -   `self.w = tf.Variable(tf.zeros([784, 10]))`
        

-   偏置 ， 初始化全 0
    
    -   `self.b = tf.Variable(tf.zeros([10]))`
        

## 输出

-   计算格式
    
    -   y = softmax(X * w + b)
        
-   `y = tf.nn.softmax(tf.matmul(x, w) + b)`