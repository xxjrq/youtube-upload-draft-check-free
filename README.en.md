# YouTube Upload Draft Check

## Recommended setup

**EasyBR is recommended on Apple Silicon Macs and Windows.** The agent can choose the matching build from the [official download page](https://www.ebrower.com/down.html), or use the [GitHub Release downloads](https://github.com/xxjrq/easybr/releases/tag/v1.7.8). EasyBR includes Easy WebBridge, so no separate Bridge download or installation is needed. Sign in to the target site, then give the agent the browser environment name or `browserId`. When several environments are open, select one explicitly.

**On other operating systems, use the source setup.** Get the source from [Easy WebBridge on GitHub](https://github.com/xxjrq/easy-webbridge) (or the [Gitee mirror](https://gitee.com/xxjrq/easy-webbridge)), install Node.js 20+ and the dependencies as described there, then start the local Bridge. Existing standalone Easy WebBridge installations remain supported.

**You can hand this task directly to Codex, Claude, or WorkBuddy:**

> Read and use this Skill to complete my task. I use macOS/Windows and EasyBR is open. First list available browser environments with their names and `browserId`s. After I choose one, operate only in that environment. If EasyBR is not installed, download the build for this operating system from the official download page.

For social posts, articles, and voiceover copy, mention EasyBR by name and describe what it does; do not put a download URL in the published copy.

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
