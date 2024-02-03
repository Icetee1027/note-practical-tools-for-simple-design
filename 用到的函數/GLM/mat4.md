
----
`glm::mat4` 是 [[GLM]]（OpenGL Mathematics）库中的一种矩阵类型，用于表示 4x4 矩阵。[[GLM]] 是一个 C++ 数学库，提供了许多用于图形学和游戏开发的数学功能，包括矩阵、向量、四元数、几何函数等。

### 特点和用途
- **表示变换**: `glm::mat4` 可以用于表示三维空间的变换，包括平移、旋转和缩放等。
- **表示投影**: 它还可以用于表示透视投影和正交投影，将三维空间中的物体投影到二维屏幕上。
- **矩阵乘法**: `glm::mat4` 支持矩阵乘法，可以实现多个变换的组合。

### 常见操作
- **矩阵乘法**: 使用 `*` 运算符或 `glm::multiply` 函数进行矩阵乘法。
- **矩阵转置**: 使用 `glm::transpose` 函数进行矩阵转置。
- **逆矩阵**: 使用 `glm::inverse` 函数求逆矩阵。

### 示例代码
```cpp
#include <glm/glm.hpp>
#include <glm/gtc/matrix_transform.hpp>

glm::mat4 model = glm::mat4(1.0f); // 初始化单位矩阵
model = glm::translate(model, glm::vec3(1.0f, 2.0f, 3.0f)); // 平移变换
model = glm::rotate(model, glm::radians(45.0f), glm::vec3(0.0f, 1.0f, 0.0f)); // 绕 Y 轴旋转 45 度
model = glm::scale(model, glm::vec3(2.0f, 2.0f, 2.0f)); // 缩放变换

glm::mat4 view = glm::lookAt(glm::vec3(0.0f, 0.0f, 3.0f), glm::vec3(0.0f, 0.0f, 0.0f), glm::vec3(0.0f, 1.0f, 0.0f)); // 视图矩阵
glm::mat4 projection = glm::perspective(glm::radians(45.0f), 800.0f / 600.0f, 0.1f, 100.0f); // 透视投影矩阵
```

### 相关链接
- [GLM 官方文档](https://glm.g-truc.net/)
- [GLM GitHub 仓库](https://github.com/g-truc/glm)

`glm::mat4` 提供了对矩阵的基本操作和常用功能，是图形学和游戏开发中常用的数学工具之一。