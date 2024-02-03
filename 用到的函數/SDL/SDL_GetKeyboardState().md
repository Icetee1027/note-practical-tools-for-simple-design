
----
`SDL_GetKeyboardState` 是一个 SDL 函数，用于获取当前键盘的键位状态。它返回一个指向包含当前键盘状态的数组的指针，数组的每个元素对应一个键位，键位的状态由一个整数表示。

### 函数原型
```c
const Uint8* SDL_GetKeyboardState(int* numkeys);
```

### 参数
- `numkeys`：一个指向整数的指针，用于存储键盘上键位的数量。

### 返回值
- 返回一个 `Uint8` 类型的指针，指向一个包含当前键盘状态的数组。数组中的每个元素都是一个 `Uint8` 类型的值，表示对应键位的状态。如果键位处于按下状态，则相应的数组元素的值为非零；如果键位未被按下，则值为零。

### 示例用法
```c
int numkeys;
const Uint8* keystate = SDL_GetKeyboardState(&numkeys);
if (keystate[SDL_SCANCODE_W]) {
    // 如果 W 键被按下
    // 执行某些操作
}
```

在这个示例中，`SDL_GetKeyboardState` 函数被用来获取当前键盘的状态，然后通过检查返回的数组中特定键位的状态来执行相应的操作。