<div align="center">

# 🚀 Manifast

### Manifest, fast — ship your desktop app to the Microsoft Store without the ceremony.

[![Get it from the Microsoft Store](https://img.shields.io/badge/Microsoft%20Store-Manifast-0078D4?logo=windows&logoColor=white)](https://apps.microsoft.com/detail/9N0W32S5WBL1)
![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-1f1f1f)
![CLI](https://img.shields.io/badge/CLI-mani-6e40c9)
![Free tier](https://img.shields.io/badge/free%20tier-really%20publishes-2ea043)

&nbsp;·&nbsp; [Report an issue](https://github.com/cybesis/manifast/issues/new/choose)
&nbsp;·&nbsp; [Privacy](PRIVACY_POLICY.md)
&nbsp;·&nbsp; [Terms](TERMS_OF_SERVICE.md)

</div>

---

Getting a desktop app onto the Microsoft Store is not hard because packaging is hard. It is hard
because of the parts nobody documents: the Azure AD service principal, the "you must submit once by
hand before the API unlocks" trap, MSIX manifests that fail certification for reasons the error
message does not explain, and screenshots that are eleven pixels too wide.

**Manifast** is the tool that knows all of that. It walks you through credentials, checks your build
before Microsoft does, packages and signs it, writes the listing, submits it, and then shows you how
it is doing.

Available as a **desktop app** and as **`mani`**, a CLI you can drop into any `npm run` script or CI
pipeline — both driven by the same engine.

## ✨ What it does

- **Credential onboarding wizard** — the single hardest step, made survivable. Walks you through
  creating the Azure AD service principal, tests the connection before you commit, and explains the
  one-manual-submission rule that blocks every newcomer's first API call.
- **Store Doctor** — a readiness check that runs *before* you submit: manifest validity, icon and
  asset completeness, screenshot dimensions, version ordering, capability declarations, and the
  cert-failure patterns that cost a review cycle.
- **Release pipeline** — a 7-step flow from build to submitted, with each step showing what it did
  and what it will do next.
- **MSIX packaging and signing** — wraps the official Windows tooling (`makeappx`, `signtool`,
  `winapp`) so you are not memorizing flags.
- **AI Listing Studio** — generate descriptions, keywords, changelogs, and certification notes from
  a short brief, including per-locale variants. *(Pro)*
- **Analytics** — your installs, ratings, and revenue from the Store, in one place. *(Pro)*
- **Workflows & templates** — reusable release recipes and generated CI configuration. *(Pro)*
- **Credential vault** — publisher identities stored in the OS keychain, switchable per project,
  with reminders before a client secret expires.
- **Add-ons & IAP manager** — durable add-ons and in-app purchases without the Partner Center maze.
  *(Pro Studio)*

## 🏪 Stores

| Store | Status |
|---|---|
| **Microsoft Store** | ✅ Supported |
| Steam | 🔜 Planned |
| Apple App Store | 🔜 Planned |
| Google Play | 🔜 Planned |
| Chrome Web Store | 🔜 Planned |

Windows first, and properly, before anything else is added.

## 💷 Pricing

**The free tier really publishes.** One project, one store profile, the full release pipeline, Store
Doctor, manual submission, and the CLI — free forever, not a trial.

Paid tiers add automation and leverage rather than unlocking the basics: unlimited projects, the AI
Listing Studio, analytics, workflows, multi-profile and team vaults, and add-on management. A
one-time lifetime option is available. Current prices are on the
[Microsoft Store listing](https://apps.microsoft.com/detail/9N0W32S5WBL1) and at
[cybesis.com](https://cybesis.com).

## 🔒 Where your data goes

Manifast is a publishing tool, so unlike a purely local app it *does* talk to the network — that is
the job. It is worth being exact about it:

- **To Microsoft** — your packages, listings, and submissions, using **your own** Partner Center
  credentials. This is the product working.
- **To an AI provider** — only for the AI Listing Studio, only when you press generate, and only the
  brief you wrote.
- **To Cybesis Studios** — nothing. We run no server that Manifast reports to. There is no telemetry
  and no analytics SDK.

Your Azure AD client secret and signing credentials are stored in the **OS keychain**, never in
plain text, and never transmitted to us. Full detail in the [Privacy Policy](PRIVACY_POLICY.md).

## 🚀 Get it

**[⬇ Download Manifast from the Microsoft Store](https://apps.microsoft.com/detail/9N0W32S5WBL1)**

## 🧭 Quick start

1. Install and open Manifast.
2. Run the **onboarding wizard** — it creates and tests your Partner Center connection.
3. **New project** → point it at your build output.
4. Run **Doctor** and fix what it flags.
5. **Pipeline** → package, sign, write the listing, submit.

Prefer the terminal? `mani init`, `mani doctor`, `mani package`, `mani submit` do the same thing.

## 🐛 Support & bug reports

This repository is the public home for Manifast **documentation and issue tracking** — the
application source is private.

- **Found a bug?** [Open an issue](https://github.com/cybesis/manifast/issues/new/choose)
- **Email:** studio@cybesis.com

For submission failures, include the Store Doctor output and the certification message Microsoft
returned — with your credentials and secrets removed.

---

<div align="center">

Built by **[Cybesis Studios](https://cybesis.com)** · Montpellier, France<br>
Built on the pipeline that ships our own Store apps

</div>
