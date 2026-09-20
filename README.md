# selfplayer-release

两个自用播放器的**发布仓库**：只存放版本清单与 APK 安装包，不含源码。

| App | 版本清单 | 包名 | 版本体系 |
|---|---|---|---|
| 自用播放器 | `version.json` | `com.privplayer.app` | 3.x |
| 自制视频播放器 | `privatevideo.json` | `com.privatevideo.player` | 1.xx |

> 两份清单**刻意分开**：两个 App 的 versionCode 体系不同，共用一份会互相误判成有新版本。

## 自制视频播放器

主清单：`https://raw.githubusercontent.com/dsawq-wqs/selfplayer-release/main/privatevideo.json`

备用（jsDelivr CDN）：`https://cdn.jsdelivr.net/gh/dsawq-wqs/selfplayer-release@main/privatevideo.json`

## 清单字段

| 字段 | 说明 |
|---|---|
| `versionCode` | 判断依据，**必须大于已装版本**才会提示更新 |
| `versionName` | 展示用的版本号 |
| `apkUrl` | APK 直链，可指向任意平台（GitHub / Gitee / 自建） |
| `notes` | 更新说明 |

## 发版步骤

1. 传新 APK 到新 Release（tag 形如 `video-v1.22`）
2. 改对应的清单文件：`versionCode` +1，更新 `versionName` / `apkUrl` / `notes`
3. 刷新 jsDelivr 缓存：访问 `https://purge.jsdelivr.net/gh/dsawq-wqs/selfplayer-release@main/privatevideo.json`
4. 手机上打开 App 即自动弹出更新

> 各项目根目录的 `发布到GitHub.py` 会把 1~3 步一次做完。
