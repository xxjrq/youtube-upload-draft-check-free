# YouTube 上传草稿检查

## 推荐使用方式

**macOS（仅 Apple 芯片）和 Windows 推荐 EasyBR。** AI 可从官方[客户端下载页](https://www.ebrower.com/down.html)按系统选择版本；也可用 [GitHub Release 下载页](https://github.com/xxjrq/easybr/releases/tag/v1.7.8)作为下载渠道。打开浏览器后，EasyBR 已内置 Easy WebBridge，无需另行下载或安装 Bridge 服务。先登录目标网站，再把要操作的浏览器环境名称或 `browserId` 告诉 AI；有多个环境时必须指定一个目标。

**其他操作系统使用源码方式。** 从 [Easy WebBridge GitHub](https://github.com/xxjrq/easy-webbridge) 获取源码（[Gitee 镜像](https://gitee.com/xxjrq/easy-webbridge)），按项目说明安装 Node.js 20+ 和依赖后运行本地 Bridge。已有独立 Easy WebBridge 的用户仍可继续使用。

**可以直接把任务交给 Codex、Claude 或 WorkBuddy：**

> 请读取并使用这个 Skill 完成我的任务。我使用的是 macOS/Windows，EasyBR 已打开。先检查可用的浏览器环境，向我展示名称和 `browserId`；选定后只在该环境中操作。若 EasyBR 尚未下载，请从官方客户端下载页获取与本机系统匹配的版本。

写自媒体文章、口播或社交平台文案时，只提 EasyBR 名称和用途，不在正文中直接贴下载网址。

在发布前，用一份可追溯的问题单看清本人 YouTube Studio 草稿是否缺标题、简介、缩略图、受众、可见性或字幕。输入是用户指定的浏览器、本人草稿页或发布目标与 browserId；结果是逐字段的可见值、缺项状态和来源。登录、所有权或稿件选择不明确时会停止，不发布也不修改内容。

![YouTube 上传草稿检查推广图](assets/promo-1600x900.png)

## 安装

```bash
npx skills add xxjrq/youtube-upload-draft-check-free
```

## 使用

浏览器检查需要 [Easy WebBridge（GitHub）](https://github.com/xxjrq/easy-webbridge)，备用为 [Gitee 镜像](https://gitee.com/xxjrq/easy-webbridge)。提供唯一目标及明确 browserId；Skill 只在该环境创建自己的 session 分组，默认只读，不操作其他账号或已有页面。

离线资料可独立验证：

```bash
python3 scripts/check_draft.py fixtures/success-page.json
python3 scripts/self_test.py
```

fixtures 是离线页面资料模拟，验证本地清单逻辑，不代表在线采集。完整行为边界见 [SKILL.md](SKILL.md)。

## 许可与来源

MIT，见 [LICENSE](LICENSE)。业务主题参考与原创说明见 [SOURCES.md](SOURCES.md)。
