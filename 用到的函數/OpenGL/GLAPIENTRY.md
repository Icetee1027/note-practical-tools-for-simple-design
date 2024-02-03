
----
`GLAPIENTRY` 是 [[OpenGL]] API 函数的调用约定修饰符，通常用于声明 [[OpenGL]] 函数的函数指针类型。在大多数情况下，它被定义为 `__stdcall` 或 `__cdecl`，这取决于编译器和平台。

具体来说，`GLAPIENTRY` 是一个宏，根据不同的编译器和平台，它会展开为相应的调用约定修饰符。在 Windows 平台上，它通常被定义为 `__stdcall`，而在其他平台上，可能会被定义为 `__cdecl`。

调用约定指定了函数调用的规则，包括参数传递方式、参数栈的清理方式等。在 [[OpenGL]] 中，`GLAPIENTRY` 通常用于修饰 [[OpenGL]] 函数的声明，以确保它们使用正确的调用约定。

例如，一个典型的 [[OpenGL]] 函数声明可能如下所示：
```c
void GLAPIENTRY glClearColor(GLfloat red, GLfloat green, GLfloat blue, GLfloat alpha);
```

在这个声明中，`GLAPIENTRY` 用于修饰函数，表示该函数遵循 OpenGL API 的调用约定。