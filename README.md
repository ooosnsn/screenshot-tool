# 截图工具（便携版）

一个简单的 Windows 桌面截图工具，能截图、做标记就行，不加多余功能。

## 下载

直接下载 `截图工具.exe`，双击就能用，不用安装，不用装 Python。

## 用法

1. 按 **F1** 或点「开始截图」，拖动鼠标框选区域，松开进入标记。
2. 标记工具：矩形、椭圆、箭头、直线、画笔、文字，红黄绿蓝黑五种颜色。
3. 画好的标记可以直接用鼠标点中拖动，换个位置。
4. 直线拖得接近横平时会自动变直，接近竖平时会自动变竖直，斜着拖就保持斜线。
5. **Ctrl+S** 保存成图片，**Ctrl+C** 复制到剪贴板，去微信、Word 里直接粘贴。
6. **Ctrl+Z** 撤销，**Delete** 删除选中的标记，**Esc** 取消。

## 版本

- v1（2026-11-25）：定版。

## 源码

源码在 `src/` 里（C + Win32），用 mingw-w64 交叉编译：

```bat
windres resource.rc -O coff -o resource.res
x86_64-w64-mingw32-gcc -O2 -mwindows -municode -finput-charset=UTF-8 -o "截图工具.exe" main.c resource.res -lgdi32 -luser32 -lcomdlg32 -lcomctl32 -lm
```
