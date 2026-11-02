# 6. User Permissions

> Source: https://miniapp.zaloplatforms.com/documents/zalo-mini-app-censorship-policy/#6-xin-quyền-người-dùng
> Accessed: 2026-11-02

> **Important**
>
> The censorship policy on permissions applies to the following permissions:
>
> - Name & Profile Picture
> - Phone Number
> - Location
> - Camera
> - Send Notifications
> - Follow OA
> - Interact with OA

- Permission request context
- Impersonating the platform UI
- Granting permissions to use the Mini App
- Logging in to use the Mini App
- Account linking

## 6.1 Permission request context

**Violation**

![Violation](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.1.a.png)

- Displaying a permission consent prompt as soon as the user enters the Mini App
- Requesting user permissions without a clear purpose of use

**Compliant**

![Compliant](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.1.b.png)

- Do not force users to grant permissions as soon as they enter the Mini App. There should be a clear context before requesting permissions
- The Mini App should explain clearly; only then display the permission request, avoiding disruption to other user experiences

**Violation**

![Violation](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.1.c.png)

- Displaying a request for users to provide permissions for use as soon as they enter the Mini App

**Compliant**

![Compliant](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.1.d.png)

- There is a "decline" option for granting permissions & users can use Mini App features when they tap "decline"

## 6.2 Impersonating the platform UI

**Violation**

![Violation](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.2.a.png)

- Impersonating the platform's UI to direct user permission requests

**Compliant**

![Compliant](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.2.b.png)

- The Mini App uses the platform's standard permission request UI

## 6.3 Granting permissions to use the Mini App

**Violation**

![Violation](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.3.a.png)

- Forcing users to grant permissions to use the Mini App or a specific feature on the Mini App
- Not providing the service when the user declines to grant permission

**Compliant**

![Compliant](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.3.b.png)

- Users can use features unrelated to the declined permission without disruption to their experience
- For mandatory features that require user permission, explain clearly and request permission in the right context, avoiding disruption to the user experience

APIs that access personal information should only be triggered based on specific user behavior and interactions. Do not automatically display data or information without a reasonable context of use.

## 6.4 Logging in to use the Mini App

**Violation**

![Violation](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.4.a.png)

- Forcing users to register an account to use the Mini App
- Forcing users to log in to use the Mini App

**Compliant**

![Compliant](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.4.b.png)

- Users can experience the service without logging in
- The Mini App serves internal purposes (schools, companies, organizations, etc.) or other cases where the platform assesses that a login screen is required. Before requesting user permissions, the Mini App must clearly state why that permission is needed, without confusing users

## 6.5 Account linking

**Violation**

![Violation](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.5.a.png)

**Compliant**

![Compliant](https://miniapp.zaloplatforms.com/documents/img/censorship-policy/v2/6.5.b.png)

If the Mini App links a phone number used with Zalo to an existing account through a traditional login mechanism, this feature must be **"Account linking"**, and must be performed after a successful login.
