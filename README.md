# KND 的小窝

放 bundle 与 lua 的地方。不是工具、不是教程，就是一个存放点：按游戏归类，随时能取。

## 目录

```
knd-nest/
├── bundles/          Unity 资源包 —— .bundle / .unity3d / .cab
│   └── <游戏代号>/
├── lua/              Lua 脚本 —— .lua / .luac / .bytes
│   └── <游戏代号>/
└── README.md         本文件
```

| 路径 | 说明 |
|---|---|
| [`bundles/`](bundles/) | 资源包。按 `bundles/<游戏代号>/` 存放，版本并存不覆盖，文件名带版本号 |
| [`lua/`](lua/) | 脚本。纯文本 `.lua` 走普通 git，`.luac` / `.bytes` 由 LFS 接管 |

---

维护：[kndnb666](https://t.me/kndnb666)
