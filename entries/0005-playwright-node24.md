# 0005 playwright 必须用 node 24

- 现象：node v18 启动 playwright-core 直接报错，截图脚本跑不起来。
- 根因：playwright-core 1.6x 要求 Node >= 20。
- 解法：用 /Users/xin/.nvm/versions/node/v24.22.2/bin/node 跑脚本；浏览器用 channel: "chrome" 复用本机 Chrome。
- 下次注意：先 node -v，别拿默认 node 跑前端工具链。
