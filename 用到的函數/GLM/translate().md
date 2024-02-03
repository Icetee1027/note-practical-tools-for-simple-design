
----
`glm::translate` 是 GLM（OpenGL Mathematics）库提供的一个函数，用于创建一个平移矩阵。它将指定的平移向量应用于一个 4x4 的矩阵，产生一个新的变换矩阵，该矩阵用于将对象沿指定方向移动。

### 函数原型
```cpp
glm::mat4 glm::translate(const glm::mat4& m, const glm::vec3& v);
```

### 参数
- `m`：一个 4x4 的矩阵，表示当前的变换矩阵。
- `v`：一个包含 x、y 和 z 分量的 3 维向量，表示要进行的平移量。

### 返回值
一个新的 4x4 变换矩阵，表示应用了平移变换后的结果。

### 示例用法
```cpp
glm::mat4 model = glm::mat4(1.0f); // 初始化单位矩阵
glm::vec3 translation = glm::vec3(1.0f, 0.0f, 0.0f); // 沿 x 轴平移 1 个单位
model = glm::translate(model, translation); // 将平移变换应用到模型矩阵上
```

以上示例代码演示了如何使用 `glm::translate` 函数在一个模型矩阵上进行平移变换，将模型沿着 x 轴移动了 1 个单位的距离。