# selfplayer-release

自用播放器的**发布仓库**：只存放 `version.json` 与 APK 安装包，不含源码。

## App 内更新机制

App 启动时会请求本仓库的 `version.json`：

```
https://raw.githubusercontent.com/dsawq-wqs/selfplayer-release/main/version.json
```

字段含义：

| 字段 | 说明 |
|---|---|
| `versionCode` | 判断依据，**必须大于已装版本**才会提示更新 |
| `versionName` | 展示用的版本号 |
| `apkUrl` | APK 直链，可指向任意平台 |
| `notes` | 更新说明 |

## 发版步骤

1. 传新 APK 到新 Release（tag 与版本号一致，如 `v3.5.0`）
2. 修改 `version.json`：`versionCode` +1，更新 `versionName` / `apkUrl` / `notes`
3. 手机上打开 App 即自动弹出更新
