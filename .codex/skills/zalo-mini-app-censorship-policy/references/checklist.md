# Mini App Censorship Checklist

This checklist interprets the criteria in the Mini App Censorship Policy. Each item corresponds to a section in the original document; mark **Pass / Fail / Insufficient information** and record the criterion code when reviewing.

## 1. Mini App Logo

- [ ] **LOGO-1.1 — Genuine logo, not impersonated**
  - Do not use the logo of another app or another brand.
  - The Mini App must have a logo.
  - The logo must be the logo of the entity that owns the Mini App.
- [ ] **LOGO-1.2 — Logo appropriate to functionality**
  - The logo must relate to the Mini App's functionality/purpose.
  - Do not use a logo containing a phone number or QR code.
  - Do not use a logo with a transparent background.
  - The logo must be clear and appropriate to the functionality and purpose.

## 2. Mini App Name

- [ ] **NAME-2.1 — Name appropriate to the feature/functionality**
  - The name must not misrepresent the Mini App's functionality.
  - The name must accurately reflect the Mini App's functionality.
- [ ] **NAME-2.2 — Naming rules**
  - Do not write the entire name in uppercase.
  - Do not use generic nouns or generic keywords as the name.
  - Must not contain the words "App", "Mini App", "Zalo".
  - Must not contain special characters such as `#`, `$`, `@`, `!`, emoji, or symbols.
  - A prefix or suffix that helps distinguish the app and identify the owning entity is recommended.
  - If the name has registered trademark rights, provide the relevant documents.

## 3. Mini App Description

- [ ] **DESC-3.1 — Description appropriate to the feature/functionality**
  - The description must accurately reflect the Mini App's functionality and purpose.
  - The Mini App must have a description.
  - The description must clearly state the functionality, audience, and purpose.
- [ ] **DESC-3.2 — Description does not contain prohibited content**
  - Must not contain links.
  - Must not contain content that violates good customs and traditions.
  - Must not contain content prohibited by law.

## 4. Mini App Content

- [ ] **CONTENT-4.1 — Navigation to third-party page links**
  - Do not encourage users to download a separate app.
  - Do not direct users to log in with Google, Facebook, etc.
  - Do not navigate to links outside the Mini App.
  - Exception: Privacy Policy, Terms of Use, etc. may be displayed, but the link must be hidden/disabled, or the document must be embedded in the Mini App as a popup.
- [ ] **CONTENT-4.2 — Content complies with the law**
  - No misleading, fraudulent, or fake content.
  - No content prohibited by law.
  - Content complies with the law and good customs and traditions.
- [ ] **CONTENT-4.3 — Advertising and monetization**
  - Do not display advertising banners without authorization.
  - Must not contain or display monetized advertising in the app.
- [ ] **CONTENT-4.4 — Virtual items**
  - No buying or selling of virtual items or virtual currency of electronic games.
  - No involvement with cryptocurrency or unlicensed digital products (NFTs).
  - No buying or selling of digital content/digital utility services (online courses, music streaming packages, movie streaming packages, etc.).
  - Purchase transactions must be tied to real-world services actually used (laundry, locker rental, charging stations, etc.).
- [ ] **CONTENT-4.5 — Cash withdrawal/Reward payout**
  - No features related to cash withdrawal or reward payout.
- [ ] **CONTENT-4.6 — Social network/direct competition with Zalo**
  - No social network or user interaction features such as posting posts, videos, likes, comments, etc.
  - No features that directly compete with products in the Zalo system (Zing MP3, Zalo, Video).
- [ ] **CONTENT-4.7 — Images and text**
  - All images must load.
  - No font errors or hard-to-read fonts.
  - Images and text are displayed clearly.
- [ ] **CONTENT-4.8 — Mini App policies and terms**
  - The title must clearly indicate that these are the policies/terms of the Mini App "Mini App Name".
  - The policy and terms content must be clear.
  - Do not use generic content.
  - Must clearly indicate which business entity the policies/terms belong to.

## 5. Mini App Performance

- [ ] **PERF-5.1 — Features work normally**
  - All features must be usable.
  - Do not leave some or all features in Demo state.
- [ ] **PERF-5.2 — Incidents during use**
  - The app must not freeze.
  - No white/black screens.
  - No errors occur during use.
- [ ] **PERF-5.3 — Load time**
  - Largest Contentful Paint (LCP) under 2.5 seconds.
  - PageLoad Time under 1.5 seconds.
  - Mini App/feature load time no more than 10 seconds.

## 6. User Permissions

Permissions covered by the policy: Name & Profile Picture, Phone Number, Location, Camera, Send Notifications, Follow OA, Interact with OA.

- [ ] **PERM-6.1 — Permission request context**
  - Do not display a permission consent prompt as soon as the user enters the Mini App.
  - Do not request permissions without a clear purpose of use.
  - Explain clearly before displaying the permission request.
  - Provide a "decline" option.
  - Users can still use unrelated features after declining.
- [ ] **PERM-6.2 — Impersonating the platform UI**
  - Do not impersonate the platform's UI to direct permission requests.
  - Use the platform's standard permission request UI.
- [ ] **PERM-6.3 — Granting permissions to use the Mini App**
  - Do not force users to grant permissions to use the Mini App or a specific feature.
  - Do not refuse to provide the service when the user does not grant permission.
  - Features unrelated to the declined permission must still work.
  - For mandatory permissions, explain clearly and request them in the right context.
  - Only trigger APIs that access personal information based on specific user behavior and interactions; do not automatically display data without a reasonable context.
- [ ] **PERM-6.4 — Logging in to use**
  - Do not force users to register an account to use the Mini App.
  - Do not force users to log in to use the Mini App.
  - Users must be able to experience the service without logging in.
  - Exception: internal Mini Apps (schools, companies, organizations, etc.) or cases where the platform assesses that a login screen is needed; the reason must be clearly explained and not cause confusion.
- [ ] **PERM-6.5 — Account linking**
  - The feature that links a Zalo phone number with an existing account must be called **"Account linking"**.
  - Only perform it after a successful login.
  - Also compare against the illustrations in `06-user-permissions.md`.

## 7. Privacy and Security

- [ ] **PRIV-7 — Personal data and security**
  - Do not collect personal data without explicit consent.
  - Must not contain malware or lead through links containing malware.
  - Do not share personal data with third parties without notification/permission.
  - Only collect data with explicit and transparent consent.
  - Must not contain unsafe links.
  - Third parties receiving data must comply with equivalent security standards.

## 8. Checkout SDK Integration

- [ ] **CHECKOUT-8 — Determine the mandatory case**
  - If the Mini App generates orders, has payment functionality, and displays prices directly: **Checkout SDK integration is mandatory**.
  - If there is no need to use the Checkout SDK: do not display product/service prices; change the purchase – payment function to "Contact" or "Consultation".

## 9. Other

- [ ] **OTHER-9.1 — Review time**
  - The Mini App is reviewed within 3 business days, excluding Saturdays, Sundays, and public holidays.
- [ ] **OTHER-9.2 — Maintaining operation**
  - Verify through a Zalo Official Account (OA) or valid documents/licenses according to the type of ownership and industry.
  - Main features operate stably according to the released version.
  - Maintain a minimum of 10 visits/month.
  - If the criteria are not met within 3 months, remediation is required to avoid restricted display or deactivation.
- [ ] **OTHER-9.3 — Special industry groups**
  - Special sectors (Pharmaceuticals, Cosmetics, Functional Foods, etc.) and conditional business lines must verify the Mini App and provide relevant documents.
- [ ] **OTHER-9.4 — Time-limited deployment**
  - Time-limited campaign/event Mini Apps must clearly state the start and end times when submitting the version review request.
  - Or display the times directly on the Mini App's UI.
- [ ] **OTHER-9.5 — Support contacts**
  - Government agencies/public service units: the "Zalo Digital Transformation" OA or `minicqnn@zalo.me`.
  - Finance, credit, banking, insurance: `support@fiza.ai`.
  - Other types: `hotrodoitac@zaloplatforms.com`.
