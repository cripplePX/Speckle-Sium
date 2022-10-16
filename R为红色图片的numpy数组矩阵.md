R为红色图片的numpy数组矩阵

G为绿色图片的numpy数组矩阵

B为蓝色图片的numpy数组矩阵



```python
# 光源比例配比
R = R * 6.5
G = G * 3.46
B = B * 1.99

# 636nm 520nm 449nm的三刺激值系数
X = 0.522 * R + 0.063 *G + 0.339 * B
Y = 0.208 * R + 0.71 * G + 0.036 * B
Z =           0.0782 * G + 1.772 * B
```



根据CIE 1976的公式计算u‘ 、v’：
$$
\begin{matrix}
{u^{'}~ = ~\frac{4x}{- 2x + 12y + 3}~ = ~\frac{4X}{X + 15Y + 3Z}} \\
{v^{'}~ = ~\frac{9y}{- 2x + 12y + 3}~ = ~\frac{9Y}{X + 15Y + 3Z}} \\
\end{matrix}
$$
即，得出u'、v'的矩阵，并另存为“npy_uu.npy”和“npy_vv.npy”

通过u'，v'的值进行瞄点，u'就是横坐标的值，v'就是纵坐标的值

tips：瞄点的方法就是使用matplotlib的库进行瞄点

