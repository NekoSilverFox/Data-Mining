# Numpy

## Numpy 优势

### 内存风格

### 并行化（向量化）运算

### 底层是 C语言实现

## ndarry 属性

### 形状

### 类型

## 基本操作

### 两大方式

- ndarry.方法()
- numpy.函数名()

### 生成数组的方式

- 生成 0 或 1 的数组

	- np.ones(shape=, dtype=)
	- np.zeros(shape=, dtype=)

- 从现有数组中生成

	- 深拷贝

		- np.array(object=, dtype=)
		- np.copy(object)

	- 浅拷贝

		- np.asarray(object=, dtype=)

- 生成固定范围的数组

	- 等距生成指定数量-左闭右闭
np.linespace(start=, stop=, num=, endpoint=)
	- 等距生成指定步长-左闭右开
np.arange(start=, stop=, step=, dtype=)

- 生成随机数组
np.random

	- 均匀分布

		- np.random.uniform(low=, high=, size=)

	- 正态分布

		- 返回指定形状的标准正态分布数组
np.random.standard_normal(size=)
		- 返回指定均值和标准差的正态分布
np.random.normal(loc=, scale=, size=)

### 切片索引

- [起始值:结束值]

### 形状修改

- 返回新数组，不修改源数组
ndarray.reshape(shape=(col, row))

	- 可以只指定行或列，另一个指定为 -1；程序会自动计算值

- 直接修改该数组，不返回值
ndarray.resize()
- 转置：列变行，行变列
ndarry.T

### 类型修改

- ndarray.astype(type=)
- 序列化到本地
ndarray.tostring()

### 数组去重

- np.unique()

## 运算

### 逻辑运算

- 布尔索引
- 通用判断函数

	- 返回 True/False
np.all(布尔表达式)
	- 返回 True/False
np.any(布尔表达式)

- 三运运算符

	- 返回新的数组
np.where(布尔表达式, 布尔值为True设置的值, 布尔值为False设置的值)

- 符合逻辑运算符

	- np.logical_and(布尔表达式1, 2, ...)
	- np.logical_or(布尔表达式1, 2, ...)
	- np.logical_not(布尔表达式1, 2, ...)

### 统计运算

- 统计指标

	- ndarry.min(axis)
	- ndarry.max(axis)
	- 中位数
ndarry.median(axis)
	- 平均数
ndarry.mean(axis, dtype)
	- 标准差
ndarry.std(axis, dtype)
	- 方差
ndarry.var(axis, dtype)

- 返回最大/小值所在位置

	- ndarry.argmax(axis)
	- ndarry.argmin(axis)

### 数组与数的运算

- 直接用 ndarry [= | - | * | /] num
会作用于 ndarry 中的每一个数

### 数组间运算

- broadcast 广播机制

	- 对应维度的元素数量相同（维度等长）
	- 对应维度的元素数量有一个数组的是 1（shape）

### 矩阵运算

- 返回 Numpy 类型的矩阵
numpy.mat(列表形式的数据或 ndarry)
- 乘法

	- 矩阵1 * 矩阵2
	- np.matmul(矩阵1, 矩阵2)

		- 禁止矩阵与标量的乘法

	- np.dot(矩阵1, 矩阵2)
	- ndarry 不转换为矩阵的形式下进行矩阵运算：
数组1 @ 数组2

### 数组合并与分割

- 合并

	- 横向拼接
numpy.hstack(ndarry1, ndarry2 ...)
	- 竖向拼接
numpy.vstack(ndarry1, ndarry2 ...)
	- 按指定的 int 类型的 axis 轴拼接
numpy.concatenate((ndarry1, ndarry2 ...), axis=按哪个轴)

- 分割

	- Numpy.split(ndarry, 数或索引数组)

