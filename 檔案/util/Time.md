- [[SDL_GetPerformanceCounter()]]

----
`Util::Time` 类是一个用于管理时间相关功能的单例类，它提供了用于获取时间信息的静态成员函数和静态成员变量。让我们更详细地了解它的功能：

- `GetDeltaTime()` 静态成员函数：用于获取当前帧与上一帧之间的时间差，以秒为单位表示。这个时间差通常被用来计算游戏中的动画、物理效果等与时间相关的变化。

- `Update()` 静态成员函数：用于更新时间相关的参数。在游戏循环中调用这个函数，它会更新当前时间和上一个时间的值，从而计算帧之间的时间差。

- `s_Now` 静态成员变量：存储当前时间的时间戳。

- `s_Last` 静态成员变量：存储上一个时间的时间戳。

- `s_DeltaTime` 静态成员变量：存储当前帧与上一帧之间的时间差，以秒为单位。

`Util::Time` 类被设计为一个单例类，意味着在程序运行期间只会有一个实例存在。开发者不需要手动创建 `Time` 对象，而是通过调用其静态成员函数来访问时间相关的功能。这个类提供了一种方便的方式来管理游戏中的时间信息，包括帧率控制、动画效果和物理模拟等方面的计算。