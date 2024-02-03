[SDL_Event (libsdl.org)](https://www.libsdl.org/release/SDL-1.2.15/docs/html/sdlevent.html)

---
`SDL_Event` 是 SDL 库中用于表示事件的数据结构。SDL 库允许程序捕获、处理各种类型的事件，包括键盘事件、鼠标事件、窗口事件等。`SDL_Event` 结构体用于存储这些事件的信息，开发者可以通过查询 `SDL_Event` 结构体的成员来获取事件的类型和相关数据。

`SDL_Event` 结构体定义如下：(參考)

```c
typedef union SDL_Event {
    Uint32 type;                    /* Event type, shared with all events */
    SDL_CommonEvent common;         /* Common event data */
    SDL_WindowEvent window;         /* Window event data */
    SDL_KeyboardEvent key;          /* Keyboard event data */
    SDL_TextEditingEvent edit;      /* Text editing event data */
    SDL_TextInputEvent text;        /* Text input event data */
    SDL_MouseMotionEvent motion;    /* Mouse motion event data */
    SDL_MouseButtonEvent button;    /* Mouse button event data */
    SDL_MouseWheelEvent wheel;      /* Mouse wheel event data */
    SDL_JoyAxisEvent jaxis;         /* Joystick axis event data */
    SDL_JoyBallEvent jball;         /* Joystick ball event data */
    SDL_JoyHatEvent jhat;           /* Joystick hat event data */
    SDL_JoyButtonEvent jbutton;     /* Joystick button event data */
    SDL_JoyDeviceEvent jdevice;     /* Joystick device change event data */
    SDL_ControllerAxisEvent caxis;  /* Game controller axis event data */
    SDL_ControllerButtonEvent cbutton; /* Game controller button event data */
    SDL_ControllerDeviceEvent cdevice; /* Game controller device event data */
    SDL_AudioDeviceEvent adevice;   /* Audio device event data */
    SDL_SensorEvent sensor;         /* Sensor event data */
    SDL_QuitEvent quit;             /* Quit request event data */
    SDL_UserEvent user;             /* User event data */
    SDL_SysWMEvent syswm;           /* System dependent window event data */
    SDL_TouchFingerEvent tfinger;   /* Touch finger event data */
    SDL_MultiGestureEvent mgesture; /* Gesture event data */
    SDL_DollarGestureEvent dgesture; /* Gesture event data */
    SDL_DropEvent drop;             /* Drag and drop event data */
    Uint8 padding2[56];
} SDL_Event;
```

`SDL_Event` 结构体中的 `type` 成员表示事件的类型，其它成员根据事件类型的不同而有所不同。开发者可以通过查询 `type` 成员来确定事件的类型，然后根据具体的事件类型来访问相应的成员，获取事件的详细信息。

使用 `SDL_PollEvent()` 函数可以从事件队列中获取事件，`SDL_WaitEvent()` 函数可以等待并获取一个事件。一旦获取到事件，开发者就可以通过查询 `SDL_Event` 结构体的成员来获取事件的类型和相关数据，然后进行相应的处理。

`SDL_Event` 结构体是 SDL 库中事件处理的核心数据结构，通过它，开发者可以实现对各种类型事件的捕获、处理和响应。