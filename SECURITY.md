# Security Policy / セキュリティ方針

- Applies to: NAMINOL LLC (NAMINOL合同会社) and its Atlassian Marketplace apps (Scheduled Banner for Jira / Confluence)
- Owner: Masaki Hori (security contact)
- Approved: 2026-10-08 / Review: at least once a year

## Reporting a vulnerability

Email masaki_hori@naminol.com. We acknowledge reports within 3 business days. Vulnerabilities reported through the Atlassian Marketplace Security (AMS) project are handled the same way.

## 1. Scope and architecture

- The apps run entirely on Atlassian Forge. They have no Forge Remote and no egress to external hosts.
- They store data only in Atlassian product storage on the customer's site.
- We operate no servers or databases of our own. Hosting, encryption at rest, backups and platform logs are provided by Atlassian.

## 2. Accounts and access

- Multi-factor authentication is required on company email, GitHub, and the Atlassian accounts used to develop and publish the apps.
- Passwords must be unique per service and at least 12 characters. Using a password manager is recommended.
- Only the people who need it get access to the Atlassian developer console, Marketplace partner account, GitHub organization and company email.
- Access is reviewed every quarter and removed promptly when someone leaves.

## 3. Workstations

- Full-disk encryption (FileVault) is enabled.
- Automatic OS and security updates are enabled.
- The built-in malware protection (XProtect / Gatekeeper) is kept on.
- OS versions that no longer receive security patches are not used.

## 4. Secure development

- We follow the OWASP Top 10 and the Atlassian Forge security guidelines:
  - least-privilege scopes
  - a permission check before any `asApp` call
  - server-side input validation
  - no secrets or personal data in logs
- Before each release we:
  - run `forge lint`
  - run `npm audit`
  - test the changed functions on a development site
- Third-party dependencies are limited to Atlassian-published Forge packages.
- `package-lock.json` serves as the software bill of materials. It is reviewed with `npm audit` at every release and at least quarterly.
- The apps hold no API keys or secrets of their own. If one is introduced, it will be stored as a Forge encrypted variable and rotated at least once a year.

## 5. Vulnerability management

We fix vulnerabilities within the Atlassian Marketplace Security Bug Fix Policy timeframes for cloud apps:

| Severity | Fix within |
|---|---|
| Critical | 10 days |
| High | 4 weeks |
| Medium | 12 weeks |
| Low | 25 weeks |

We respond to AMS tickets within the triage period. For critical vulnerabilities we notify affected customers using Atlassian's vulnerability notification template.

## 6. Incident response

1. **Detect and record**: what happened, when, and which apps and customers are affected.
2. **Contain**, for example:
   - disable the affected function
   - deploy a fix
   - revoke access
3. **Notify Atlassian within 24 hours** with a P1 ticket in the Atlassian developer support portal.
   - Cover the eight items in Atlassian's incident management guidelines: category and scope, impact, data types, timeline, containment, root cause, remediation, and contact.
   - Send an update at least every 6 hours until resolved.
4. **Notify affected customers within 72 hours** where possible.
5. **Review** after resolution: root cause, lessons learned and preventive actions. Update this policy if needed.

This plan is tested by walking through a sample scenario at least once a year.

## 7. Business continuity

- Source code is kept in a version-controlled repository with an offsite copy.
- The apps can be redeployed from source with the Forge CLI. Runtime data stays in Atlassian storage.
- Restoring the development environment and redeploying is tested at least once a year.

## 8. AI / ML

We do not apply AI/ML algorithms to Atlassian or customer data, and no subprocessors do so on our behalf.

---

## 日本語の要約

- **前提**：アプリは Atlassian Forge 上だけで動き、外部への通信はなく、自社サーバーも持ちません。
- **アカウント**：メール・GitHub・Atlassian は2段階認証を必須にします。パスワードはサービスごとに別にし、12文字以上にします。アクセス権は四半期ごとに見直します。
- **作業用 PC**：FileVault、自動アップデート、OS 標準のマルウェア対策を有効にします。
- **開発**：リリースのたびに lint、npm audit、開発サイトでのテストを行います。
- **脆弱性の修正期限**：Atlassian の規定に従います（Critical 10日 / High 4週 / Medium 12週 / Low 25週）。
- **インシデント**：Atlassian へ24時間以内に P1 チケットで報告し、6時間ごとに状況を伝えます。顧客には可能なら72時間以内に知らせます。
- **年1回の訓練**：インシデント対応の机上訓練と、再デプロイの復旧テストを行います。
