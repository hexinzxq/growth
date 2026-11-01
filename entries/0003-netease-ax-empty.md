# 0003 网易云界面点不动：AX 树是空的

- 现象：osascript 报 -1719 / 点不到按钮，读窗口元素数为 0。
- 根因：网易云是自绘界面，不暴露 Accessibility 树。
- 解法：screencapture 截图 → 按 2 倍像素换算逻辑坐标 → /opt/homebrew/bin/cliclick 点（brew install cliclick）。
- 下次注意：桌面 App 自动化先探测 AX 是否有元素，没有就走"截图 + 坐标"这条。
