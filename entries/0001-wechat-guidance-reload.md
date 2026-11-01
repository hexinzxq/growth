# 0001 微信渠道改 guidance 要重启才生效

- 现象：改完 /Users/xin/.dsh/integrations/dsh-weixin/workspaces.json 里的人设，聊天里完全没变化。
- 根因：workspaces.json 的 contextEnhancement 在启动时读进内存（BotWorkspaceStore 内部字段），进程不 watch 文件。
- 解法：改完重启 DSH，或在设置页保存一次（走 setContextEnhancement）触发重载。
- 下次注意：任何"改配置没反应"，先确认是不是热加载。
