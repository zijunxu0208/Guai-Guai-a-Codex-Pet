# 乖乖 Cat Codex 宠物

乖乖 是一只基于我的宠物——乖乖，一只蓝眼睛重点色双色长毛猫，制作的 Codex 自定义宠物。

这个仓库提供的是一个可以直接安装的 Codex v2 宠物包。发布内容不包含原始猫咪照片、临时生成文件、本地缓存或失败实验版本。

![Bluebell 挥爪预览](previews/waving.gif)

## 快速安装

克隆或下载本仓库后，把宠物目录复制到 Codex 的宠物目录：

```bash
mkdir -p ~/.codex/pets
cp -R pets/bluebell-cat ~/.codex/pets/bluebell-cat
```

然后重启 Codex，或在支持热重载的 Codex 版本中重新加载宠物列表。

也可以直接运行安装脚本：

```bash
./install.sh
```

## 让 Codex Agent 帮你部署

如果你正在 Codex 里查看这个仓库，可以直接把下面这段话发给 Agent：

```text
请帮我部署这个 Codex 宠物。把仓库中的 pets/bluebell-cat 复制到 ~/.codex/pets/bluebell-cat，保留 pet.json 和 spritesheet-idle-waves.png。部署后检查 pet.json 是否指向 spritesheet-idle-waves.png，并提醒我重启 Codex 或重新加载宠物列表。不要修改宠物图片文件。
```

如果 Agent 因权限限制无法写入 `~/.codex/pets`，它应该请求你授权写入该目录；授权后再执行复制。

## 包内容

```text
pets/bluebell-cat/
  pet.json
  spritesheet-idle-waves.png
```

其中 `spritesheet-idle-waves.png` 是 Codex v2 宠物图集：

- 1536 x 2288 像素
- 8 列 x 11 行
- 单格尺寸 192 x 208 像素
- `spriteVersionNumber: 2`

## 动作说明

Codex 运行时负责决定不同状态播放哪一行动画。这个宠物包包含标准的 `waving` 和 `running` 动作行，但在当前本地 Codex 运行时中，鼠标悬停没有触发专门的挥爪行。

因此这个发布版本采用了一个实用处理：默认 idle 行使用挥爪帧构成，这样 Bluebell 在空闲时会实际挥爪。项目运行或 Agent 工作时，仍保留 Codex 可使用的 running 行。

## 预览

![运行预览](previews/running.gif)

完整动作表可以查看：[previews/contact-sheet.png](previews/contact-sheet.png)

视线方向预览可以查看：[previews/look-directions.png](previews/look-directions.png)

## 不包含的内容

本仓库不公开以下信息：

- 原始猫咪照片
- 私有本地路径
- 临时生成目录
- 失败或实验性的 drag-mix 版本
- Codex 本地缓存

## 许可证

宠物图像和包文件采用 Creative Commons Attribution-NonCommercial 4.0 International License 授权。详见 [LICENSE](LICENSE)。

你可以将本宠物用于个人部署、个人修改、非商业分享和非商业再创作。未经单独授权，不允许商业使用、商业再分发、付费打包，或用于商业产品和商业服务。

乖乖 是非官方自定义宠物，不是 Codex 或 OpenAI 官方资产。
