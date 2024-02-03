
----
`glm::scale` 是 GLM（OpenGL Mathematics）库提供的一个函数，用于创建一个缩放矩阵。它将指定的缩放因子应用于三个坐标轴，产生一个新的变换矩阵，该矩阵用于将对象在三个坐标轴上进行缩放。

### 函数原型
```cpp
glm::mat4 glm::scale(const glm::mat4& m, const glm::vec3& scale);
```

### 参数
- `m`：一个 4x4 的矩阵，表示当前的变换矩阵。
- `scale`：一个包含 x、y 和 z 分量的 3 维向量，表示在三个坐标轴上的缩放因子。

### 返回值
一个新的 4x4 变换矩阵，表示应用了缩放变换后的结果。

### 示例用法
```cpp
glm::mat4 model = glm::mat4(1.0f); // 初始化单位矩阵
glm::vec3 scale = glm::vec3(2.0f, 1.5f, 1.0f); // 分别在 x、y 和 z 轴上进行 2、1.5 和 1 倍的缩放
model = glm::scale(model, scale); // 将缩放变换应用到模型矩阵上
```

以上示例代码演示了如何使用 `glm::scale` 函数在一个模型矩阵上进行缩放变换，将模型在 x 轴上进行 2 倍缩放，在 y 轴上进行 1.5 倍缩放，在 z 轴上进行 1 倍缩放。