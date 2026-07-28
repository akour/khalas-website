# Google Play Data Safety answers — Khalas

This mapping is based only on the stated behaviour of package `com.habibiapps.routines`.

## Overview

| Play Console question | Answer | What to enter |
|---|---|---|
| Does your app collect or share any of the required user data types? | **Yes** | RevenueCat receives purchase/transaction information, an anonymous app user ID, and device identifiers for subscription management. |
| Is all user data collected by your app encrypted in transit? | **Yes** | Subscription-related data sent to RevenueCat/Google uses encrypted transport. Routine data is not transmitted. Confirm this against the release build before submission. |
| Do you provide a way for users to request that their data is deleted? | **Yes** | Use the public `data-deletion.html` URL. |
| Is your app independently reviewed against a global security standard? | **No** | Do not claim an independent security review unless one has actually occurred. |

## Data types to declare

| Category in Play | Data type | Collected? | Shared? | Required or optional? | Purpose |
|---|---|---:|---:|---|---|
| Financial info | Purchase history | **Yes** | **No*** | Optional; only when the user uses subscription features | App functionality; account management |
| Device or other IDs | Device or other IDs | **Yes** | **No*** | Required for subscription verification when using Premium | App functionality; fraud prevention, security and compliance; account management |

\* RevenueCat and Google Play are service providers processing subscription information for app functionality. Google Play’s form generally does not count a transfer to a service provider as “sharing” when it is made under the developer’s instructions. Confirm that your RevenueCat agreement and implementation meet Play’s service-provider exception. If not, mark the relevant data types as shared.

## Data types not collected by HabibiApps

Select **not collected** for:

- Name
- Email address
- User IDs tied to an identified account
- Address
- Phone number
- Race and ethnicity
- Political or religious beliefs
- Sexual orientation
- Other personal information
- Precise or approximate location
- Payment information or card details
- Credit score
- Other financial information
- Health information
- Fitness information
- Emails
- SMS or MMS
- Other in-app messages
- Photos
- Videos
- Voice or sound recordings
- Music files
- Documents and files
- Calendar events
- Contacts
- App interactions
- In-app search history
- Installed apps
- Other user-generated content
- Web browsing history
- Crash logs
- Diagnostics
- Other app performance data

## Important local-data distinction

Routines, steps, completion logs, reminder settings, and exported files are processed only on the device. Under Google Play’s Data Safety definitions, on-device processing that is never transmitted off the device is not “collected” and should not be declared as collected.

## Security and account questions

| Question | Answer |
|---|---|
| Can users create an account? | **No.** Khalas has no accounts. |
| Does the app support account deletion? | **Not applicable.** There is no app account. Still provide the data-deletion URL for local and purchase-record instructions. |
| Does the app sell user data? | **No.** |
| Is data used for advertising or marketing? | **No.** |
| Is data used for analytics or personalization? | **No.** |
| Is data used for developer communications? | **No.** |

## Verify before submitting

Two answers depend on the final SDK configuration rather than copy alone:

1. Confirm RevenueCat’s current Android SDK disclosure, including the exact device identifiers it sends in your configured version.
2. Confirm whether RevenueCat qualifies as a service provider under your agreement. This determines whether Play should show “shared” as No or Yes.

