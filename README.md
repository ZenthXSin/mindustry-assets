# Mindustry Assets

Mindustry v159.5 的 `core/assets/` 资源文件打包为独立 Maven artifact。

供 `mindustry-mod-validator-full` 使用——完整客户端需要这些资源（shaders、sprites、fonts 等）才能初始化。

## 包含内容

- `shaders/` — 33 个 shader 文件（.vert / .frag）
- `sprites/` — 游戏贴图
- `fonts/` — 字体文件
- `bundles/` — 本地化文本
- `sounds/` — 音效
- `music/` — 音乐
- `cursors/` — 光标图片
- `icons/` — 图标
- 其他（maps、planets、scripts 等）

总大小约 60MB。

## 用法

```groovy
dependencies {
    implementation 'com.github.ZenthXSin:mindustry-assets:1.0.0'
}
```

## 来源

Mindustry v159.5 源码树的 `core/assets/` 目录。
