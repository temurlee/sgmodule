# Modules for Surge & Stash

脚本基于 Surge 测试；Stash 版使用同一套脚本，按 Stash 的 `http.script` 覆写格式封装。其他客户端不做保证。

## Modules for Surge

### 🎥 YouTube Enhance

- **功能**：去广告、画中画、后台播放、翻译
- **适用**：YouTube & YouTube Music
- **安装**：[链接](YouTube.Enhance.sgmodule?raw=true)

---

### 📺 Bilibili Helper

- **功能**：去弹幕、去广告、阻止 P2P
- **适用**：Bilibili
- **安装**：[链接](Bilibili.Helper.sgmodule?raw=true)

---

### 🌐 Aliyun DoH JSON API

- **功能**：适配阿里 DoH JSON API 鉴权
- **安装**：[链接](Alidns.sgmodule?raw=true)
- **备选**：使用[快捷指令](https://www.icloud.com/shortcuts/d94224c9df9f4e7ebe7ef2124f5e0180)动态更新鉴权 DNS（查看注释了解更多）

---

### 🏃‍♂️ Keep

- **功能**：去广告、简化导航栏
- **注意**：可能需重装 Keep 应用
- **安装**：[链接](KeepAds.sgmodule?raw=true)

---

## Modules for Stash

### 🎥 YouTube Enhance

- **功能**：去广告、画中画、后台播放、翻译
- **适用**：YouTube & YouTube Music
- **覆写文件**：[YouTube.Enhance.stoverride](YouTube.Enhance.stoverride?raw=true) / [一键安装](https://link.stash.ws/install-override/raw.githubusercontent.com/temurlee/sgmodule/master/YouTube.Enhance.stoverride)
- **直连配置**：[Stash.YouTube.Direct.yaml](Stash.YouTube.Direct.yaml?raw=true) / [一键导入](https://link.stash.ws/install-config/raw.githubusercontent.com/temurlee/sgmodule/master/Stash.YouTube.Direct.yaml)

#### 使用说明

> 直连配置是独立配置文件，不是覆写。请在 Stash 的「配置」中导入；如果一键链接失败，可以把文件下载到 iCloud，选择用 Stash 打开。若仍提示解析错误，改用 `YouTube.Enhance.stoverride`，再把首页模式切到「直连 / Direct」。

1. 在 Stash 的「配置 → 覆写」中导入 `YouTube.Enhance.stoverride` 并启用；或在「配置」中直接导入 `Stash.YouTube.Direct.yaml`。
2. 在 Stash → MitM 中生成并安装 CA 证书，然后在 iOS「设置 → 通用 → 关于本机 → 证书信任设置」中信任该证书。
3. 如果设备所在网络已经完成科学上网、不需要 Stash 再代理，使用 `Stash.YouTube.Direct.yaml`；它不配置任何代理节点，并用 `MATCH,DIRECT` 兜底所有流量。使用覆写时，请在 Stash 首页把模式切到「直连 / Direct」。
4. MitM 只对 `youtubei.googleapis.com` 和 `*.googlevideo.com` 开启，其他 App 的 HTTPS 不会被解密。
5. 脚本从 `raw.githubusercontent.com` 更新；如果设备无法访问该域名，可以把 `Script/Youtube/` 下的两个 JS 保存到本地，用 `script-providers.<name>.path` 引用。
