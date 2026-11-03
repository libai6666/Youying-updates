# Youying 更新分发仓

柚影（Youying）App 的公开更新通道。源码在私有仓库开发，CI 发版时把各端安装包以 GitHub Release 形式推送到本仓库，并更新对应的清单文件；App 端轮询清单即可发现新版本。

## 清单文件

App 按平台读取：

| 平台 | 文件 |
|---|---|
| Android | `latest-android.json` |
| Windows | `latest-windows.json` |
| iOS | `latest-ios.json` |

清单格式：

```json
{
  "version": "1.4.5",
  "build": 29,
  "url": "https://github.com/libai6666/Youying-updates/releases/download/<tag>/<asset>",
  "page": "https://github.com/libai6666/Youying-updates/releases/tag/<tag>",
  "notes": ["变更说明……"],
  "published": "2026-11-03T09:00:00Z"
}
```

- `version` / `build`：与安装包一致，App 用它和本机版本比较。
- `url`：可直接下载的安装包地址（Android 为 APK，Windows 为 setup.exe，iOS 仅作记录，更新走下载页）。
- `page`：Release 页面，iOS 与备用下载入口使用。
- `notes`：可选更新说明，弹窗中展示。
- `published`：发布时间（UTC）。

## 维护

文件由 `libai6666/Youying` 的发版工作流自动维护，正常不需要手工改动；手工改动时请保持 JSON 格式与字段含义不变。
