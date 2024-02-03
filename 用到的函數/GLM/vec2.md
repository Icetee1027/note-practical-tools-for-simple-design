
----
`glm::vec2` 是 [[GLM]]（OpenGL Mathematics）库中的一种向量类型，用于表示二维向量。[[GLM]] 是一个 C++ 数学库，提供了许多用于图形学和游戏开发的数学功能，包括向量、矩阵、四元数、几何函数等。
### 特点和用途
- **表示二维向量**: `glm::vec2` 可以用于表示二维空间中的位置、方向或位移等。
- **点和向量运算**: 支持向量的加法、减法、乘法、除法等运算，以及点乘、叉乘等向量运算。
- **常见操作**: 可以进行向量长度计算、归一化、取反等常见操作。
### 常见操作
- **向量加法**: 使用 `+` 运算符进行向量加法。
- **向量减法**: 使用 `-` 运算符进行向量减法。
- **标量乘法**: 使用 `*` 运算符进行标量乘法。
- **标量除法**: 使用 `/` 运算符进行标量除法。
- **点乘**: 使用 `glm::dot` 函数进行点乘运算。
- **叉乘**: 使用 `glm::cross` 函数进行叉乘运算。
- **向量长度**: 使用 `glm::length` 函数计算向量长度。
- **向量归一化**: 使用 `glm::normalize` 函数将向量归一化。
### 示例代码
```cpp
#include <glm/glm.hpp>
glm::vec2 position(1.0f, 2.0f); // 初始化二维向量
glm::vec2 velocity(0.5f, -0.5f); // 初始化二维向量
glm::vec2 result = position + velocity; // 向量加法
float length = glm::length(result); // 计算向量长度
glm::vec2 direction = glm::normalize(result); // 归一化向量
float dotProduct = glm::dot(position, velocity); // 计算点乘
glm::vec2 crossProduct = glm::cross(glm::vec3(position, 0.0f), glm::vec3(velocity, 0.0f)); // 计算叉乘
```
### 相关链接
- [GLM 官方文档](https://glm.g-truc.net/)
- [GLM GitHub 仓库](https://github.com/g-truc/glm)
`glm::vec2` 提供了对二维向量的基本操作和常用功能，是图形学和游戏开发中常用的数学工具之一。