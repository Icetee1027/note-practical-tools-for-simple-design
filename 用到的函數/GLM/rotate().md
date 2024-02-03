
----
`glm::rotate` 是 GLM（OpenGL Mathematics）库提供的一个函数，用于创建一个旋转矩阵。它将指定的旋转角度绕指定的轴进行旋转，产生一个新的变换矩阵，该矩阵用于将对象绕指定轴旋转。

### 函数原型
```cpp
glm::mat4 glm::rotate(const glm::mat4& m, float angle, const glm::vec3& axis);
```

### 参数
- `m`：一个 4x4 的矩阵，表示当前的变换矩阵。
- `angle`：一个浮点数，表示旋转角度（以弧度为单位）。
- `axis`：一个包含 x、y 和 z 分量的 3 维向量，表示旋转轴。

### 返回值
一个新的 4x4 变换矩阵，表示应用了旋转变换后的结果。

### 示例用法
```cpp
glm::mat4 model = glm::mat4(1.0f); // 初始化单位矩阵
float angle = glm::radians(90.0f); // 将角度转换为弧度，这里表示绕 y 轴旋转 90 度
glm::vec3 axis = glm::vec3(0.0f, 1.0f, 0.0f); // y 轴作为旋转轴
model = glm::rotate(model, angle, axis); // 将旋转变换应用到模型矩阵上
```

以上示例代码演示了如何使用 `glm::rotate` 函数在一个模型矩阵上进行旋转变换，将模型绕着 y 轴旋转了 90 度。