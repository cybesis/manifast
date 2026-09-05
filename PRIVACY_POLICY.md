# Manifast — Privacy Policy

**Last updated:** 5 September 2026
**Applies to:** Manifast for Windows and the `mani` CLI, published by Cybesis Studios (Montpellier, France)
**Contact:** studio@cybesis.com

> This document describes what Manifast the *application* does with your data. Cybesis Studios'
> general company privacy policy is at <https://cybesis.com/privacy>. Where the two differ about the
> Manifast app, this document governs.

---

## The short version

Manifast publishes your app to a store. Doing that requires talking to that store's API on your
behalf, so — unlike a purely offline tool — Manifast does use the network. Being precise about which
network calls happen, and to whom, is the point of this document.

- **Cybesis Studios collects nothing.** We operate no server that Manifast reports to. No telemetry,
  no analytics SDK, no usage tracking, no crash reporting to us.
- **Your credentials never reach us.** Azure AD secrets and signing credentials live in your
  operating system's keychain on your machine.
- **Traffic goes to Microsoft, using your own credentials** — because that is how your app gets
  published.
- **Optional AI** sends only the brief you write, only when you press generate.
- **Payments** are handled by our payment provider, not by us.

---

## What Cybesis Studios collects

**Nothing from the application.** Manifast contains no analytics, advertising, A/B testing, session
recording, or crash-reporting SDK. We cannot see your projects, your credentials, your listings,
your submission history, your revenue, or whether you have ever opened the app.

We do hold:

- **Support correspondence** you send us by email or in a GitHub issue.
- **Purchase records** for paid licences, as described under *Payments and licensing* below.

## Your Partner Center credentials

To submit on your behalf, Manifast needs Azure AD service-principal credentials for your Partner
Center account: a **tenant ID**, a **client ID**, and a **client secret**.

- These are supplied by you and are stored in the **operating system keychain** (Windows Credential
  Manager), not in a plain-text config file, and not in your project folder.
- They are used solely to obtain an access token from **Microsoft** and to call the Microsoft Store
  submission API on your instruction.
- They are **never transmitted to Cybesis Studios**. We have no server to receive them and no
  ability to read your keychain.
- Access tokens obtained from Microsoft are cached locally to avoid re-authenticating on every
  action, and expire normally.
- Deleting a profile from the Vault removes the stored secret from the keychain.

**Secret expiry.** Azure AD client secrets expire (one year by default). Manifast may remind you
before expiry. That check is a local date comparison — it involves no call to us.

## Code signing

If you sign packages through Manifast, it invokes the standard Windows tooling (`signtool`) on your
machine with the certificate you nominate. **Private keys and certificates are never uploaded,
copied, or transmitted anywhere.** Manifast reads what it needs to run the signing operation locally
and nothing more.

## What is sent to Microsoft

When you use Manifast to package, submit, or monitor an app, the following goes to Microsoft's
Partner Center and Store APIs — authenticated as **you**, with your own credentials:

| Sent | When |
|---|---|
| Your application package (MSIX) | When you upload or submit |
| Listing text, keywords, screenshots, and other assets | When you save or submit a listing |
| Pricing, availability, and add-on configuration | When you change them |
| Submission and certification queries | When you check status |
| Analytics queries | When you open Analytics |

Microsoft's privacy statement and your Partner Center agreement govern this data. Cybesis Studios is
not a party to it and never sees it in transit.

**Store analytics** shown in Manifast are *your own* sales, install, and rating figures, fetched
from Microsoft with your credentials and displayed to you. They are not aggregated, shared, or sent
to us.

## Optional AI listing generation

The **AI Listing Studio** can draft descriptions, keywords, changelogs, certification notes, and
localized variants.

- It runs **only when you explicitly ask it to generate something**. It is never automatic and never
  runs in the background.
- What is sent is the **brief and app metadata you provide** — the app name, a short description of
  what it does, and any guidance you type. Your source code, your packages, your credentials, and
  your analytics are **not** sent.
- Requests go to the configured AI provider. Review that provider's privacy policy and retention
  terms before using the feature, particularly if your listing brief contains anything unannounced
  or confidential.
- If you do not use the feature, no AI request is ever made.

**Unreleased product information.** A listing brief for an unannounced app is commercially sensitive
by nature. Treat the AI Listing Studio the way you would treat any external drafting service, and do
not paste anything you are not prepared to send to a third-party model provider.

## What Manifast stores on your device

| Data | Location | Purpose |
|---|---|---|
| Project configuration (`manifast.json`) | Your project folder | Per-project settings, package paths, listing data |
| Credential profiles | OS keychain | Publisher identities |
| Cached access tokens | Local app data | Avoid re-authenticating constantly |
| Analytics cache | Local app data | Show figures without refetching |
| Licence file | Local app data | Offline entitlement verification |
| Build and packaging output | Your project folder | The MSIX and intermediate artifacts |

`manifast.json` lives in your project and is intended to be committed to version control. **It does
not contain secrets** — credentials stay in the keychain. Review it before committing, as you would
any config file.

## Payments and licensing

Free-tier use requires no account and no payment.

Paid licences are sold through our payment provider (**Paddle**), which acts as merchant of record.
Paddle collects the billing information necessary to process the transaction and comply with tax
law, and its privacy policy governs that data. **Cybesis Studios never receives or stores your full
payment card details.** We receive the record of the purchase and the email address associated with
the licence, which we use to issue and support it.

Where a paid tier is purchased as a Microsoft Store add-on instead, Microsoft handles the
transaction and Microsoft's privacy statement applies.

Licences are verified using an offline cryptographic signature. Verification is a **local**
operation — it does not phone home, and Manifast continues working without a network connection.

## Third parties, summarized

| Party | What reaches them | When |
|---|---|---|
| **Microsoft** (Partner Center / Store) | Your packages, listings, submissions, analytics queries | Whenever you publish or check status |
| **AI provider** | The listing brief you write | Only when you press generate |
| **Paddle** | Your billing details | Only when you purchase a paid tier |
| **Cybesis Studios** | Nothing from the app | — |

## Children

Manifast is a professional developer tool, not directed at children, and does not knowingly collect
data from anyone.

## Your rights

Cybesis Studios holds no personal data from the application itself, so there is nothing for us to
export or erase in that respect — your projects and credentials are already entirely in your
possession.

For purchase records and support correspondence we do hold, you may request access, correction, or
erasure by writing to studio@cybesis.com, subject to any legal retention obligations that apply to
transaction records. You also have the right to lodge a complaint with your local data protection
authority; in France, that is the CNIL.

## Changes

Material changes to this policy will be reflected in the date above and in the app's release notes.
The current version always lives at
<https://github.com/cybesis/manifast/blob/main/PRIVACY_POLICY.md>.
