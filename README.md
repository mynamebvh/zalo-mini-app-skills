# Zalo Mini App — Codex skills

Codex skills that package Zalo Mini App documentation into references and checklists you can use directly while building or reviewing an app.

## Skills

### 1. `zalo-mini-app-zaui`

Build UI with **ZaUI Components** (`zmp-ui`).

```
.codex/skills/zalo-mini-app-zaui/
├── SKILL.md                  # Main guidance for Codex
└── references/
    ├── INDEX.md              # Index of all documentation
    ├── examples.md           # Usage patterns verified against zmp-ui
    ├── overview.md
    ├── installation.md
    ├── principles.md
    ├── release-notes.md
    ├── foundation/           # Colors, Icons, Spacing, Typography, ...
    ├── container/            # Box, Center, Cluster, Grid, Stack, ZBox
    ├── display/              # Avatar, Calendar, Icon, List, Text, ...
    ├── form/                 # Button, Input, Select, Picker, DatePicker, ...
    ├── layout/               # App, Page, Header, BottomNavigation, Tabs, ...
    └── overlay/              # Modal, Sheet, ActionSheet, Snackbar
```

- Source: <https://docs.zaloplatforms.com/docs/MA/zaui>
- Scraped: 2026-11-02; source docs state last updated 2026-10-28.
- Package reference: `zmp-ui@1.11.15-2`.
- **52 current pages** scraped.
- `/specs/*` skipped because it duplicates the "Design guidelines" tab 100%; versions 1.7.0–1.10.0 skipped as outdated.

### 2. `zalo-mini-app-censorship-policy`

Review a Mini App against Zalo's **Censorship Policy**.

```
.codex/skills/zalo-mini-app-censorship-policy/
├── SKILL.md                  # Review workflow + quick checklist
└── references/
    ├── INDEX.md
    ├── checklist.md          # Full checklist with criterion IDs
    ├── 00-overview.md
    ├── 01-logo-mini-app.md
    ├── 02-mini-app-name.md
    ├── 03-mini-app-description.md
    ├── 04-mini-app-content.md
    ├── 05-mini-app-performance.md
    ├── 06-user-permissions.md
    ├── 07-privacy-and-security.md
    ├── 08-checkout-sdk-integration.md
    └── 09-other.md
```

- Source: <https://miniapp.zaloplatforms.com/documents/zalo-mini-app-censorship-policy/>
- Accessed: 2026-11-02; the source page does not show an update date.
- All 9 sections and 27 subsections scraped, with 42 illustrations preserved.
- Checklist uses criterion IDs (LOGO, NAME, DESC, CONTENT, PERF, PERM, PRIV, CHECKOUT, OTHER).

### 3. `zalo-mini-app-api`

Use the **Zalo Mini App JavaScript API** (`zmp-sdk`).

```
.codex/skills/zalo-mini-app-api/
├── SKILL.md                  # Main guidance + category map
└── references/
    ├── INDEX.md              # Index of every API
    ├── intro.md              # Official API overview
    ├── events.md
    ├── errorCode.md
    ├── changelog.md
    ├── basics/               # getAppInfo, getSystemInfo, ...
    ├── user/                 # authorize, getUserInfo, getSetting, ...
    ├── routing/              # openMiniApp, openWebview, ...
    ├── native-storage/       # setItem, getItem, ...
    ├── lfs/                  # saveFile, getFileInfo, ...
    ├── user-interface/       # showToast, configAppView, hideKeyboard, ...
    ├── location/
    ├── media/                # camera/, cameraContext/, file/
    ├── device/               # network/, contact/, qr/, screen/, bio-authentication/
    ├── permission/
    ├── zalo/                 # openChat, followOA, ...
    ├── advertising/
    └── widgets/
```

- Source: <https://docs.zaloplatforms.com/docs/MA/api/intro>
- Accessed: 2026-11-02; docs state last updated 2026-10-28.
- Package: `zmp-sdk`.
- **93 pages** scraped: every API in the official introduction, plus events, error codes, and changelog.
- Six pages missing from the sitemap (`advertising/*`, `device/bio-authentication/*`) were recovered from links in the introduction.

## Installing into Codex

Option 1 — use in the current project: keep `.codex/skills/` at the project root.

Option 2 — install globally for every project:

```bash
cp -r .codex/skills/* ~/.codex/skills/
```

Verify:

```bash
ls ~/.codex/skills/zalo-mini-app-zaui/SKILL.md
ls ~/.codex/skills/zalo-mini-app-censorship-policy/SKILL.md
ls ~/.codex/skills/zalo-mini-app-api/SKILL.md
```

## Notes

- Each reference keeps the original documentation content (now in English) with a source link.
- The ZAUI skill includes `references/examples.md` with examples verified against `zmp-ui@1.11.15-2`.
- The censorship skill includes `references/checklist.md` for pre-submission audits.
- The API skill includes `references/INDEX.md` listing every API with a one-line description.