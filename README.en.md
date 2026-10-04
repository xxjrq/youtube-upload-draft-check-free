# YouTube Upload Draft Check

Create a traceable pre-publish issue list for one confirmed YouTube Studio draft. Input is a user-selected browser, owned Studio draft or publishing target, and browserId. Output records visible title, description, thumbnail, audience, visibility, and captions values, gaps, and sources. It stops if ownership, login, or draft selection is unclear; it never publishes or changes visibility.

![YouTube Upload Draft Check promo](assets/promo-1600x900.png)

## Install

```bash
npx skills add xxjrq/youtube-upload-draft-check-free
```

Browser inspection requires [Easy WebBridge on GitHub](https://github.com/xxjrq/easy-webbridge), with a [Gitee mirror](https://gitee.com/xxjrq/easy-webbridge). The Skill uses only the supplied browserId and its own task session.

## Offline verification

```bash
python3 scripts/check_draft.py fixtures/success-page.json
python3 scripts/self_test.py
```

Fixtures simulate visible pages and are never presented as online collection.
