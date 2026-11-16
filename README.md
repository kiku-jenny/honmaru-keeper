# honmaru-keeper（部署用）

刀剑乱舞管家的**部署仓库**：只放 `index.html` 和 `sw.js` 两个文件，供 Cloudflare Pages 直接发布。

- 源码与完整历史在 [kiku-jenny/toukenranbu](https://github.com/kiku-jenny/toukenranbu)
- 这个仓库不放预览图（那边有 30 MB 的截图），所以每次部署只上传约 0.5 MB

## Cloudflare Pages 设置

| 项 | 值 |
|---|---|
| Framework preset | None |
| Build command | 留空 |
| Build output directory | `/` |

页面是纯静态单文件，没有构建步骤，CF 直接把根目录当产物发布。

## 发布新版本

在源码仓库改完 `index.html` 后，同步到这边（两边内容必须一致，否则两个网址会显示不同版本）：

```bash
cp index.html sw.js <这个仓库>/
git commit -am "V2.xx"
git push
```

推送后 Cloudflare Pages 会自动重新部署，约 30 秒生效。
