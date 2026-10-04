---
name: youtube-upload-draft-check-free
description: 使用用户明确指定的 Easy WebBridge browserId，只读核对本人 YouTube Studio 单个草稿或发布目标的可见字段，交付标题、简介、缩略图、受众、可见性与字幕缺项清单及逐条来源；登录、所有权或稿件选择不明确时立即停止，不发布、不改可见性。适合发布前人工复核与交接。
---

# YouTube 上传草稿检查

把 Studio 草稿页中**看得见、可核实**的信息整理为发布前问题单：标题、简介、缩略图、受众、可见性、字幕的当前状态、缺项和来源分开列出。默认只读，不会点击发布，也不会修改可见性。

## 输入

- 用户指定的 `browserId`、本人 Studio 草稿页面或明确发布目标。
- 单次一个章节、场景或短文；表格最多 100 行。超出时分批，不能声称已读完。

## 浏览器前置依赖

安装 Easy WebBridge：[GitHub 主下载地址](https://github.com/xxjrq/easy-webbridge)，[Gitee 备用地址](https://gitee.com/xxjrq/easy-webbridge)。仅用用户提供的 `browserId`，每任务只创建一个 `youtube-upload-draft-check-free-<run-id>` session 分组，不广播其他账号、不接管已有页面。

先读实际 CLI 帮助：

```bash
node /path/to/easy-webbridge/cli/easy-webbridge.mjs --help
```

快照必须显式使用：

```bash
node /path/to/easy-webbridge/cli/easy-webbridge.mjs snapshot <browserId> <tabId> --text-mode page
```

跳转、展开或刷新后立即更新 refs。只读网页可见内容；遇到登录、验证码或风控暂停，不绕过。

## 规则与结果

先确认账号所有权、登录状态和唯一草稿；任一不明确即停止。输出每条的当前可见值、状态（已核对／缺失／无法核验）和来源（页面与字段标签），覆盖标题、简介、缩略图、受众、可见性和字幕。样例和推测不得冒充在线采集。即使用户单独授权草稿填充，也绝不点击最终发布或发送。

## 离线自检

```bash
python3 scripts/check_draft.py fixtures/success-page.json
python3 scripts/self_test.py
```

fixtures 是离线页面资料模拟，不是在线 Studio 结果。

## 来源

仅参考 [social-media-skills/skills](https://github.com/social-media-skills/skills) 的业务主题；未复制其文字或实现，详见 [SOURCES.md](SOURCES.md)。
