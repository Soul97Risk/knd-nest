# KND 的小窝

放 bundle 与 lua 的地方。不是工具、不是教程，就是一个存放点：按游戏归类，一个文件一条登记，随时能取、随时能核对。

## 目录

```
knd-nest/
├── bundles/          Unity 资源包 —— .bundle / .unity3d / .cab
│   └── <游戏代号>/
├── lua/              Lua 脚本 —— .lua / .luac / .bytes
│   └── <游戏代号>/
├── INDEX.md          清单：每个文件的来源、版本、日期、大小、SHA256
├── NOTICE.md         版权与使用边界
└── README.md         本文件
```

| 路径 | 说明 |
|---|---|
| [`bundles/`](bundles/) | 资源包。按 `bundles/<游戏代号>/` 存放，版本并存不覆盖，文件名带版本号 |
| [`lua/`](lua/) | 脚本。纯文本 `.lua` 走普通 git，`.luac` / `.bytes` 由 LFS 接管 |
| [`INDEX.md`](INDEX.md) | 落地即登记。没有 SHA256 的条目视为未完成 |
| [`NOTICE.md`](NOTICE.md) | 仓库未附 LICENSE，即保留所有权利；资源版权归原厂商 |

---

维护：[kndnb666](https://t.me/kndnb666)
