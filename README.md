# 爱弥斯 · Aimisi Codex Pet

非官方、个人定制的 Codex 桌面宠物。原装、运动装、居家装均提供完整 v2 包，每套包含 9 个标准动作状态和 16 个注视方向。

![待机](previews/idle.gif)
![向右移动](previews/running-right.gif)
![挥手](previews/waving.gif)

## 安装

将所需条目复制到 `~/.codex/pets`。已有同名条目时先备份；也可以一次安装三套：

```powershell
$petRoot = Join-Path $env:USERPROFILE '.codex\pets'
$backupRoot = Join-Path $env:USERPROFILE '.codex\pet-backups'
New-Item -ItemType Directory -Path $petRoot,$backupRoot -Force | Out-Null
foreach ($id in @('aimisi','aimisi-sport','aimisi-home')) {
    $destination = Join-Path $petRoot $id
    if (Test-Path -LiteralPath $destination) {
        $backup = Join-Path $backupRoot "$id-$(Get-Date -Format 'yyyyMMdd-HHmmss')"
        Copy-Item -LiteralPath $destination -Destination $backup -Recurse
    }
    Copy-Item -LiteralPath ".\pets\$id" -Destination $petRoot -Recurse -Force
}
```

重新打开宠物选择器，选择「爱弥斯」「爱弥斯·运动装」或「爱弥斯·居家装」。如果仍显示旧图像，可重新打开应用。服饰通过独立条目手动切换。发布检查覆盖图集、逐帧图像及浏览器预览，应用内所有动作触发器尚未实际验证。

| 条目 | 造型与动作风格 | 预览 |
| --- | --- | --- |
| `aimisi` | 原装，元气俏皮 | [动作](previews/contact-sheet.png) · [注视](previews/look-directions.png) |
| `aimisi-sport` | 蓝白运动外套、短裙裤与运动鞋，轻快互动 | [动作](previews/aimisi-sport/contact-sheet.png) · [注视](previews/aimisi-sport/look-directions.png) |
| `aimisi-home` | 象牙白针织衫、蓝色袖口与家居鞋，放松陪伴 | [动作](previews/aimisi-home/contact-sheet.png) · [注视](previews/aimisi-home/look-directions.png) |

## 当前版本

- `spriteVersionNumber: 2`
- 8 列 × 11 行，每格 192 × 208，总图 1536 × 2288，WebP 透明通道。
- 标准状态：待机、向右移动、向左移动、挥手、跳跃、受挫、等待输入、执行任务、检查结果。
- 16 向注视：以向上为 000°，顺时针每隔 22.5°；不是人物全身旋转。
- 左右移动分别制作，保留蓝色发夹的解剖侧别；待机更安静，受挫动作含恢复过程。

原装安装包校验见 [原装发布检查](qa/release-summary.json)。两套新增服饰的本地安装图集与仓库图集逐字节一致，校验见 [换装发布检查](qa/wardrobe-release-summary.json)。每套的动作、方向语义、三位隔离盲审、透明通道及连续性检查记录保存在 `qa` 对应条目目录。

## 动作与换装

两套新服饰均包含完整动作，左右移动独立制作以保留非对称发夹；跳跃保留蓄力、腾空与落地高度；挥手、等待、专注和受挫恢复各有对应手势与表情。注视以眼睛、眼睑和头颈配合，保持脚和下身稳定。

当前使用应用原生的 9 个状态。服饰是手动切换的独立宠物条目；额外日常概念动作没有独立随机触发器，自动换装也不在本包中。衣摆和辫梢跟随较轻，少数接近竖直方向的横向线索较轻微，作为已复核的改进提醒保留。

## 权利说明

这是非官方粉丝作品，用于个人定制，与 OpenAI、Codex、库洛游戏及《鸣潮》无关联。未获得相关权利前，请勿商用。AI 生成素材不代表角色权利已获授权。
