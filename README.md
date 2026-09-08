# Cinnamoroll_Desk

基于 [RustDesk](https://github.com/rustdesk/rustdesk) 二次开发的远程桌面客户端（个人版）。

品牌名：**Cinnamoroll**（云桂远程）  
维护账号：`linxi27667`

> 本仓库发布 **Windows / Android 客户端安装包** 与使用说明。  
> 核心协议与开源组件仍遵循 RustDesk 原项目许可（AGPL-3.0）。

## 特性

- 玉桂狗风格 UI（天蓝奶油主题、品牌头图、地址簿空状态贴纸）
- Windows 便携包 + 一键安装（服务/开始菜单/桌面图标）
- Android arm64 APK
- 可对接自建 `hbbs` / `hbbr` / API

## 一键拿安装包

### 本机整理目录（推荐直接拷给别人）

```text
F:\RustDesk\release\
  Windows\Cinnamoroll-Windows-portable.zip
  Android\Cinnamoroll-1.5.0-arm64.apk
  README.txt
```

### GitHub Release

到本仓库 **Releases** 下载最新：

- `Cinnamoroll-Windows-portable.zip`
- `Cinnamoroll-1.5.0-arm64.apk`

## 快速安装

### Windows

1. 解压 `Cinnamoroll-Windows-portable.zip`
2. 右键 `一键安装.bat` → **以管理员身份运行**
3. 从开始菜单打开 Cinnamoroll / RustDesk
4. 设置 → 网络 → 填写你的自建服务器：

| 项 | 说明 |
|----|------|
| ID / 中继 | 你的服务器 IP 或域名 |
| API | 一般是 `https://你的服务器` |
| Key | 自建 hbbs 的公钥 |
| 使用 WebSocket | 电脑端测直连时可先关闭；手机端通常需要开启 |

### Android

1. 安装 `Cinnamoroll-1.5.0-arm64.apk`（允许未知来源）
2. 网络设置同上
3. **务必开启「使用 WebSocket」**（开源自建 + API 场景下，手机不开 WS 容易握手失败）

## 画质建议（公网）

- Bitrate（码率）：`100% ~ 300%`
- FPS：先 `30`（不要一上来 120）
- 被控电脑分辨率可先设为 `1920x1080`
- 服务器若开启 `ALWAYS_USE_RELAY=Y` 会强制中继，无法打洞直连

## 目录说明

```text
Cinnamoroll_Desk/
  README.md
  docs/                 使用与部署说明
  releases/             Release 资源说明（安装包见 GitHub Releases）
```

## 二次开发说明

- 上游：RustDesk `1.5.0`
- 主要改动：Flutter UI 主题 / 品牌资源 / 移动端与桌面端壳层
- 原生库：匹配版本的 `librustdesk`（勿混用 1.4.x 与 1.5.x）

## 安全提示

- 请勿把服务器 **Root 密码、API 账号密码、设备连接密码** 提交进公开仓库
- Key、服务器地址请自行保管；需要公开仓库时使用占位符
- 分享安装包时，按需单独告知对方服务器配置

## 许可

- 本仓库自定义 UI/文档部分：以仓库声明为准（个人自用二次分发）
- RustDesk 上游及衍生二进制：遵循 [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html)
