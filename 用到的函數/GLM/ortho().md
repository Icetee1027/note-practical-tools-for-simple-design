
----
`glm::ortho` 是 [[GLM]]（OpenGL Mathematics）库提供的一个函数，用于创建一个正交投影矩阵。正交投影是一种简单的投影方式，它将场景投影到一个长方体的平面上，使得在观察方向的任何位置，物体的大小都保持不变。

### 函数原型
```cpp
glm::mat4 glm::ortho(float left, float right, float bottom, float top, float nearVal, float farVal);
```

### 参数
- `left`：视景体左侧面的 x 轴坐标。
- `right`：视景体右侧面的 x 轴坐标。
- `bottom`：视景体底部面的 y 轴坐标。
- `top`：视景体顶部面的 y 轴坐标。
- `nearVal`：视景体近处面到视点的距离。
- `farVal`：视景体远处面到视点的距离。

### 返回值
一个新的 4x4 投影矩阵，表示使用正交投影方式的投影矩阵。

### 示例用法
```cpp
// 创建一个正交投影矩阵，视景体的左右侧面分别位于 x 轴 -1 和 1 的位置，
// 底部和顶部面分别位于 y 轴 -1 和 1 的位置，近处和远处面分别位于 z 轴 -1 和 1 的位置。
glm::mat4 projection = glm::ortho(-1.0f, 1.0f, -1.0f, 1.0f, -1.0f, 1.0f);
```

以上示例代码演示了如何使用 `glm::ortho` 函数创建一个正交投影矩阵，其中视景体的各个面分别位于指定的坐标轴位置。