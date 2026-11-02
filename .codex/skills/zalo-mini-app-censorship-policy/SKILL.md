---
name: zalo-mini-app-censorship-policy
description: Review a Zalo Mini App against Zalo's censorship and approval policy. Use when preparing an app for submission, auditing logo/name/description/content/performance/permissions/privacy/Checkout SDK requirements, or answering questions about Zalo Mini App review criteria.
---

# Zalo Mini App — Censorship Policy

This skill packages Zalo's **Mini App Censorship Policy** and turns it into a review checklist that can be used to audit a Mini App before submitting it for approval.

- Source: <https://miniapp.zaloplatforms.com/documents/zalo-mini-app-censorship-policy/>
- Accessed: 2026-11-02. The original page does not display an update date.
- Original document language: Vietnamese.

## When to use

- Preparing to submit a Mini App for censorship review.
- Reviewing logo, name, description, content, performance, permissions, privacy, Checkout SDK.
- Checking whether a new feature risks violating the policy.
- Answering questions about review criteria or review time.

## How to use

1. Read `references/checklist.md` for the full checklist organized by criterion code.
2. Read the corresponding section file in `references/` when you need the original content or illustrations.
3. For criteria that are only illustrated with images, open the image link in the section file for comparison.
4. Report using the template at the end of this file, specifying criterion codes.

## Quick checklist

| Section | Main requirements | Reference |
| --- | --- | --- |
| 1. Logo | Genuine, not impersonated; clear, matches functionality; no phone number/QR code; no transparent background | `references/01-logo-mini-app.md` |
| 2. Name | Matches functionality; not all caps; no generic nouns; no "App", "Mini App", "Zalo", special characters, emoji; should have a prefix/suffix | `references/02-mini-app-name.md` |
| 3. Description | Matches functionality, audience, purpose; no links; no content violating the law/good customs | `references/03-mini-app-description.md` |
| 4. Content | No navigation outside; complies with the law; no monetized advertising; no virtual items/cryptocurrency; no cash withdrawal/reward payout; no social network/direct competition with Zalo; clear images/fonts; clear policy terms | `references/04-mini-app-content.md` |
| 5. Performance | Features actually work, not a demo; no freezing/white/black screen; LCP < 2.5s; PageLoad Time < 1.5s; no more than 10s | `references/05-mini-app-performance.md` |
| 6. Permissions | Request permissions in the right context, with an option to decline; don't force permissions right when entering the app; don't force login/sign-up; don't fake the platform UI; link accounts correctly | `references/06-user-permissions.md` |
| 7. Privacy | Explicit consent when collecting data; no malware; no unauthorized third-party sharing; safe links | `references/07-privacy-and-security.md` |
| 8. Checkout SDK | Mandatory integration if there are orders/payments/direct prices; otherwise hide prices and switch to "Contact"/"Consultation" | `references/08-checkout-sdk-integration.md` |
| 9. Other | Review within 3 business days; OA verification; minimum 10 visits/month; special sectors require documents; time-limited campaigns must be stated clearly | `references/09-other.md` |

## Common rejection reasons

- Impersonated logo, missing logo, logo containing a phone number/QR code, or a transparent background.
- Name written entirely in uppercase, using generic nouns, containing "App"/"Mini App"/"Zalo", special characters, or emoji.
- Description containing links or not matching functionality.
- Navigating users outside the Mini App, encouraging them to download a separate app, or logging in with Google/Facebook.
- Displaying advertising banners, selling virtual items/cryptocurrency/unlicensed NFTs.
- Having cash withdrawal/reward payout features or social network features (posts, videos, likes, comments).
- Forcing users to grant permissions right when entering the app or forcing login/sign-up.
- Having payments/prices but not integrating the Checkout SDK.
- Features still in Demo state, app freezing, white/black screen.
- LCP > 2.5 seconds, PageLoad Time > 1.5 seconds, or loading longer than 10 seconds.

## Review process

1. Collect information: logo, name, description, screen flows, access permissions, privacy policy, payment flow.
2. Check each section 1–9 in the checklist; mark **Pass / Fail / Insufficient information**.
3. For criteria with illustrations, open the image in the reference for visual comparison.
4. Record criterion codes (e.g., `PERM-6.1`, `CONTENT-4.4`, `CHECKOUT-8`) so the development team can look them up easily.
5. Suggest specific fixes, not just point out issues.
6. Do not assert that the Mini App will be approved; the final decision rests with Zalo.

## Report template

```markdown
## Conclusion
- Status: Pass / Needs fixes / Insufficient information
- Risk level: High / Medium / Low

## Violations / risks
| Code | Section | Issue | Severity | Fix |
| --- | --- | --- | --- | --- |
| LOGO-1.2 | Logo | Logo contains a phone number | High | Use a logo with only the brand name/icon |

## Passed
- ...

## Needs confirmation
- ...
```

## Limitations

- Some criteria are expressed through illustrations (e.g., sections 3.2, 6.5); the images must be opened for a full assessment.
- The policy may be updated by Zalo; before official submission, re-check the source page.
- This is a review-support document, not legal advice.
