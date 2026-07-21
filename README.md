# Mindustry Assets

Mindustry 的完整资源文件打包为独立 artifact，供 `mindustry-mod-validator-full` 使用。

完整客户端初始化需要这些资源（shaders、sprites.aatls、fonts 等），而 JitPack 构建的 `mindustry-core` jar 不包含 `assets/` 目录，因此需要独立分发。

## 包含内容

| 目录 | 内容 | 来源 |
|------|------|------|
| `shaders/` | 33 个 shader 文件（.vert / .frag） | Mindustry v159.7 release jar |
| `sprites/` | 贴图打包文件（sprites.aatls + sprites.png） | Mindustry v159.7 release jar |
| `sprites/fallback/` | 低分辨率贴图（2048x2048 fallback） | Mindustry v159.7 release jar |
| `fonts/` | 字体文件 | Mindustry v159.7 release jar |
| `bundles/` | 本地化文本（bundle_*.properties） | Mindustry v159.7 release jar |
| `sounds/` | 音效文件（.ogg） | Mindustry v159.7 release jar |
| `music/` | 音乐文件（.ogg） | Mindustry v159.7 release jar |
| `cursors/` | 光标图片 | Mindustry v159.7 release jar |
| `icons/` | 图标 | Mindustry v159.7 release jar |
| `maps/` | 地图数据 | Mindustry v159.7 release jar |
| `planets/` | 星球数据 | Mindustry v159.7 release jar |
| `scripts/` | JS 脚本 | Mindustry v159.7 release jar |
| `vfxshaders/` | VFX shader 文件 | Mindustry v159.7 release jar |

总大小约 53MB。

## 为什么需要独立分发

- JitPack 构建的 `mindustry-core` jar **不包含** `assets/` 目录
- 源码树的 `core/assets/` 只有原始 PNG，没有构建生成的 `.aatls` 打包文件
- 完整客户端（`ClientLauncher`）初始化时通过 `Core.files.internal()` 从 classpath 加载这些资源

## 用法

```groovy
dependencies {
    implementation 'com.github.ZenthXSin:mindustry-assets:1.0.0'
}
```

所有文件在 jar 根路径，`Core.files.internal("shaders/mesh.vert")` 等调用自动解析。

## 构建

```bash
./gradlew jar
```

## 来源

[Mindustry v159.7 release jar](https://github.com/Anuken/Mindustry/releases/download/v159.7/Mindustry.jar) 的 `assets/` 目录。

## License

与 Mindustry 相同（GPLv3）
