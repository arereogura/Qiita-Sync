<!--
title:   numpy.sumのaxisは-1を指定した場合はどう言う意味？
tags:    Python,numpy
id:      fc8c3534d1ef7b7ac8e6
private: false
-->
`numpy.sum`関数において、`axis`パラメータに`-1`を指定すると、最後の次元に沿った和を計算します。

例えば、もし2次元配列（行列）を持っている場合、`axis=-1`は各行の要素の和を計算します。3次元配列の場合、それぞれの2次元スライスの各行の要素の和を計算します。このように、`axis=-1`は常に最後の次元に沿って和を取ります。

2次元配列の例：

```python
import numpy as np

arr = np.array([[1, 2], [3, 4]])
result = np.sum(arr, axis=-1)
print(result)
#[3, 7]
```

3次元配列の場合：

```python
arr = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
result = np.sum(arr, axis=-1)
print(result)
# [[3, 7],
#  [11, 15]]
```
この方法で、配列の形状が変わっても同じ次元に対して和を取るコードを書くことができます。


他にも色々比較してみます
```python
#3x2
arr = np.array([[1,2],[3,4],[5,6]])
result = np.sum(arr,axis=-1)
print(result)
#[ 3  7 11]

result = np.sum(arr,axis=1)
print(result)
#[ 3  7 11]

result = np.sum(arr,axis=0)
print(result)
#[ 9 12]
```