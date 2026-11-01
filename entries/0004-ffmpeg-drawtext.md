# 0004 ffmpeg 没编译 freetype，drawtext 用不了

- 现象：ffmpeg -vf drawtext 报 "No such filter: 'drawtext'"。
- 根因：brew 装的 ffmpeg 未带 freetype/libass 依赖。
- 解法：不在 ffmpeg 里画字。用 HTML+CSS 排版，playwright 逐帧截图，再 ffmpeg 只做拼接与音频。
- 下次注意：视频里的文字一律走 HTML 渲染，好看又好改。
