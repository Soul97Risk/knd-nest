# lua/

Lua 脚本。`.lua` 是纯文本，`.luac` 是字节码，`.bytes` 是加密或混淆后的容器 —— 三种都放这里。

## 放法

```
lua/
└── <游戏代号>/
    ├── ui-config.lua
    ├── battle-20261022.lua
    └── notes.md
```

- 一层游戏代号目录
- 纯文本 `.lua` 走普通 git，能看 diff，改动可追溯
- `.luac` / `.bytes` 二进制，由 `.gitattributes` 自动交给 Git LFS

## 写进 notes.md 的内容

| 项 | 为什么重要 |
|---|---|
| 加密方式 | `XOR 0xC0` / AES-CBC / 无 —— 复现的第一步就是这个 |
| 对应的游戏版本 | 同一个文件名在不同版本里内容完全不同 |
| 解包/还原命令 | 下次拿到新版本时能直接跑，不用重新摸 |
| opcode 表来源 | 若是 Lua 5.4 改过的 opcode，记下来源 |

`.bytes` 的原文件与解密后的 `.lua` 可以并存，前者放本目录、后缀标注 `-raw`，后者标 `-dec`。

## 登记

同 `bundles/`：放进来的同时补 [INDEX.md](../INDEX.md)。
