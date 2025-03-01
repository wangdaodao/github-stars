---
project: logto
stars: 9572
description: 🧑‍🚀 An identity and access management (IAM) infrastructure with authentication, authorization, MFA, SSO, user management, and multi-tenancy features. Supports OAuth 2.0, OIDC, and SAML. No framework restrictions.
url: https://github.com/logto-io/logto
---

Logto
=====

Logto1 is an open-source identity and access management infrastructure for modern apps and SaaS products, supporting OIDC, OAuth 2.0 and SAML open standards for authentication and authorization.

Key features
------------

### 🧑‍💻 Comprehensive frontend-to-backend identity solutions

-   Enables OpenID Connect (OIDC) based authentication and authorization with Logto SDKs.
-   Supports passwordless sign-in, along with various options like email, phone number, username, Google, Facebook, and other social sign-in methods.
-   Offers beautiful prebuilt UI with customizable options to suit your business needs.

### 📦 Out-of-the-box infrastructure

-   Includes a ready-to-use Management API that allows you to build customized functionality on top of Logto.
-   Provides various official SDKs and guides that help you integrate your apps with Logto across multiple platforms and languages.
-   Offers flexible social and message connectors that can be used for one-click social sign-ins and customized with SAML, OAuth, and OIDC protocols.

### 💻 Enterprise-ready solutions

-   Implements role-based access control (RBAC) for scalable authorization.
-   Organizations is the way to build multi-tenancy apps with ease.
-   Enables user management with audit logs to track identity-related activities and maintain security.
-   Provides single sign-on (SSO) and multi-factor authentication (MFA) without coding.

Get started
-----------

### Logto Cloud

Try Logto Cloud to start the Logto journey with zero deployment overhead.

### GitPod

You can launch Logto via GitPod. Please wait for the message `App is running at https://3002-...gitpod.io` to appear in the terminal, press Command on macOS or Ctrl on Windows, then click the URL starting with `https://3002-` to continue your Logto journey.

### Docker Compose

Docker Compose CLI usually comes with Docker Desktop.

curl -fsSL https://raw.githubusercontent.com/logto-io/logto/HEAD/docker-compose.yml | \\
docker compose -p logto -f - up

### npm-init

Requires Node.js `^20.9.0` + PostgreSQL `^14.0`.

npm init @logto

Language support
----------------

const languages \= \['Deutsch', 'English', 'Español', 'Français', 'Italiano', '日本語', '한국어', 'Polski', 'Português', 'Русский', 'Türkçe', '简体中文', '繁體中文'\];

Web compatibility
-----------------

Logto uses the default browserslist config to compile frontend projects, which is:

```
> 0.5%, last 2 versions, Firefox ESR, not dead
```

Bug report, feature request, feedback
-------------------------------------

-   Our team takes security seriously, especially when it relates to identity. If you find any existing or potential security issues, please do not hesitate to email 🔒 security@logto.io.
-   About other bug reports, feature requests, and feedback, you can:
    -   Directly 🙋 open an issue on GitHub if you find a bug.
    -   💬 Join our Discord server to have a live chat.
    -   📧 Subscribe to our newsletter to stay tuned on our latest articles and updates.

Licensing
---------

MPL-2.0.

Contributing
------------

We have a contributing guideline available. Feel free to reach out to us before coding.

Resources
---------

-   📚 Logto docs for
-   📝 Logto blog for in-depth articles, tutorials, and updates.
-   🔗 Logto API
-   Check out our awesome list of community-contributed resources.

Footnotes
---------

1.  Designed by Silverhand Inc. ↩
