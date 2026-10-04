# YouTube 上传草稿检查

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
