# knd 的小窝

放 bundle 与 lua 的地方。不是工具、不是教程，就是一个存放点。

---

## 目录

| 路径 | 放什么 |
|---|---|
| [`bundles/`](bundles/) | Unity 资源包：`.bundle` / `.unity3d` / `.cab` |
| [`lua/`](lua/) | Lua 脚本：`.lua` / `.luac` / `.bytes`（加密或编译后的变体） |
| [`INDEX.md`](INDEX.md) | 清单。每个文件一条：名字、来源、版本、日期、大小、SHA256 |

根目录只放这几个说明文件。资产一律进上面两个目录，不堆在根上。

---

## 命名规范

```
<游戏代号>-<资源名>-<版本或日期>.<扩展名>
```

```
saman-weapon-skin-v2.3.1.bundle
golddash-ui-config-20261022.lua
```

硬性要求只有一条：**不要出现空格、`#`、`?`、`%`、中文标点**。这些字符在 URL、`curl`、
shell 里都要转义，坑的来源全是它们。

子目录按 `<游戏代号>/` 分，同一游戏的东西别散在两层里。

---

## 大文件怎么走

GitHub 对单文件有硬限制，超了推不上去（不只是慢）：

| 体积 | 走法 |
|---|---|
| ≤ 50 MB | 直接提交。`*.bundle` / `*.unity3d` / `*.bytes` / `*.7z` / `*.zip` 由 `.gitattributes` 自动交给 Git LFS |
| 50 – 100 MB | 同上，但已经接近上限，一次别推太多 |
| > 100 MB | **推不上去**。走 Releases 附件（单文件上限 2 GB），仓库里只放下载链接与 SHA256 |
| 单次 push 累计 > 2 GB | 拆成多次推 |

LFS 免费额度是 1 GB 存储 + 1 GB 月流量。存大包之前先算一下，不够就走 Releases ——
Releases 的附件流量不计入 LFS 额度。

---

## 下载

网页上点文件 → Download，拿到的是真文件，不需要装任何东西。

`git clone` 就不一样了：没装 Git LFS 的话，LFS 文件只会下来一个一百多字节的指针文本。

```bash
git lfs install          # 只需一次
git clone https://github.com/Soul97Risk/knd-nest.git
```

已经 clone 过才发现是指针：

```bash
git lfs pull
```

---

## 校验

```bash
sha256sum FILE                       # Linux
certutil -hashfile FILE SHA256       # Windows
```

结果记进 [INDEX.md](INDEX.md)。一个文件一条，别嫌麻烦 —— 这些文件大多是二进制，
没有校验值就没法判断手里的版本和仓库里的是不是同一个。

---

## 版权

见 [NOTICE.md](NOTICE.md)。

一句话：**仓库未附 LICENSE，即保留所有权利**。这里的游戏资源版权归各自发行商，
只做个人备份与技术研究。要用请找权利人。

---

维护：[kndnb666](https://t.me/kndnb666)
