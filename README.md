# selfplayer-release

**自制视频播放器**的发布仓库：只存放版本清单与 APK 安装包，不含源码。

| App | 版本清单 | 包名 | 版本体系 |
|---|---|---|---|
| 自制视频播放器 | `privatevideo.json` | `com.privatevideo.player` | 1.xx |

> 原「自用播放器」（`version.json` / 3.x）已整体下线并删除，本仓库不再维护该线。

## 自制视频播放器

主清单：`https://raw.githubusercontent.com/dsawq-wqs/selfplayer-release/main/privatevideo.json`

备用（jsDelivr CDN）：`https://cdn.jsdelivr.net/gh/dsawq-wqs/selfplayer-release@main/privatevideo.json`

## 清单字段

| 字段 | 说明 |
|---|---|
| `versionCode` | 判断依据，**必须大于已装版本**才会提示更新 |
| `versionName` | 展示用的版本号 |
| `apkUrl` | 主下载地址（本仓库默认写加速镜像，保证国内能下动） |
| `apkUrlBackups` | 备用下载地址数组，主地址失败自动依次尝试 |
| `notes` | 更新说明 |

## 发版步骤

1. 传新 APK 到新 Release（tag 形如 `video-v1.22`）
2. 改对应的清单文件：`versionCode` +1，更新 `versionName` / `apkUrl` / `notes`
3. 刷新 jsDelivr 缓存：访问 `https://purge.jsdelivr.net/gh/dsawq-wqs/selfplayer-release@main/privatevideo.json`
4. 手机上打开 App 即自动弹出更新

> 各项目根目录的 `发布到GitHub.py` 会把 1~3 步一次做完。
