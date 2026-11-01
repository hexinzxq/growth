# 0007 B 站投稿手写 upos 一直 403

- 现象：preupload 通过，PUT 到 upos 回 403；换 auth、加 Origin/Referer、加 put_query 都不行。
- 根因：upos 的签名与路径、请求头强绑定，手写容易错；不同 CDN 节点行为也不一致。
- 解法：用 bilibili-api-python（video_uploader.VideoUploaderPage + VideoMeta + Credential），一次通过，BV1EKxp6ZEWn。
- 下次注意：平台上传别造轮子，用成熟库；403 先怀疑签名绑定而不是权限。
