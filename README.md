# 爱弥斯 · Aimisi Codex Pet

非官方、个人定制的 Codex 桌面宠物。当前发布包已升级至 v2，包含 9 个标准动作状态和 16 个注视方向。

![待机](previews/idle.gif)
![向右移动](previews/running-right.gif)
![挥手](previews/waving.gif)

## 安装

先备份已有的 `~/.codex/pets/aimisi` 文件夹，再将本仓库的 `pets/aimisi` 文件夹复制到 Codex 的 pets 目录。已有安装的用户也使用同一包更新。

```powershell
$destination = Join-Path $env:USERPROFILE '.codex\pets\aimisi'
if (Test-Path -LiteralPath $destination) {
    $backup = "$destination-backup-$(Get-Date -Format 'yyyyMMdd-HHmmss')"
    Copy-Item -LiteralPath $destination -Destination $backup -Recurse
}
Copy-Item -LiteralPath '.\pets\aimisi' -Destination (Join-Path $env:USERPROFILE '.codex\pets') -Recurse -Force
```

重新打开宠物选择器并选择「爱弥斯」。如果仍显示旧图像，可重新打开应用。发布检查验证了文件和逐帧图像；未声称验证所有应用内动作触发器。

## 当前版本

- `spriteVersionNumber: 2`
- 8 列 × 11 行，每格 192 × 208，总图 1536 × 2288，WebP 透明通道。
- 标准状态：待机、向右移动、向左移动、挥手、跳跃、受挫、等待输入、执行任务、检查结果。
- 16 向注视：以向上为 000°，顺时针每隔 22.5°；不是人物全身旋转。
- 左右移动分别制作，保留蓝色发夹的解剖侧别；待机更安静，受挫动作含恢复过程。

当前安装包与 2026-10-08 核验的本地已安装原装 v2 完全一致。校验信息见 [发布检查](qa/release-summary.json)，完整图集与方向图见 [动作总览](previews/contact-sheet.png)、[注视方向](previews/look-directions.png)。

## 换装进度

运动装、居家装与额外日常动作目前仍在制作完整原生状态，**尚未作为可安装宠物发布**。概念预览不是完整 v2 包，也不代表应用支持自动换装或额外随机触发器。

## 权利说明

这是非官方粉丝作品，用于个人定制，与 OpenAI、Codex、库洛游戏及《鸣潮》无关联。未获得相关权利前，请勿商用。AI 生成素材不代表角色权利已获授权。
