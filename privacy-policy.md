# Privacy Policy — Ember

**Effective date:** 2026-09-17
**Version:** 1.5
**Application:** Ember (`com.embers.app`)
**Publisher:** Paul Rabiller, 745A Havelock Road, Singapore 169657
**Contact:** contact.app.ember@gmail.com

This policy is written in English. English is the authoritative version.

---

## 1. Summary

Ember runs entirely on your device.

- There is no server, no account, and no cloud service operated by the publisher.
- No data from the app is ever sent to the publisher automatically, and the publisher has no technical
  means of accessing it.
- There is no analytics, no crash reporting, no advertising, and no third-party tracking of any
  kind.
- Android's built-in backup stores an encrypted copy of your app data in your own Google account.

Two features deserve a careful read: **reading notifications**, which involves information about
other people, explained in full in section 3; and the **optional diagnostic** you may attach to a
support email, explained in section 5.

---

## 2. Permissions Ember uses

**Notification access** (optional, off by default). A special access you enable manually in Android
Settings. It powers automatic contact detection. See section 3.

**Notification posting** (`POST_NOTIFICATIONS`). Required from Android 13 onward so Ember can show
you its own reminders. Nothing to do with reading other apps' notifications. Ember says so at the
moment it asks, because being asked about notifications twice in one sitting is genuinely confusing.

Ember **requests** no other permission of its own. What the manifest carries beyond that, and
why:

- **No contacts permission.** Ember never reads your address book. There is no code in the app that
  touches the system contacts provider.
- **No storage permission.** Export uses Android's native file picker, which grants access only to
  the single file you choose.
- **Internet permission: declared, and unused by Ember.** The merged manifest does carry
  `INTERNET` and `ACCESS_NETWORK_STATE`. Neither is requested by Ember: both are pulled in by
  Google Play Billing, through a Google component it depends on, and they are what lets Play reach
  Google's own servers to process a purchase. **No code in Ember opens a network connection**, and
  the app has no server to connect to. The only thing that deliberately goes online is your own
  browser, when you tap the refund link in Settings.

  We would rather tell you the permission is there than claim an absence you could disprove by
  opening the app's page on Google Play. An automated check on every build lists every permission in
  the published manifest, with where each one comes from; a new one cannot appear unnoticed.

---

## 3. Notification access — what is read and what is kept

Ember offers an optional feature that detects when a friend has contacted you, so you do not have to
record it by hand. It is off by default, and the app is fully usable without it.

### What Ember reads

When the feature is enabled, Ember examines notifications from **three applications only**:
WhatsApp, Facebook Messenger, and Instagram. A notification from any other application is discarded
on arrival, before any of its content is read.

From a qualifying notification, Ember reads the sender's identifier and the display name shown in
the conversation.

### The pool of observed people

**Please read this section carefully — it concerns people other than you.**

To let you link a friend without typing identifiers by hand, Ember maintains a local pool of the
people it has observed on those three platforms. Each entry holds the display name as the platform
showed it, and the platform-specific identifier attached to that conversation.

This pool covers **both one-to-one and group conversations**. For someone seen in a group, Ember also
stores **the name of that group** — not its messages, only its name, and only so that the linking
screen can tell two people with the same display name apart.

This means the pool can contain people you have not added as friends in Ember, and may never add.
Their names sit in Ember's local database as candidates for linking.

Entries you have not linked to anyone are **erased automatically after 30 days**. Entries you have
linked are kept, so that a friend you speak to twice a year stays verifiable. You can also empty the
pool yourself at any time — see section 9.

The pool never leaves your device except inside your own Android backup, described in section 6. It
is never transmitted to the publisher, never shared, and the publisher cannot see it.

### What Ember records as contact

When a notification matches an identifier you have linked to a friend, Ember records **three
things**: the date and time, which app it came from, and the nature of the exchange — a direct
message, a group message, or a call. Nothing else from the notification is recorded.

### What Ember never keeps

**The content of your messages is never stored.** Message text is never saved, never written to any
file, and never written to any log. It is not retained beyond the instant the notification is
handled.

### How linking works

You type your friend's name yourself — Ember never fills it in for you. You then attach one or more
entries from the pool to that friend. Removing a friend removes their contact events, notes, and
links.

### Your consent is tied to this text

When the disclosure screen changes in substance — a platform added, a new field retained, a longer
retention period — Ember records that the text has changed and **shows it to you again** before the
feature resumes. A consent given for one description does not silently carry over to another.

### Revoking access

You can withdraw Notification Access at any time in **Android Settings → Apps → Special app access →
Notification access**, or from Ember's own Settings. Ember stops reading notifications immediately.
Data already recorded remains until you delete it.

---

## 4. What Ember stores on your device

- Friends you created: the name you typed, plus any notes, birthday, or favourite marking you added.
- The pool of observed people described in section 3.
- Links between your friends and pool entries.
- Contact events: date and time, platform, and nature of the exchange.
- App settings, and your answer to the disclosure screen with the version of the text you saw.
- Two timestamps recording when your free trial started, so that it cannot be restarted. Neither
  contains anything personal.
- The date detection last recognised anyone, used to warn you if detection has silently stopped
  working.

All of it lives in a local database on your device.

---

## 5. What the publisher receives

Nothing automatically. Ember never transmits anything to the publisher on its own.

The publisher receives personal data from you only if **you** choose to send an email to
contact.app.ember@gmail.com. In that case the publisher receives your email address and whatever you
write, uses it solely to answer you, and keeps it no longer than needed for that purpose. This is the
only circumstance in which the publisher acts as a data controller in respect of your data.

### The optional diagnostic

Ember's Settings contain a "Something wrong, or an idea?" entry that opens **your own email app**,
with the address and subject filled in. Ember does not send anything itself; you write, read and send
the message.

A checkbox, **on by default**, inserts a short diagnostic block into the body of that message. It is
plain text, sitting in the email in front of you: you can read it and delete it before sending.

It contains **counts and states, never content**:

| Included | Never included |
|---|---|
| App version and build number | Any friend's name |
| Android version, device model, interface language | Any platform identifier, account ID, or link |
| Number of friends tracked, number paused | The text of any note |
| Number of links per platform | Any birthday |
| Number of exchanges in the last 30 days, number of notes | Any group name or observed display name |
| Whether notification access is granted, which sources are on | The content of any notification |
| Your plan and trial days remaining | The exact timestamp of any exchange |
| How long ago detection last recognised anyone, in days | — |

The last row is deliberately expressed in days rather than as a date: a precise timestamp would tell
the publisher when somebody messaged you.

---

## 6. Backup

Ember uses Android's built-in **Auto Backup for Apps**. This is a platform feature, available to all
users on all plans, not something the publisher operates.

- **What is backed up:** everything Ember stores on your device — friends, links, notes, birthdays,
  favourites, contact events, settings, the trial timestamps, **and the pool of observed people**
  described in section 3.
- **Where it goes:** the backup space Android reserves in your own Google account. It does **not**
  consume your personal Google Drive storage quota.
- **Encryption:** your data is encrypted **on your device, before it is uploaded**, using a key
  derived from your device's lock screen. Google cannot read the contents, and neither can the
  publisher.
- **Your control:** you can disable backup, and delete existing backups, in your Android and Google
  account settings. **Uninstalling Ember does not automatically remove a backup already made.**

The publisher has no access to backups and no way to request them.

A note on the pool, since it concerns people other than you: it is included in the backup because
Android's backup rules operate on files, and the pool shares a single database with everything else.
Separating it would mean a second database for no meaningful gain, given that the backup is encrypted
on your device, lands in your own account, and is unreadable to Google and to the publisher alike. We
would rather tell you it is there than claim an exclusion that does not exist.

---

## 7. Payments

Premium is a one-time purchase processed entirely by **Google Play Billing**. Google handles the
payment and receives the payment information. The publisher never receives, sees, or stores your
payment details, card number, or billing address, and receives only aggregate, anonymised sales
reporting from Google.

Google's handling of that data is governed by Google's own privacy policy.

---

## 8. Sharing

The app shares no data with anyone. There are no third-party SDKs in the app other than Google Play
Billing. There are no advertising partners, no analytics providers, and no data brokers.

The publisher does not sell, rent, or share personal data, because the publisher does not receive
any.

---

## 9. Your control over your data

**Export.** Ember can export your data as a versioned JSON file through Android's native file
picker. The file is produced on your device and goes only where you send it.

**Import.** You can restore from an export file. Importing **replaces your existing data entirely** —
it does not merge. The confirmation prompt says so before you proceed.

**Deleting a friend.** Removing a friend deletes their contact events, notes, and links.

**Clearing observed people.** The pool screen has an action that empties the pool of everyone you
have **not** linked to a friend. People you have linked are left untouched, so clearing the pool
never interrupts any tracking you have set up.

**Deleting everything.** Settings contains an **Erase all my data** action that removes your friends,
links, the pool, contact events, notes, birthdays, favourites, and settings. Because it cannot be
undone, it asks you to type the word `ERASE` to confirm.

Two technical values are kept: the timestamps recording that your free trial has already run. They
contain no identifier and nothing personal, and they are retained so the action cannot be used to
restart the trial. The confirmation dialog states this before you proceed. Any purchase you made is
also kept, and is restored automatically by Google Play.

You can also use **Android Settings → Apps → Ember → Storage → Clear data**, or uninstall the app.
Both remove everything Ember holds on the device, including those timestamps.

**Backups** made through Android's backup system must be removed separately, through your Google
account settings.

If you have emailed the publisher and want that correspondence deleted, write to
contact.app.ember@gmail.com.

---

## 10. Children

Ember is not directed at children. It is intended for users aged 16 and over. The publisher does not
knowingly collect data from anyone, including children, as no data is collected at all.

---

## 11. Legal basis and applicable law

The publisher is an individual established in Singapore.

**Singapore (PDPA).** The only personal data the publisher collects is email correspondence you
initiate, used solely to respond to you.

**European Economic Area and United Kingdom (GDPR / UK GDPR).** The data Ember processes on your
device — including the pool of observed people described in section 3 — is processed by you, on your
own device, for your own personal and household purposes. That falls outside the scope of the GDPR
under Article 2(2)(c). The publisher is not a controller or processor of that data and has no access
to it. For email correspondence you send to the publisher, the legal basis is the publisher's
legitimate interest in responding to you (Article 6(1)(f)), and you may request access to or
deletion of that correspondence.

Other jurisdictions: the same facts apply — no collection, no transmission, no third-party sharing.

---

## 12. Security

Your data is protected by your device's own security: screen lock, device encryption, and Android's
application sandbox, which prevents other apps from reading Ember's data. Backups are encrypted on
your device before upload. Because the app transmits nothing to the publisher, there is no server to
breach.

Keeping your device locked and up to date is the most effective protection for your Ember data.

---

## 13. Changes to this policy

If this policy changes materially — in particular if the app's data handling ever changes — the
updated policy will be published at https://paulrabiller.github.io/ember-legal/ and shipped in the
app, and you will be asked to review the notification disclosure again before the affected feature
resumes.

---

## 14. Contact

Paul Rabiller
745A Havelock Road, Singapore 169657
contact.app.ember@gmail.com
