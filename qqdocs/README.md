# 企鹅文档重放

用到的工具: [mkcert](https://github.com/FiloSottile/mkcert), [caddy 服务器](https://github.com/caddyserver/caddy).

需要信任 mkcert CA, 给 caddy 赋予 80、443 端口权限.

1. 从 HAR 包中提取 `/dop-api/get/sheet`, 保存为 `challenge.json`.
2. 执行 `mkcert docs.qq.com`, 生成自签名证书, 保存为 `docs.qq.com.pem`、`docs.qq.com-key.pem`.
3. 修改 hosts, 添加 `127.0.0.1 docs.qq.com`.
4. 保存 [caddy 配置文件](./Caddyfile), 执行 `caddy start`, 启动服务器.
