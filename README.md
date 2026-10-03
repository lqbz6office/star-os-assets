# star-os-assets

**Star OS** —— 小天才 4100 / Z12 的 Magisk 定制模块,**在线版**的分发仓库。

## 我要装模块,该下哪个?

| 你要什么 | 下这个 |
|---|---|
| **在线版**(约 130 KB,刷入时自动去下载资源包) | 本仓库的 [`zz_star_os-1.3fix3-online.zip`](zz_star_os-1.3fix3-online.zip) |
| **离线全量版**(约 174 MB,不联网也能装) | 到 [Releases](../../releases) 页找 `zz_star_os-*-full.zip` |
| **资源包**本体(约 174 MB,在线版刷入时自动下载的那一份) | 同样在 [Releases](../../releases) 页 |

装法:把 zip 传到手表 → Magisk 应用 → 模块 → 从本地安装。

> ⚠ Release 里的 `star_os_assets-*.zip` 是**资源包**,不是模块,**不要直接刷它**。

## 本仓库里的文件是干什么的

| 文件 | 作用 |
|---|---|
| `update.json` | **模块更新清单**。模块 `module.prop` 里的 `updateJson=` 指向它,Magisk 应用据此在模块页显示「更新」按钮 |
| `changelog.md` | 更新说明。点「更新」时 Magisk 会显示它 |
| `zz_star_os-1.3fix3-online.zip` | 在线版模块本体。`update.json` 的 `zipUrl` 指向它 —— 走 OTA 更新的就是这一个 |
| `README.md` | 本文件 |

## 为什么都走 jsDelivr

国内直连 `raw.githubusercontent.com` 常年不通(实测 HTTP 000,15 秒超时),
所以模块里的 `updateJson` 和 `update.json` 里的 `zipUrl` 都指向
`https://cdn.jsdelivr.net/gh/lqbz6office/star-os-assets@main/<文件名>`,
内容与仓库里的文件**逐字节一致**。

> jsDelivr 对分支引用(`@main`)最长有约 12 小时缓存,刚发的新版本可能要等一会儿才在
> 更新检查里生效。文件名带版本号,所以新旧版本之间不会串。

## 说明

- 模块源码不在本仓库,这里只放分发用的文件。
- 更新由模块维护者发布,请不要直接改这里的文件 —— 改了会让 `update.json` 里的
  `versionCode` 与模块对不上,表现为"永远不提示更新"。
