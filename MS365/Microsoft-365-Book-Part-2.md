# Microsoft 365 for IT Support
## Part 2 — Managing Users and Mailboxes: Lifecycle, Aliases, Delegation, Groups and Shared Mailboxes

---

## Preface to Part 2

Part 1 covered what Microsoft 365 is, how licensing works, how to connect a domain, how to create users and how to get people signed in with MFA. That's enough to open the door.

**Part 2 is where the real day-to-day job lives.** Once users exist, IT support spends its time answering questions like:

- *"Someone left the company. What do I do with their account?"*
- *"We need a finance@ address, but we don't want to pay for another licence."*
- *"My manager's assistant needs to read his email, but he won't share his password."*
- *"Customers email support@ and we want every reply to come from support@, not from individual staff."*
- *"I can open my email in the app but not in the browser. Why?"*

This part answers all of those. It follows the second class of the course and expands each topic into a chapter.

### How this book is organised

Each chapter contains:

- **What you will learn:** the goals of the chapter.
- **The explanation:** the main content, in plain language.
- 💡 **Explain it like this:** analogies you can use when teaching.
- 🛠️ **Hands-on:** step-by-step tasks.
- 🏢 **In the real world:** how the topic appears in an actual IT job.
- 🎯 **Interview corner:** what employers ask and how to answer.
- ✅ **Check your understanding:** questions with answers at the end of the chapter.

Chapter numbering continues from Part 1, so this part starts at Chapter 14. The examples again use the fictional company **Contoso** (`contoso.com`), the same example company Microsoft uses in its own documentation.

---

## Contents

14. [The User Lifecycle: Onboarding and Offboarding](#chapter-14--the-user-lifecycle-onboarding-and-offboarding)
15. [Email Aliases](#chapter-15--email-aliases)
16. [The User Page: Every Setting Explained](#chapter-16--the-user-page-every-setting-explained)
17. [Admin Roles in Practice](#chapter-17--admin-roles-in-practice)
18. [Office Apps: Installing, Activating and Supporting](#chapter-18--office-apps-installing-activating-and-supporting)
19. [Controlling How Users Reach Their Mailbox](#chapter-19--controlling-how-users-reach-their-mailbox)
20. [Email Forwarding and Automatic Replies](#chapter-20--email-forwarding-and-automatic-replies)
21. [The Global Address List and Protecting Executives](#chapter-21--the-global-address-list-and-protecting-executives)
22. [Mailbox Delegation](#chapter-22--mailbox-delegation)
23. [Mailbox Housekeeping: Restrictions, Size and Archiving](#chapter-23--mailbox-housekeeping-restrictions-size-and-archiving)
24. [Groups: Microsoft 365 Groups and Distribution Lists](#chapter-24--groups-microsoft-365-groups-and-distribution-lists)
25. [Shared Mailboxes](#chapter-25--shared-mailboxes)
26. [Choosing the Right Tool](#chapter-26--choosing-the-right-tool)
27. [Career: Scenarios and Interview Practice](#chapter-27--career-scenarios-and-interview-practice)

Appendices
- [D. Quick Reference: Where Every Setting Lives](#appendix-d--quick-reference-where-every-setting-lives)
- [E. Glossary for Part 2](#appendix-e--glossary-for-part-2)
- [F. Lab Workbook for Part 2](#appendix-f--lab-workbook-for-part-2)

---

# Chapter 14 — The User Lifecycle: Onboarding and Offboarding

### What you will learn
- Why licences must be watched constantly
- The correct offboarding procedure
- Why you must never delete a leaver's account
- What happens to data when an account is deleted

## 14.1 The lifecycle

Every staff member's account goes through the same journey:

```
   Hire                    Employment                       Leave
    │                          │                              │
    ▼                          ▼                              ▼
 Create user            Reset passwords                 Remove licence
 Assign licence         Change job title / manager       Remove roles
 Guide first sign-in    Add aliases, groups              Block sign-in
 Set up Outlook         Add or remove permissions        Preserve the data
```

Part 1 covered the left side. This chapter covers the right side, which is the part new IT staff most often get wrong.

## 14.2 Licences are money

A licence is charged **every month, per user**. Nothing stops you creating fifty users and licensing them all. The bill simply grows.

> 💡 **Explain it like this:** *"If you go to a restaurant and your child orders food while you're in the restroom, you still pay the bill. Once it's ordered, it's ordered."* In the cloud, everything you switch on is charged until you switch it off.

This is why a business **watches its licences constantly**, and why unlicensing a leaver is the **first** step of offboarding, not the last.

🛠️ **Hands-on: remove a licence**
**Users → Active users → [user] → Licenses and apps →** untick the licence → **Save changes**.

You can also do it for several users at once: tick them in the list → **… → Manage product licences → Replace/Remove**.

## 14.3 Offboarding: the three minimum steps

When someone leaves, do these in order:

| Step | Action | Why |
|---|---|---|
| **1** | **Remove the licence** | Stops the monthly charge immediately |
| **2** | **Remove all admin roles** | They must not keep any permissions |
| **3** | **Block sign-in** | They can no longer access anything |

**Blocking sign-in** is under **Users → Active users → [user] → Block sign-in**. It's also wise to **sign them out of all sessions** (Chapter 16), because an already-open session can survive for a while.

## 14.4 Never delete the account

This is the rule the instructor repeated most often: **"We never delete the account."**

**What you lose if you delete it:**

| Data | Why it matters |
|---|---|
| **Mailbox** | Years of conversations with customers and suppliers, written **on behalf of the company** |
| **OneDrive files** | The person's work documents |
| **SharePoint contributions** | Documents and site permissions |
| **Teams chats** | Conversations and decisions |
| **Settings and licences history** | Rebuilding is painful |

> **The key idea:** that email was never personal. The employee wrote it as a representative of the company, so **the company is responsible for it and owns it.**

**What Microsoft tells you when you delete:** the account and its data can be **restored for 30 days**. After that, it's gone. Even inside those 30 days, the address, aliases and permissions aren't simply available for someone else to use.

**A blocked, unlicensed account costs nothing.** Leave it in place. Two years later you can re-enable it, add a licence and reuse it if needed.

## 14.5 Preserving a leaver's data

Blocking the account keeps the data, but colleagues often still need access to it. You have several options, each covered later in this book:

| Need | Solution | Chapter |
|---|---|---|
| A colleague must **receive** the leaver's new email | **Email forwarding** | 20 |
| A colleague must **read** the leaver's old email | **Mailbox delegation** (Read and manage) | 22 |
| The team must **keep using the address** and reply from it | **Convert to a shared mailbox** | 25 |
| The company must **keep** the mailbox for legal reasons | Archive or retention policy | 23 |
| The leaver's **files** must be handed over | Transfer OneDrive ownership to the manager | 16 |

A common company policy is to keep the blocked account for **90 days**, take a backup or archive of the mailbox, hand the files to the manager, and only then delete it.

> 🏢 **In the real world:** offboarding is often an official checklist signed off by HR. Getting it wrong is serious: a leaver who can still sign in is a security incident, and a deleted mailbox can be a legal problem.

> 🎯 **Interview corner:** *"An employee resigned today. Walk me through what you do."*
> **Good answer:** "First I remove their licence, so the company stops paying. Then I remove any admin roles, block their sign-in and sign them out of all sessions. I don't delete the account, because that would destroy the mailbox, OneDrive files and Teams chats, and that data belongs to the company. Depending on the handover, I'd set up forwarding to their manager, give the manager Read and manage permission on the mailbox, or convert it to a shared mailbox. We'd only delete it after the retention period, once everything is archived."

### ✅ Check your understanding
1. What are the three minimum offboarding steps, in order?
2. Why is removing the licence first?
3. Name four things you lose by deleting an account.
4. How long can a deleted user be restored?
5. Does a blocked, unlicensed account cost anything?

**Answers:** (1) Remove the licence, remove roles, block sign-in. (2) The company is charged monthly per licence. (3) Any four of: mailbox, OneDrive files, SharePoint documents, Teams chats, settings. (4) 30 days. (5) No.

---

# Chapter 15 — Email Aliases

### What you will learn
- What an alias is and what it can't do
- How to add and verify aliases
- Why businesses rely on them

## 15.1 What is an alias?

An **alias** is an **extra email address attached to an existing mailbox**. Email sent to the alias lands in that same mailbox.

Bipin works in finance. His address is `bipin@contoso.com`. The company also wants customers to write to `finance@contoso.com`. Two ways to do that:

| Option | Cost | Work |
|---|---|---|
| Create a **new user** called finance | **Another licence, every month** | Someone must sign in to a second account |
| Add **finance@** as an **alias** of Bipin | **Free** | Nothing. It arrives in his normal inbox. |

> 💡 **Explain it like this:** *"An alias is a nickname. People might call me by my name, or 'the tutor', or 'the owner'. Whatever they call me, it reaches the same person. But when I answer, my real name is what they see."*

## 15.2 The rules

| Question | Answer |
|---|---|
| Does it need a licence? | **No. Aliases are free.** |
| Does it have its own mailbox? | **No.** That's the point: mail goes to the owner's mailbox. |
| Can it receive email? | **Yes.** |
| Can the user **send or reply** from it? | **No.** Replies go out from the **primary address**. |
| Can you sign in with it? | **No.** |
| Can two people share an alias? | **No.** Every address in the tenant must be unique. |
| How many aliases per user? | Many. |
| Does it appear in the Exchange mailbox list? | **No**, because it isn't a mailbox. |

> ⚠️ **One way only.** This is the single most important fact about aliases, and the most common exam and interview question. **Incoming: yes. Outgoing: no.**

📘 **Advanced note:** Microsoft does offer an optional organisation setting that lets users send from an alias. It's **off by default**, and most companies leave it off. For your course, your exam and your first job, treat an alias as **receive only**. When a department genuinely needs to *reply* from a shared address, the right answer is a **shared mailbox** (Chapter 25).

## 15.3 Adding an alias

🛠️ **Hands-on**

1. **Users → Active users →** click the user.
2. Open **Manage username and email** (the email aliases section).
3. Type the alias, e.g. `finance`, choose the domain, and **Add**.
4. Repeat for more aliases, e.g. `sales`.
5. **Save changes.** It can take a few minutes to apply.

🛠️ **How to verify it worked**
Start a new email and type **`finance`** in the **To** box. If **the owner's name** appears in the suggestion, the alias is attached to that person. Then send a test message and check it arrives in their inbox.

**Removing an alias:** the same page has a delete option next to each address. Removing an alias frees the address for use elsewhere.

## 15.4 Why businesses love aliases

Look at almost any company's *Contact us* page. You'll see `info@`, `sales@`, `support@`, `accounts@`, `careers@`, often plus one address per city or branch: `sydney@`, `melbourne@`, `brisbane@`.

From the outside, the company looks large and well organised, with a department for everything. From the inside, **many of those addresses can be aliases pointing to a handful of real mailboxes**.

The instructor showed a real estate company whose website lists an address for every suburb. Each one simply delivers to the agent who covers that area. **Nobody pays for extra licences just to have extra addresses.**

**Aliases work beautifully with rules** (Part 1, Chapter 11). Create a rule so that anything sent to `finance@` goes to a Finance folder, and anything sent to `sales@` goes to a Sales folder. One mailbox, neatly sorted.

## 15.5 A related limit: one domain, one mail provider

A student asked whether the same domain could use Microsoft 365 **and** Gmail at the same time. **No.** The domain's **MX record** points to one mail system. *"One name must be unique all over the world."*

### ✅ Check your understanding
1. What is an alias, in one sentence?
2. Does an alias cost anything?
3. Can a user reply from their alias?
4. Can two users have the same alias?
5. Why don't aliases show up in the Exchange mailbox list?
6. A department needs to both receive **and** reply from `support@`. Is an alias the right answer?

**Answers:** (1) An extra email address for an existing mailbox. (2) No. (3) No, replies come from the primary address. (4) No, addresses must be unique. (5) Because an alias isn't a mailbox. (6) No. That needs a shared mailbox.

---

# Chapter 16 — The User Page: Every Setting Explained

### What you will learn
- What each setting on a user's page does
- Which ones you'll use daily in support
- Why the manager field matters more than it looks

Everything here is under **Users → Active users → [click a user]**.

## 16.1 Identity and profile

| Setting | Use |
|---|---|
| **Profile photo** | The photo follows the account **everywhere**: Outlook, Teams, SharePoint. Another everyday example of single sign-on. |
| **Display name, job title, department, office, phone** | Keeps the company directory accurate. **Maintaining this is part of the IT job.** |
| **Username / email address** | Fix a typo, or move a user to a different domain. Large companies often own **several domains** for their brands and franchises, e.g. separate domains for each branch of a chain. |
| **Aliases** | Chapter 15. |

## 16.2 Access and security

| Setting | Use |
|---|---|
| **Reset password** | The most common helpdesk request of all |
| **Block sign-in** | Offboarding, or an account you suspect is compromised |
| **Sign out of all sessions** ⭐ | Signs the account out of **every device, everywhere** |
| **Sign-in activity** | The last **30 days** of sign-ins. For the full history use **Entra ID → user → Sign-in logs**, which shows each attempt, the app, the location and whether it succeeded. |
| **Manage multifactor authentication** | Opens the per-user MFA page in Entra ID |
| **Delete user** | Avoid. See Chapter 14. |

### Sign out of all sessions: the one to remember

> 💡 **Explain it like this:** *"You signed in at a friend's house and you think you forgot to sign out. You're not sure. From home, you sign out of everything with one click."*

**The real reason it exists is lost devices.** If a staff member loses a work phone or laptop:

1. **Sign out of all sessions** so the open sessions die.
2. **Reset the password** so the stored password no longer works.
3. **Block sign-in** if the person can't be reached or the device may be in the wrong hands.
4. (With Intune, later in the course, you can also **remotely wipe** the device.)

> *"A laptop is one or two thousand dollars. That's nothing for the company. **Losing the data** is what matters."*

📘 **Note:** sign-out revokes the sessions, but an app holding a valid token can keep working for up to about an hour. Resetting the password as well closes that gap.

## 16.3 Contact and organisation

| Setting | Use |
|---|---|
| **Alternate email address** | A **personal** address for the user, used when they can't reach their work email, e.g. to send them account details or reach them on leave |
| **Groups** | Which groups the user belongs to (Chapter 24) |
| **Manager** ⭐ | The user's line manager |

### Why the manager field matters

It looks like a cosmetic field. It isn't. It's your **approval trail**.

> *"Someone keeps asking you for access to something. Do you just grant it? Impossible. If you're not sure, CC their manager: 'Your staff member is asking for this access, are you aware?' If the manager approves, you grant it, and you have proof. You're on the safe side. The manager is responsible."*

This habit protects you. **IT should never grant access to sensitive data on a user's word alone.**

## 16.4 The other tabs

| Tab | Contents |
|---|---|
| **Licenses and apps** | Assign or remove licences, and switch **individual apps** on or off. A Business Premium licence contains dozens of apps, and companies often untick the ones staff don't need. |
| **Mail** | The mail settings chapters: email apps (19), forwarding and automatic replies (20), global address list (21), delegation (22), aliases (15), convert to shared mailbox (25) |
| **OneDrive** | Storage used, access to the files, and the **retention period** for the OneDrive of a deleted user (30 days by default; an admin can extend it) |
| **Office apps** | Which devices have Office activated (Chapter 18) |
| **Devices** | Intune, covered later in the course |

### ✅ Check your understanding
1. A user lost their work phone. What three things do you do immediately?
2. Where do you see more than 30 days of sign-in history?
3. Why should you record a user's manager?
4. What is the alternate email address for?
5. Where does a user's profile photo appear?

**Answers:** (1) Sign out of all sessions, reset the password, block sign-in if needed. (2) Entra ID → the user → Sign-in logs. (3) So you can get approval before granting access, which gives you a documented trail. (4) A personal address to contact them when they can't use work email. (5) Everywhere: Outlook, Teams, SharePoint.

---

# Chapter 17 — Admin Roles in Practice

### What you will learn
- What a user without a role actually sees
- How to compare roles before assigning one
- Job-specific roles beyond the three main ones

Part 1, Chapter 12 introduced Helpdesk, User and Global Administrator. This chapter is about using roles in practice.

## 17.1 A user with no role

Sign in as a normal user and go to **admin.microsoft.com**. You get:

> *"You don't have permission to view or manage this page. Switch to an account that has permission."*

**This is correct and intended.** Normal staff must never reach the admin center.

> 🏢 **Try it yourself.** Keep a **test user with no role** in your tenant. Whenever you change a setting, sign in as them in a private window and see the result from the user's side. It's the fastest way to learn, and it stops you telling a user "it should work" when it doesn't.

## 17.2 Job-specific roles

Roles aren't only for general IT staff:

| Role | Typical holder | Notes |
|---|---|---|
| **Billing Administrator** | The **accountant** | They can pay the bills and manage subscriptions, **but get no other admin rights** |
| **Exchange Administrator** | Email specialist | Manages mailboxes and mail flow. *"If you get the Exchange admin role, you cannot see Teams."* |
| **SharePoint Administrator** | Files and intranet specialist | SharePoint and OneDrive only |
| **Teams Administrator** | Teams and telephony specialist | Teams only |
| **Global Reader** | Auditors, trainees | Can see everything, change nothing |

This is the **principle of least privilege** in action: each person gets the smallest role that does their job.

## 17.3 What a Helpdesk Administrator can really do

After assigning the Helpdesk Administrator role to the test user, the class signed in again. The user **could** open the admin center, but:

| Can | Cannot |
|---|---|
| **Reset passwords** for non-admin users | **Create** users |
| **Re-authenticate** users (force MFA re-registration, sign-out) | **Delete** users |
| **Manage service requests** with Microsoft | **Add multiple users / templates** |
| **Monitor service health** | Manage licences, groups or billing |

📘 **Note:** role changes take a few minutes to apply. If the dashboard doesn't appear, wait, then sign out and in again.

## 17.4 The compare roles tool 📌

Instead of memorising permissions, let the portal show you.

🛠️ **Hands-on**
1. **Roles → Role assignments**.
2. **Tick up to three roles**, e.g. Helpdesk Administrator, User Administrator and Global Administrator.
3. Click **Compare roles**.
4. Read the table. Each permission has a tick or a cross per role.

**Do this before assigning any role you're unsure about.** It's also excellent interview preparation, because you can describe real differences rather than vague ones.

### ✅ Check your understanding
1. What does a user with no admin role see at admin.microsoft.com?
2. Which role suits an accountant who only pays invoices?
3. Can an Exchange Administrator manage Teams?
4. Name two things a Helpdesk Administrator cannot do.
5. How do you compare what three roles can do?

**Answers:** (1) A message saying they don't have permission and should switch accounts. (2) Billing Administrator. (3) No. (4) Any two of: create users, delete users, manage licences, manage groups, manage billing. (5) Roles → Role assignments → tick up to three → Compare roles.

---

# Chapter 18 — Office Apps: Installing, Activating and Supporting

### What you will learn
- How users install Office themselves
- How to check which devices have Office activated
- How to deactivate an installation

## 18.1 "Word isn't working"

This is a routine support call. Before troubleshooting the app, check the basics:

1. **Does the user have a licence that includes desktop apps?** Business **Basic** doesn't. Standard and Premium do.
2. **Have they actually installed Office?**
3. **Have they signed in to Office so it's activated?**

The admin center answers questions 2 and 3 for you.

## 18.2 Checking activations

🛠️ **Hands-on**
**Users → Active users → [user] → Office apps**

You'll see each device where the user has installed and activated Office, including the **device name** and **operating system**.

In class, the test user's activation appeared after signing in, and the device name matched the PC. (You can check a PC's name with the `hostname` command in Command Prompt.)

**Nothing listed** means they haven't installed or activated it, and that's your answer.

## 18.3 Helping a user install Office

🛠️ **Hands-on (the user does this on their own computer)**
1. Sign in at **office.com** (or outlook.office.com, or any Microsoft 365 site).
2. Open the **app launcher** (the grid icon) or **More apps**.
3. Choose **Install apps** → **Microsoft 365 apps**.
4. Run the downloaded installer.
5. Open Word and **sign in with the work account** so it activates.

> *"Later we'll push this software from **Intune**."* In a managed company, apps are deployed automatically to devices, and users never install anything by hand. Manual installation is still useful for one or two machines, or after a reinstall or crash.

## 18.4 Deactivating a device 📌

The same **Office apps** page lets you **sign out of / deactivate** a device.

**Why it matters:** a licence allows a limited number of installations. If someone has left the company, or is using an old personal computer, deactivate it. *"Otherwise he can use this service forever."* Deactivation is also part of a thorough offboarding.

### ✅ Check your understanding
1. Which Business licence does **not** include desktop Office apps?
2. Where do you check which devices have Office activated?
3. What are the steps for a user to install Office manually?
4. Why would you deactivate an Office installation?

**Answers:** (1) Business Basic. (2) Users → Active users → the user → Office apps. (3) Sign in at office.com → app launcher / More apps → Install apps → run the installer → sign in to activate. (4) The user has left, or is using a device they shouldn't, or has used up their installs.

---

# Chapter 19 — Controlling How Users Reach Their Mailbox

### What you will learn
- The different ways a mailbox can be reached
- How to allow or block each one
- A classic interview question

## 19.1 Many doors into one mailbox

A mailbox can be opened in several ways, and each can be allowed or blocked **per user**:

| Protocol / app | What it is |
|---|---|
| **Outlook on the web (OWA)** | Email in a browser at outlook.office.com |
| **Outlook desktop (MAPI)** | The installed Outlook app |
| **Exchange ActiveSync** | Phone and tablet mail apps |
| **Outlook mobile** | The Outlook app on iPhone and Android |
| **IMAP / POP** | Older mail protocols, often disabled for security |

## 19.2 Blocking an app

🛠️ **Hands-on**
**Users → Active users → [user] → Mail → Manage email apps** → untick the apps to block → **Save**.
(The same settings live in the **Exchange admin center → Recipients → Mailboxes → [user] → Email apps**.)

The class unticked **Outlook on the web** for a test user. A few minutes later that user could no longer open outlook.office.com, while the desktop app and the admin center still worked normally.

> **Important:** you are blocking **a way of reading the mailbox**, not the mailbox itself. Mail still arrives and can still be read by the other apps.

📘 **Notes:**
- Changes take **a few minutes**. Browser cache can hide the effect, so test in a **private window**.
- Modern companies often do this with **Conditional Access** in Entra ID instead, because it can apply rules by group, device and location rather than user by user. The per-user setting is still what you'll meet on a small tenant, and it's what interviewers ask about.

## 19.3 Why a business would do this

- **Security:** stop staff reading company email on unmanaged personal phones.
- **Compliance:** some organisations forbid webmail on public computers.
- **Legacy protocols:** IMAP and POP are frequently disabled because they don't support modern authentication well.

> 🎯 **Interview corner:** *"A user says they can't open their email in a web browser, but it works fine in the desktop app and on their phone. What's the cause?"*
> **Good answer:** "Outlook on the web is blocked for that mailbox in the email apps settings. I'd check Users → the user → Mail → Manage email apps, or the same setting in the Exchange admin center, and confirm whether it was blocked deliberately by policy before re-enabling it."

### ✅ Check your understanding
1. Name four ways a mailbox can be reached.
2. If you block OWA, can the user still get email?
3. Where do you change these settings?
4. Why might a company block ActiveSync?

**Answers:** (1) Any four of: Outlook on the web, Outlook desktop, ActiveSync, Outlook mobile, IMAP, POP. (2) Yes, mail still arrives and other apps still work. (3) Users → the user → Mail → Manage email apps, or the Exchange admin center. (4) To stop company email being read on unmanaged personal devices.

---

# Chapter 20 — Email Forwarding and Automatic Replies

### What you will learn
- How to forward a mailbox, with or without keeping a copy
- When to use each option
- How to set an out-of-office for someone else

## 20.1 Email forwarding

**Forwarding** sends a copy of every incoming message to another address.

🛠️ **Hands-on**
**Users → Active users → [user] → Mail → Manage email forwarding**
1. Turn on **Forward all emails sent to this mailbox**.
2. Type the **forwarding address**.
3. Decide about **"Keep a copy of forwarded email in this mailbox"**.
4. **Save.**

## 20.2 The two cases

| | **Case 1: on holiday** | **Case 2: left the company, or completely off** |
|---|---|---|
| Situation | The person wants cover while away, but wants to see what happened when they return | The person is gone, or wants no trace of work during leave |
| Keep a copy | ✅ **Tick it** | ❌ **Leave it unticked** |
| Result | **Both** mailboxes get every message | **Only the other person** gets the message |

The class tested both and saw exactly that.

> *"If you keep one copy, when you come back from holiday you know everything that happened. If you don't, it's completely blind."*

📘 **Notes:**
- Forwarding to another **internal** address always works.
- Forwarding to an **external** address (Gmail, Yahoo) is often **blocked by policy**, because attackers who compromise an account commonly set up external forwarding to quietly steal mail. Many tenants block it by default, and security teams **alert** on it.
- Forwarding is handy for a leaver, but if the whole team needs the address long term, **convert the mailbox to a shared mailbox** (Chapter 25).

## 20.3 Automatic replies for another user

In Part 1 users set their own out-of-office in Outlook. But what if they're **already on holiday** and phone you from the airport? You can't sign in as them, because **you must never know their password**.

🛠️ **Hands-on**
**Users → Active users → [user] → Mail → Manage automatic replies**
- Turn it on, set the dates, and write the message for **inside** and **outside** the organisation.

**The admin can do this for any user without their password.** It's one of the small things that makes users trust IT.

### ✅ Check your understanding
1. Which setting decides whether the original mailbox still receives its mail?
2. Which case should not keep a copy?
3. Why is external forwarding often blocked?
4. A user is already on holiday and forgot their out-of-office. What do you do?

**Answers:** (1) "Keep a copy of forwarded email in this mailbox". (2) Case 2: the person has left or wants to be completely off. (3) Attackers use it to steal mail from compromised accounts. (4) Set it for them from Users → the user → Mail → Manage automatic replies.

---

# Chapter 21 — The Global Address List and Protecting Executives

### What you will learn
- What the global address list is
- How and why to hide a user from it
- Why executives use a different email pattern

## 21.1 The global address list (GAL)

The **GAL** is the company directory built into Outlook. Any user can browse it and see every colleague's name and email address.

In Outlook on the web: **People → search, or the "All company" / directory view.**

It's genuinely useful. It's how staff find each other without asking. But not everyone should be in it.

## 21.2 Hiding a user

🛠️ **Hands-on**
**Users → Active users → [user] → Mail →** untick **Show in global address list** → **Save**.
(Also available in the **Exchange admin center**.)

It takes a **couple of minutes** to apply. The class refreshed the directory and the name had gone.

**Who gets hidden, and why:**

| Who | Reason |
|---|---|
| **CEO, CFO, directors** | So ordinary staff can't email them directly. *"Otherwise they email the manager asking for a pay rise while he's on holiday."* Requests should go through the **line manager**. |
| **Service and system accounts** | They aren't people and shouldn't clutter the directory |
| **Shared mailboxes that only one team uses** | Keeps the directory clean |

> ⚠️ **Hiding is not blocking.** The mailbox still works, and anyone who **knows** the address can still email it. You've only removed it from the list. To actually stop specific senders, use **delivery restrictions** (Chapter 23).

## 21.3 Why executives use a different address pattern 📌

Most companies use one predictable pattern, such as `firstname@contoso.com`. That's convenient, but it means **anyone can guess any address**.

For the CEO, CFO and directors, companies often use a **different pattern**, e.g. `lastname.firstname@contoso.com`.

**Why:** executives are the main target of **phishing** and **business email compromise**, where an attacker pretends to be the CEO and asks the finance team to pay an invoice. If the address can't be guessed, the attacker's job is harder.

> 🏢 **In the real world:** hiding an executive from the GAL and giving them an unusual address pattern are small, cheap steps that genuinely reduce risk. They're often written into a company's security policy.

### ✅ Check your understanding
1. What is the GAL?
2. How do you hide a user from it?
3. If someone is hidden, can they still receive email?
4. Why does a CEO often have a different address pattern?

**Answers:** (1) The company directory of users inside Outlook. (2) Users → the user → Mail → untick "Show in global address list". (3) Yes, if the sender knows the address. (4) So attackers can't guess it and send phishing or CEO-fraud emails.

---

# Chapter 22 — Mailbox Delegation

### What you will learn
- Why delegation exists
- The three delegation permissions
- Which one to recommend, and why

## 22.1 The problem

A senior manager receives hundreds of emails a day and has an assistant who handles most of them. The assistant needs access to the mailbox.

**The obvious answer, sharing the password, is wrong.** With single sign-on, that one password opens email, files, Teams, and everything else. **Passwords are never shared.**

**Delegation** gives someone access to a **mailbox only**, using their **own** account and their **own** MFA.

## 22.2 The three permissions

🛠️ **Where:** **Users → Active users → [mailbox owner] → Mail → Manage mailbox delegation**

| Permission | What the delegate can do | What the recipient sees |
|---|---|---|
| **Read and manage** (Full Access) | Open the mailbox, **read, organise and delete**. **Cannot send.** | — |
| **Send as** | Send email **as the mailbox itself** | Only the **owner's** name. Nobody can tell someone else sent it. |
| **Send on behalf** | Send with both identities shown | **"Assistant on behalf of Manager"** |

### Read and manage
The assistant reads everything, files it, deletes junk, and flags what matters. *"You can read everything, mark the important ones and tell me. But you cannot reply."*

In class, the delegate opened the manager's mailbox, read and deleted messages, but **got an error when trying to send**.

### Send as
The message looks **exactly** as if the owner wrote it.

> 💡 **Explain it like this:** *"If someone sits at my desk and types 'no class today', everyone thinks I sent it."*

Powerful, and **risky**. If the delegate writes something wrong, **the owner is responsible**, and there's no visible trace of who actually typed it. Give it only to people who are completely trusted.

### Send on behalf ⭐ the safest choice
The recipient sees both names: the assistant sent it, with the manager's authority.

> 💡 **Explain it like this:** *"When a head of state wishes everyone a happy holiday, the secretary typed and sent it, but the message belongs to the leader. Everyone understands that, and nothing is hidden."*

## 22.3 Using a delegated mailbox

Once the permission applies (it can take a while, up to about an hour):

- In **Outlook on the web**, open the other mailbox from the profile menu (**Open another mailbox**). The address bar then shows **the other person's mailbox**, even though you're signed in as yourself.
- In **Outlook desktop**, a mailbox you have Full Access to usually appears **automatically** in the folder list.
- To send as or on behalf of the mailbox, show the **From** field in a new message and pick the other address.

## 22.4 Where else delegation is used

- The **assistant / executive** pattern above.
- Giving a manager access to a **leaver's** mailbox (Chapter 14).
- Team access to a **shared mailbox**, which is really the same permissions applied to a mailbox with no owner (Chapter 25).

> 🎯 **Interview corner:** *"What's the difference between Send as and Send on behalf?"*
> **Good answer:** "With Send as, the message looks as if the mailbox owner sent it, so the recipient can't tell who really wrote it. With Send on behalf, the recipient sees 'the delegate on behalf of the owner', so it's transparent. I'd normally recommend Send on behalf, and only use Send as when the business specifically wants the sender hidden, for example replies from a department address."

### ✅ Check your understanding
1. Why not just share the manager's password?
2. Which permission lets someone read but not send?
3. With Send as, what does the recipient see?
4. Which permission is the most transparent and usually the safest?
5. How does the delegate open the mailbox?

**Answers:** (1) With SSO the password opens everything, not just email, and passwords must never be shared. (2) Read and manage. (3) Only the mailbox owner's name. (4) Send on behalf. (5) It appears in Outlook desktop automatically, or they use Open another mailbox in Outlook on the web.

---

# Chapter 23 — Mailbox Housekeeping: Restrictions, Size and Archiving

### What you will learn
- How to control who may email a mailbox
- How message size limits work
- What archiving is and when to enable it
- OneDrive retention for leavers

Most of these live in the **Exchange admin center** (**admin.exchange.microsoft.com → Recipients → Mailboxes → [user]**), and some are mirrored in the Microsoft 365 admin center's **Mail** tab.

## 23.1 Delivery restrictions

You can control **who is allowed to send email to a mailbox**: accept mail only from certain senders or groups, or reject mail from specific senders.

**Real use:** protecting senior managers, so requests go through the **line manager** instead of landing on the boss's desk. The class blocked two senders from a test mailbox, and their messages were rejected.

📘 **Note:** the blocked sender receives a delivery failure, so they know. Use this deliberately, as company policy, not as a personal favour.

## 23.2 Message size limits

Every mailbox has a maximum **send** and **receive** message size.

- The class set the limit to a tiny value and the sender immediately got **"delivery has failed to this recipient because of size"**.
- For comparison, **Gmail's limit is 25 MB**, and beyond that Google turns the attachment into a **Drive link**. Microsoft 365 behaves the same way with **OneDrive**.

📘 **Note:** Exchange Online's default is **35 MB**, and the maximum you can set is **150 MB**. Because of encoding overhead, the practical limit is lower than the number suggests.

> 🏢 **The right answer for big files is a link, not an attachment.** Teach users to upload to OneDrive or SharePoint and share a link. It's faster, it doesn't fill mailboxes, and access can be revoked later.

## 23.3 Archiving

**"If the mailbox is full, enable the archive."**

An **online archive** is a second storage area attached to the mailbox. In Outlook it appears as an extra set of folders. A **retention policy** moves older mail into it automatically.

- It **frees space in the main mailbox** while keeping everything searchable.
- It's the standard answer to *"my mailbox is full"*, along with clearing very large attachments.
- 📘 **Note:** the default policy moves items older than **two years** into the archive, and an admin can change that. In Business Premium and the Enterprise plans, archiving can also **auto-expand** as it fills.

> 💡 **Explain it like this:** *"It's like compressing a folder in Windows. Nothing is lost, it's just stored more efficiently and out of your way."*

## 23.4 OneDrive retention

On the user's **OneDrive** tab you can see their storage (**1 TB** by default), reach their files, and set the **retention period for a deleted user's OneDrive**.

- The default is **30 days** after the account is deleted.
- An admin can extend it, which is useful when a leaver's files may be needed later.
- **Better practice:** before deleting anyone, hand their OneDrive over to their **manager**.

### ✅ Check your understanding
1. What are delivery restrictions used for?
2. What's Gmail's attachment limit, and what does Google do above it?
3. What is Exchange Online's default message size limit?
4. A user says their mailbox is full. What do you suggest?
5. How long is a deleted user's OneDrive kept by default?

**Answers:** (1) Controlling who may send email to a mailbox, often to protect senior managers. (2) 25 MB, then it becomes a Google Drive link. (3) 35 MB (up to 150 MB maximum). (4) Enable the online archive, and clear or relocate very large attachments. (5) 30 days, and it can be extended.

---

# Chapter 24 — Groups: Microsoft 365 Groups and Distribution Lists

### What you will learn
- Why group email exists
- The difference between a Microsoft 365 group and a distribution list
- Where email to a group actually lands

## 24.1 The purpose of group email

*"I want to send one email to everybody at the same time. That is group email."*

One address, many recipients. Every member receives the message, each one replies individually, and everyone can see who replied.

## 24.2 Microsoft 365 group (with Teams)

🛠️ **Hands-on**
**Teams & groups → Active teams & groups → Add a group → Microsoft 365 (with Teams)**
1. Give it a **name** and **description**.
2. Add **owners** (who manage it) and **members**.
3. Set the **group email address**.
4. Choose whether people can **join without approval** or need the owner's approval.
5. **Create.**

**What you get:**
- ✅ a **group email address**
- ✅ a **group in Microsoft Teams** with chat and calls
- ✅ a **separate group mailbox**, and this is the part that surprises people

> ⚠️ **Mail sent to a Microsoft 365 group does not arrive in each member's inbox.** It goes to the **group mailbox**, which appears under **Groups** in Outlook. In class, members looked in their own inbox and thought the email had failed. It was in the group.

- ⚠️ **External senders are blocked by default.** To allow them: group **Settings → "Let people outside the organisation email this group"**.

A Microsoft 365 group also brings a **SharePoint site**, a **shared calendar** and **Planner**, which is why it's the collaboration option.

## 24.3 Distribution list

🛠️ **Hands-on**
**Teams & groups → Add a group → Distribution list** → name it, add owners and members → **Create**.

**What you get:**
- ✅ a **group email address**
- ✅ mail arrives in **each member's own inbox**
- ❌ **no Teams group**
- ❌ **no group mailbox**
- ✅ external senders allowed

It's the simplest option: a mailing list, nothing more. `allstaff@contoso.com` is the classic example.

## 24.4 Comparison

| | **Microsoft 365 group** | **Distribution list** |
|---|---|---|
| Email address | ✅ | ✅ |
| Where mail lands | **Group mailbox** (Groups in Outlook) | **Each member's inbox** |
| Teams group and chat | ✅ | ❌ |
| SharePoint site, shared calendar | ✅ | ❌ |
| External senders | Blocked by default | Allowed |
| **Reply appears to come from** | **The individual** | **The individual** |
| Licence needed | No | No |

**The last row is the important one.** With both types, a reply goes out **in the replying person's own name**. For a department that must answer as the department, you need the next chapter.

### ✅ Check your understanding
1. Where does email to a Microsoft 365 group land?
2. Where does email to a distribution list land?
3. Which type creates a Teams group?
4. Why can't a customer email a brand-new Microsoft 365 group?
5. If Anna replies to a message sent to a distribution list, whose name does the recipient see?

**Answers:** (1) In the group mailbox, under Groups in Outlook. (2) In each member's own inbox. (3) The Microsoft 365 group. (4) External senders are blocked by default; the setting must be enabled. (5) Anna's.

---

# Chapter 25 — Shared Mailboxes

### What you will learn
- The problem a shared mailbox solves
- Why it needs no licence and can't be signed in to
- How to create one and add members
- Converting a leaver's mailbox to a shared mailbox

## 25.1 The problem

Five people work on bookings. Customers write to `booking@contoso.com`.

With a **group or distribution list**, incoming mail works fine. But when Anna replies, the customer gets a reply from **Anna**. Tomorrow Ben replies and the customer gets a reply from **Ben**. The conversation fragments, and the customer starts emailing individuals directly.

*"Whoever replies, the reply should go from the same email address, not from the individual's name."*

## 25.2 The solution

A **shared mailbox** is a mailbox that **belongs to no one person**. Several staff open it with their own accounts, and **everything sent from it goes out as the shared address**.

| | **Group / distribution list** | **Shared mailbox** |
|---|---|---|
| Incoming | Everyone receives it | Everyone sees the same inbox |
| **Outgoing** | **The individual's name** | **The shared address** |
| Licence | Not needed | **Not needed** (up to 50 GB) |
| Sign in directly | N/A | **No** |
| Shared Sent items | No | **Yes**, so the team can see what was answered |

## 25.3 Why businesses use them

- **The company answers, not a person.** *"I don't want to put any person in the hassle. The company will be responsible."*
- **Staff change, the address doesn't.** *"Today we hire one person, tomorrow another. I don't want to put the name, I want the department name."*
- **Nothing is missed.** Every member sees the same inbox and the same Sent items, so they know what's already been answered.
- **Privacy for staff.** Outside users can't tell who replied. **IT can**, through the mailbox audit logs, message trace, the sending computer and the IP address.

**Typical shared mailboxes:** `info@`, `support@`, `sales@`, `booking@`, `accounts@`, `careers@`.

**When you don't need one:** a role only one person does, or a tiered helpdesk where level 1, 2 and 3 are deliberately separate people.

## 25.4 Creating a shared mailbox

🛠️ **Hands-on**
1. **Teams & groups → Shared mailboxes → Add a shared mailbox** (or **Exchange admin center → Recipients → Mailboxes**).
2. **Name:** Booking. **Email:** `booking@contoso.com`. **Save.**
3. **Add members.** Adding members through the admin center normally grants both **Read and manage** and **Send as**, which is what makes replies go out from the shared address.
4. **Wait.** The mailbox appears **automatically** in each member's Outlook, below their own mailbox. It can take **30 to 60 minutes**.
5. **Test:** email the shared address from outside, have one member reply, and confirm the reply comes from `booking@`.

📘 **Notes:**
- Automatic appearance ("automapping") happens in **Outlook desktop**. In Outlook on the web, a member can add it manually with **Add shared folder or mailbox**.
- A shared mailbox is free **up to 50 GB**. Beyond that, or if you need an archive or litigation hold, it needs a licence.
- Technically an account exists behind it, but **sign-in is blocked**. Leave it that way.
- A shared mailbox has its own **calendar**, which is ideal for a bookings or on-call rota.

## 25.5 Converting a leaver's mailbox

This closes the loop with Chapter 14, and it's a favourite interview question.

🛠️ **Hands-on**
1. **Users → Active users → [leaver] → Mail → Convert to shared mailbox.**
2. Add the **manager** or the team as members.
3. **Remove the licence.** The mailbox is now shared, so it doesn't need one.

The company keeps every email, the team can still answer anything that arrives, and the monthly cost disappears.

### ✅ Check your understanding
1. What's the one big difference between a group and a shared mailbox?
2. Does a shared mailbox need a licence?
3. Can you sign in to a shared mailbox?
4. How long can it take to appear in Outlook?
5. Can a customer tell which member replied? Can IT?
6. How do you keep a leaver's mailbox without paying for it?

**Answers:** (1) Replies from a shared mailbox go out from the shared address, not the individual's name. (2) No, up to 50 GB. (3) No. (4) Up to about an hour. (5) The customer can't; IT can, through logs and message trace. (6) Convert it to a shared mailbox and remove the licence.

---

# Chapter 26 — Choosing the Right Tool

### What you will learn
- How to pick between alias, forwarding, group, distribution list, shared mailbox and delegation
- The questions to ask before you build anything

## 26.1 The decision guide

Ask these questions in order:

**1. Does the address need to send email, or only receive it?**
- **Receive only** → an **alias** (free, no mailbox).
- **Send too** → keep going.

**2. Does one person handle it, or a team?**
- **One person, permanently** → their own mailbox, maybe with an alias for a friendlier address.
- **A team** → keep going.

**3. Should replies come from the team address, or from the individual?**
- **From the team address** → **shared mailbox**.
- **From the individual** → **Microsoft 365 group** or **distribution list**.

**4. Does the team also need chat and shared files?**
- **Yes** → **Microsoft 365 group** (with Teams).
- **No, just email** → **distribution list**.

**5. Is this about one person helping another with their own mailbox?**
- → **Mailbox delegation** (Read and manage / Send as / Send on behalf).

**6. Is this temporary cover for someone away or gone?**
- → **Forwarding** (with a copy if they want to see it later), or **automatic replies**.

## 26.2 The comparison table

| Tool | Licence | Own mailbox | Can send? | Replies show | Best for |
|---|---|---|---|---|---|
| **Alias** | Free | No | ❌ | The real address | Extra addresses for one person |
| **Forwarding** | — | — | ❌ | — | Temporary cover, leavers |
| **Distribution list** | Free | No | ❌ (it's a list) | The individual | Announcements, `allstaff@` |
| **Microsoft 365 group** | Free | Yes (group) | Members reply individually | The individual | Team collaboration with Teams and files |
| **Shared mailbox** | Free to 50 GB | Yes (shared) | ✅ | **The shared address** | Department addresses: info@, support@ |
| **Delegation** | — | Uses the owner's | ✅ (Send as / on behalf) | The owner, or "on behalf of" | Assistants, leaver handover |

## 26.3 Worked examples

| Requirement | Answer |
|---|---|
| "We want careers@ to reach the HR manager." | **Alias** on the HR manager's mailbox |
| "Everyone in the company must get the fire drill notice." | **Distribution list** (`allstaff@`) |
| "The marketing team wants chat, files and a shared inbox." | **Microsoft 365 group** |
| "Three people answer support@ and customers must always see support@." | **Shared mailbox** |
| "The CEO's assistant reads and sorts his mail, and sometimes writes for him." | **Delegation**: Read and manage plus Send on behalf |
| "Anna left. Her customers still email her." | **Convert to a shared mailbox** (or forward to her replacement) |
| "Ben is on leave for two weeks and Sara is covering." | **Forwarding with a copy** + **automatic replies** |

### ✅ Check your understanding
For each, name the tool: (1) `invoices@` should reach the one accountant. (2) Four people answer `bookings@` and every reply must come from `bookings@`. (3) The project team needs chat, a shared inbox and a document library. (4) The CFO's assistant must write emails that clearly come from the assistant with the CFO's authority. (5) Everyone must receive a company announcement in their own inbox.

**Answers:** (1) Alias. (2) Shared mailbox. (3) Microsoft 365 group. (4) Send on behalf delegation. (5) Distribution list.

---

# Chapter 27 — Career: Scenarios and Interview Practice

## 27.1 What you can now do

- ✅ Offboard a leaver correctly and protect the company's data
- ✅ Create free extra addresses with aliases
- ✅ Manage every setting on a user's page, including lost-device response
- ✅ Assign and compare admin roles
- ✅ Support Office installation and activation
- ✅ Control which apps can reach a mailbox
- ✅ Configure forwarding and out-of-office for other people
- ✅ Hide executives from the directory and explain why
- ✅ Delegate mailbox access safely without sharing passwords
- ✅ Manage mailbox restrictions, size limits and archiving
- ✅ Choose correctly between aliases, groups, distribution lists and shared mailboxes

## 27.2 Scenario practice

Work through these out loud, as if answering an interviewer.

1. **The leaver.** "Sara resigned and finishes today. Her customers email her daily and her manager needs her files." What do you do, and in what order?
2. **The cheap department address.** "We're launching a careers page and need careers@. We're not paying for another licence." What do you set up, and what will you warn them about?
3. **The angry customer.** "A customer says our support replies come from different people every time and nobody knows the history." What's the fix?
4. **The lost laptop.** "An engineer left their laptop in a taxi." What are your first three actions?
5. **The webmail mystery.** "A user can read email on their phone but not in the browser."
6. **The assistant.** "The CFO wants their assistant to handle their mail, but won't share the password, and wants recipients to know the assistant sent it."
7. **The full mailbox.** "A user can't receive email. Their mailbox is full."
8. **The missing group email.** "We created a Microsoft 365 group but nobody receives the emails, and customers get bounce messages."
9. **The pay-rise problem.** "Staff keep emailing the CEO directly."
10. **The holiday cover.** "A manager is on leave for three weeks and wants a colleague to handle their mail, but wants to read what happened when they return."

**Suggested answers**
1. Remove the licence, remove roles, block sign-in, sign out of all sessions. Don't delete. Convert the mailbox to a shared mailbox (or forward to her replacement), give the manager access, and transfer her OneDrive to the manager.
2. An alias on the HR mailbox. Warn them that replies will come from the HR person's own address, not careers@. If replies must show careers@, use a shared mailbox.
3. A shared mailbox for support@, with the team as members. Every reply goes out as support@ and everyone sees the shared inbox and Sent items.
4. Sign out of all sessions, reset the password, block sign-in (and remote-wipe with Intune if the device is managed).
5. Outlook on the web is blocked for that mailbox in the email apps settings.
6. Mailbox delegation: Read and manage plus Send on behalf.
7. Enable the online archive, and check for very large attachments; also review the size limits.
8. Email to a Microsoft 365 group goes to the group mailbox, not personal inboxes. External senders are blocked by default, so tick "Let people outside the organisation email this group".
9. Hide the CEO from the global address list, and consider delivery restrictions so mail must come through the line manager. Use a non-guessable address pattern.
10. Forwarding to the colleague **with** "keep a copy", plus automatic replies set from the admin center.

## 27.3 Interview quick answers

| Question | Short answer |
|---|---|
| What's an alias? | A free extra address on an existing mailbox. Receive only. |
| Alias vs shared mailbox? | An alias can only receive; a shared mailbox can also send as itself. |
| Group vs shared mailbox? | Group replies come from the individual; shared mailbox replies come from the shared address. |
| M365 group vs distribution list? | The group has a Teams group and a group mailbox; a DL just delivers to each member's inbox. |
| Send as vs Send on behalf? | Send as hides the real sender; Send on behalf shows "X on behalf of Y". |
| Offboarding? | Remove licence, remove roles, block sign-in. Never delete. |
| Deleted user restore window? | 30 days. |
| Mailbox full? | Enable the archive. |
| Can't use webmail but apps work? | OWA blocked in email apps settings. |
| Shared mailbox licence? | Free up to 50 GB, and you can't sign in to it. |

**Coming next in the course:** Microsoft Teams and SharePoint, then **Microsoft Intune** for device and application management.

---

# Appendix D — Quick Reference: Where Every Setting Lives

### Users → Active users → [click a user]

| Tab | Settings |
|---|---|
| **Account** | Display name, username, **aliases**, job title, department, **manager**, **alternate email**, **roles**, **sign-in activity**, **sign out of all sessions**, **block sign-in**, delete, profile photo |
| **Licenses and apps** | Assign/remove licences, switch individual apps on and off |
| **Mail** | **Email apps** (block OWA / mobile / desktop), **forwarding**, **automatic replies**, **mailbox delegation**, **aliases**, **show in global address list**, **convert to shared mailbox** |
| **OneDrive** | Storage, access to files, deleted-user retention |
| **Office apps** | Activated devices, deactivate a device |
| **Devices** | Intune (later) |

### Elsewhere in the Microsoft 365 admin center

| Task | Path |
|---|---|
| Set the default domain | Settings → Domains → select → Set as default |
| Compare admin roles | Roles → Role assignments → tick up to 3 → **Compare roles** |
| Create a group | Teams & groups → Active teams & groups → Add a group |
| Allow external email to a group | The group → Settings → "Let people outside the organisation email this group" |
| Create a shared mailbox | Teams & groups → Shared mailboxes → Add a shared mailbox |
| Bulk licences | Users → Active users → select → Manage product licences |

### Exchange admin center (admin.exchange.microsoft.com)

| Task | Path |
|---|---|
| All mailbox settings | Recipients → Mailboxes → [user] |
| Delivery restrictions | Mailbox → Mailbox settings → Delivery restrictions |
| Message size limits | Mailbox → Mailbox settings → Message size restrictions |
| Archive | Mailbox → Others / Manage mailbox archive |
| Shared mailboxes | Recipients → Mailboxes (shared) |
| Message trace | Mail flow → Message trace |

### Entra ID (entra.microsoft.com)

| Task | Path |
|---|---|
| Full sign-in logs | Users → [user] → Sign-in logs |
| Authentication methods / reset MFA | Users → [user] → Authentication methods |
| Per-user MFA | Users → Per-user MFA |

---

# Appendix E — Glossary for Part 2

| Term | Meaning |
|---|---|
| **Alias** | An extra email address for an existing mailbox. Free, receive only. |
| **ActiveSync** | The protocol phone mail apps use to reach a mailbox |
| **Archive (online archive)** | A second storage area for older mail, used when a mailbox fills up |
| **Automapping** | A shared or delegated mailbox appearing automatically in Outlook |
| **Delivery restriction** | A rule about who may send mail to a mailbox |
| **Distribution list (DL)** | A group address that delivers to each member's own inbox |
| **Full Access / Read and manage** | Delegation permission to read, organise and delete, but not send |
| **GAL (Global Address List)** | The company directory inside Outlook |
| **Group mailbox** | The shared inbox belonging to a Microsoft 365 group |
| **Mailbox delegation** | Giving someone access to another mailbox without sharing the password |
| **Message trace** | The Exchange tool that tracks where a message went |
| **Microsoft 365 group** | A group with an email address, group mailbox, Teams group and SharePoint site |
| **Offboarding** | Remove licence → remove roles → block sign-in. Never delete. |
| **OWA (Outlook Web App)** | Outlook in the browser |
| **Send as** | Delegation permission to send as the mailbox, hiding the real sender |
| **Send on behalf** | Delegation permission showing "X on behalf of Y" |
| **Shared mailbox** | A department mailbox with no licence and no sign-in, whose replies go out from the shared address |
| **Sign out of all sessions** | Signs an account out of every device at once |
| **User mailbox** | An ordinary mailbox belonging to one licensed person |

---

# Appendix F — Lab Workbook for Part 2

Do these in a practice tenant. Tick each one when you can do it **without looking at the book**.

| # | Lab | Chapter | ✔ |
|---|---|---|---|
| 1 | Create a **test user** with no role. Try to open admin.microsoft.com as them and read the message. | 17 | ☐ |
| 2 | Give them **Helpdesk Administrator**. Sign in again and list what they can and can't do. | 17 | ☐ |
| 3 | Use **Compare roles** on Helpdesk, User and Global Administrator. Write down three differences. | 17 | ☐ |
| 4 | Add **two aliases** to a user. Verify by typing the alias in the To box, then send a test to each. | 15 | ☐ |
| 5 | Reply from that mailbox and confirm which address the reply comes from. | 15 | ☐ |
| 6 | Try to add the **same alias** to a second user. Note the error. | 15 | ☐ |
| 7 | Set a **profile photo** and check it in Outlook and Teams. | 16 | ☐ |
| 8 | Check **sign-in activity**, then **sign out of all sessions**. | 16 | ☐ |
| 9 | Set an **alternate email** and a **manager** on a user. | 16 | ☐ |
| 10 | Open the **Office apps** tab, check activations, and **deactivate** a device. | 18 | ☐ |
| 11 | **Block OWA** for the test user. Wait, then confirm from a private window. Re-enable it. | 19 | ☐ |
| 12 | Set **forwarding with a copy** and test. Then **without a copy** and test again. | 20 | ☐ |
| 13 | Turn on **automatic replies for another user** from the admin center. | 20 | ☐ |
| 14 | **Hide a user** from the global address list and confirm they disappear from People → All company. | 21 | ☐ |
| 15 | Grant **Read and manage** to another account. Open the mailbox and try to send. | 22 | ☐ |
| 16 | Switch to **Send on behalf** and compare how the message appears. | 22 | ☐ |
| 17 | Set a tiny **message size limit**, send an attachment, read the failure, then restore the limit. | 23 | ☐ |
| 18 | Add a **delivery restriction** blocking one sender, then test and remove it. | 23 | ☐ |
| 19 | **Enable the archive** on a mailbox and find the archive folders in Outlook. | 23 | ☐ |
| 20 | Create a **Microsoft 365 group**. Send it mail and find where it lands. Allow external senders and test from Gmail. | 24 | ☐ |
| 21 | Create a **distribution list** and compare where its mail lands. | 24 | ☐ |
| 22 | Create a **shared mailbox**, add two members, and confirm a reply comes from the shared address. | 25 | ☐ |
| 23 | **Convert** a test user's mailbox to a shared mailbox and remove the licence. | 25 | ☐ |
| 24 | Perform a full **offboarding** on a test user: licence → roles → block sign-in. Don't delete. | 14 | ☐ |

---

*End of Part 2.*
