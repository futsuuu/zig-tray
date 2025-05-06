# zig-tray

zig-tray is a library for creating tray applications. Supports tray and notifications.

## Features

- tray witch `.ico` support!
- left click callback support
- right click callback support
- sending notification and notification click callback support

## Supported platforms

 - [x] Windows
 - [ ] Linux
 - [ ] MacOS

## Installation

zig-tray uses Zig 0.14.0.

1. Add to `build.zig.zon`

```sh
# It is recommended to replace the following branch with commit id
zig fetch --save https://github.com/star-tek-mb/zig-tray/archive/master.tar.gz
# Of course, you can also use git+https to fetch this package!
```

2. Config `build.zig`

Add this:

```zig
// To standardize development, maybe you should use `lazyDependency()` instead of `dependency()`
// more info to see: https://ziglang.org/download/0.12.0/release-notes.html#toc-Lazy-Dependencies
const zig_tray = b.dependency("zig_tray", .{
    .target = target,
    .optimize = optimize,
});

// add module
exe_mod.addImport("zig-tray", zig_tray.module("tray"));
```

## Example

see folder `example`!

## Credits

https://github.com/zserge/tray - for initial C library
https://github.com/glfw/glfw/blob/master/src/win32_window.c#L102 - for icon creating from rgba
