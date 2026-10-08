# Scheduled Banner for Jira / Confluence

Schedule announcement banners in Jira and Confluence Cloud. Provided by NAMINOL LLC (NAMINOL合同会社).

- [Privacy Policy / プライバシーポリシー](PRIVACY.md)
- [Terms of Service / 利用規約](TERMS.md)
- [Security Policy / セキュリティ方針](SECURITY.md)
- Support / お問い合わせ: masaki_hori@naminol.com

## Scheduled Banner for Jira

Shows Jira's built-in announcement banner during the period you set, and hides it afterwards.

1. Open **Jira settings → Apps → 予約バナー (Scheduled Banner)**.
2. Click **お知らせを追加 (Add announcement)** and enter:
   - Message
   - Display period and time zone (defaults to your profile time zone)
   - Audience: logged-in users only (recommended), or everyone including anonymous visitors
   - Whether users can dismiss the banner with ×
3. Save. The banner appears and disappears automatically. Changes are applied every 5 minutes, so they may be delayed by up to about 5 minutes.

Notes:
- Only one announcement is shown at a time. If periods overlap, the one with the later start wins.
- A banner that an administrator set manually is never turned off by the app. While a scheduled announcement is active, it takes priority.

## Scheduled Banner for Confluence

Shows a banner at the top of Confluence during the period you set.

1. Open **Confluence administration → Apps → 予約バナー (Scheduled Banner)**.
2. On first use, choose a storage space. Pick a space that everyone can view and only administrators can administer. Users who cannot view it will not see banners.
3. Click **お知らせを追加 (Add announcement)**, enter the message, period and time zone, and save.

Notes:
- Shown on pages, blog posts, live docs, space overviews, Confluence home, search results, the spaces directory and the editor. Not shown on whiteboards or databases (Confluence limitation).
- Users can dismiss the banner. Each user who dismisses an announcement will not see it again.

## 日本語

### Jira 版
1. **Jira 管理設定 → アプリ → 予約バナー**を開きます。
2. **お知らせを追加**から、本文・表示期間・タイムゾーン（初期値はプロフィールの設定）・表示する相手・× で閉じられるかを設定して保存します。
3. 期間になると自動で表示され、終了すると消えます。反映は5分ごとのため、最大約5分遅れます。

### Confluence 版
1. **Confluence 管理 → アプリ → 予約バナー**を開きます。
2. 初回は保存先スペースを選びます（全員が閲覧でき、管理者だけが管理できるスペース）。
3. **お知らせを追加**から、本文・表示期間・タイムゾーンを設定して保存します。閉じたユーザーには再表示されません。
