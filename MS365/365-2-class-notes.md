# Microsoft 365 — Class 2: User Management, Aliases, Mail Settings, Delegation, Groups & Shared Mailboxes

Teaching notes for class 2 of the Microsoft 365 course. The whole video (~2 h 27 min) is covered in order.

---

## How to use this document

- Each section follows the video **in order**, with **timestamps** so you can check the recording.
- The auto-generated transcript had many errors. They are corrected here, e.g. "Elias" is **alias**, "helpdex/helbex" is **Helpdesk**, "inter ID" is **Entra ID**, "same age" is **Send as**, "into official" is **Intune**.
- Class chatter is left out: connection problems, roll calls, passwords, student names where they don't matter.
- 📘 **Note** boxes are short clarifications I added. They weren't said in the video.
- The instructor numbered the day's work as **tasks**. He covered about **18 tasks** and said so several times: *"I'm covering almost 15–17 tasks today."*

### Class overview

| Time | Topic |
|---|---|
| 0:00 – 6:00 | Recap of class 1 |
| 6:00 – 12:10 | Onboarding a new user again, licences, and the same account in Entra ID (SSO) |
| 12:10 – 19:30 | Removing licences, and the **offboarding** procedure |
| 19:30 – 23:10 | Bulk users recap, default domain, creating a test account |
| 23:10 – 33:30 | Signing in from three places, adding several accounts to Outlook |
| 33:50 – 52:10 | **Email aliases** ⭐ |
| 52:10 – 57:00 | The user's other tabs: photo, sign-in activity, sign out of all sessions, alternate email, manager |
| 56:36 – 1:02:50 | **Admin roles** again, and the **compare roles** tool |
| 1:03:40 – 1:15:20 | **Office app activation**: checking and installing Office |
| 1:15:20 – 1:18:10 | Devices, licences and the **Exchange admin center** |
| 1:18:26 – 1:23:20 | **Blocking email apps** (web, mobile, desktop) ⭐ interview question |
| 1:23:30 – 1:31:00 | **Email forwarding** ⭐ |
| 1:31:04 – 1:32:50 | Setting **automatic replies for another user** |
| 1:32:54 – 1:43:45 | **Hiding a user from the global address list** |
| 1:43:47 – 1:52:40 | **Mailbox delegation**: Read and manage, Send as, Send on behalf ⭐ |
| 1:52:43 – 2:00:30 | OneDrive tab, **delivery restrictions**, **message size**, **archive** |
| 2:00:40 – 2:15:40 | **Microsoft 365 groups** and **distribution lists** ⭐ |
| 2:15:47 – 2:26:40 | **Shared mailboxes** ⭐ |

### The task list from this class

| # | Task |
|---|---|
| 1 | Create a user (single and bulk with CSV) |
| 2 | Assign or remove a licence |
| 3 | Assign admin roles |
| 4 | **Offboarding**: remove licence → remove roles → block sign-in (never delete) |
| 5 | Set up MFA / Microsoft Authenticator |
| 6 | **Email aliases** |
| 7 | Change the profile photo |
| 8 | Check sign-in activity and **sign out of all sessions** |
| 9 | Add an alternate (personal) email and a manager |
| 10 | Check and install **Office apps**, and deactivate a device |
| 11 | **Block email apps** (OWA, mobile, desktop) |
| 12 | **Email forwarding** (with or without a copy) |
| 13 | Set **automatic replies** for another user |
| 14 | **Hide a user** from the global address list |
| 15 | **Mailbox delegation** (read and manage / send as / send on behalf) |
| 16 | **Delivery restrictions**, **message size limit**, **archive** |
| 17 | **Microsoft 365 group** (with Teams) and **distribution list** |
| 18 | **Shared mailbox** |

---

## Part 1 — Recap of class 1 (0:00 – 6:00)

The instructor spent the first few minutes revising.

### What Microsoft 365 is
- A **complete business suite** for medium to enterprise organisations, with almost every feature a business needs.
- Features listed: **VoIP phone and Teams** (not covered yet), **identity / Entra ID** (not covered yet), **Exchange Online / Outlook** email, **storage** with OneDrive and SharePoint, **security** (not part of this course), and **MDM and MAM** through **Intune**.
- *"That's why it's called the business suite: **except printer, it has everything**."*

### Licences
- Small to medium business: **Basic, Standard, Premium**.
- Enterprise: **E3, E5, E7**. Government: **G3, G5**. Education: **A1, A3, A5**. Plus frontline worker plans.
- **All the features in this course are covered by Business Premium.**
- Yesterday the class **bought a Business Premium trial with a credit card**, which gave **25 licences**.

### Where you work
- **admin.microsoft.com** is the admin center.
- The class also has its own domain (`jobforit.online`), and everyone has a username and password.

### Yesterday's tasks
1. **Create users**, individually and **in bulk with a CSV file**
2. **Assign or remove licences**
3. **Assign roles**. Roles are for IT only. A **billing administrator** role can be given to an accountant, who can pay the bills but gets no other admin rights.
   - For an IT person: **Global Administrator** is the maximum ("superpower"), **Helpdesk Administrator** is the minimum, and **User Administrator** is in between.
4. **MFA with Microsoft Authenticator**. Everyone must have the app, because **Microsoft enforces the security policy**.

---

## Part 2 — Onboarding again, and licences (6:00 – 12:10)

### Creating a user for a student who missed class (6:42 – 9:53)
**Users → Active users → Add a user**
1. Type the **name** and **username**, and pick the **domain**.
2. **Licences:** the licence contains **59 applications**. In a real company they **untick the apps staff don't need**. In class everything is ticked, because students are learning all of it.
3. **Roles:** none for now. Roles can be added later.
4. **Password:** a **custom temporary password** was used.
5. 📌 **Useful option:** instead of reading the password out, you can **send the account details to the user's personal email address** at the end of the wizard.

### Adding a licence to an existing account (9:55 – 10:30)
A student already had an account but **no licence**, so no email. Fix: **user → Licenses and apps → tick the licence → Save.** Then they can sign in to **Outlook, Teams and SharePoint**.

### Student question: where does the admin dashboard come from? (7:47 – 8:52)
- When a company **buys (or trials) Microsoft 365 Business Premium** with a card, Microsoft gives it the **admin dashboard**.
- Usually **one person in the company buys it**, and then **IT manages everything** from that dashboard: how many users, which apps, and all the settings.

### The same user exists in Entra ID (10:30 – 12:10)
A student asked what the difference is between adding a user in the admin center and in Entra ID (Azure).
- **No difference.** *"Same, same."* The user created in the admin center **appears in Entra ID** too.
- **This is SSO (single sign-on).** Create an account once in Microsoft, and it exists across all Microsoft products. **You never recreate it.**

---

## Part 3 — Removing licences and the cost of the cloud (12:10 – 13:40)

- **Trial limit: 25 licences.** *"Free one is 25. If you pay, unlimited."*
- **To remove a licence:** user → **Licenses and apps** → **untick** the licence (or mark the user unlicensed) → **Save**.
- **Why it matters: money.** In the cloud, **the risky part is cost**. Every licence is charged every month.

> 💡 **The instructor's analogy:** *"If you go to a restaurant and your child orders something while you're in the restroom, you still have to pay."* Once it's ordered, the company pays. That's why a business **watches its licences all the time** and thinks twice before buying.

- **If someone leaves the company, remove their licence immediately.**

---

## Part 4 — Offboarding ⭐ (13:40 – 19:30)

**Offboarding** is what IT does when a staff member leaves. The instructor called it a task and repeated it several times.

### The three minimum steps, in order

| Step | Action | Why |
|---|---|---|
| **1** | **Remove the licence** | The company pays monthly. Why pay for someone who left? |
| **2** | **Remove all roles** | They must not keep admin permissions |
| **3** | **Block sign-in** (disable the account) | They can no longer log in |

### ⚠️ Never delete the account
- *"We never delete the account in an organisation."*
- If you delete it you **lose everything**: their **email**, **OneDrive files**, **SharePoint documents**, **Teams chats**, and their settings.
- The person was emailing **on behalf of the company**, so **those conversations belong to the company**, not to them.
- If you do delete a user, the admin center warns that you can **restore the account and its data for 30 days**. After that it's gone, and even during those 30 days the email aliases, permissions and OneDrive access are not simply usable by someone else.
- **A blocked, unlicensed account costs nothing.** *"If you disable the account, Microsoft never charges."* Leave it there. Even two years later you can re-enable it, add a licence and reuse it.
- **Before finally deleting** (some companies do this after about 90 days), take a **backup / archive of the mailbox**, and give someone access to the data. The instructor covers those options later in the class: **mailbox permissions** (Part 16) and **forwarding** (Part 14).

> 🎯 This is a **very common interview question**: *"What do you do when an employee leaves?"*

---

## Part 5 — Bulk users, default domain and a test account (19:30 – 23:10)

### Bulk users recap (19:30 – 21:30)
- **Users → Active users → Add multiple users.**
- You can type users into the form, but *"that is the hard part"*. **Use the CSV file and the sample template**, fill in all the parameters, and upload them all at once.
- From the same page you can also **reset passwords**, **delete users**, and open **per-user MFA**, which redirects to **Entra ID**, where MFA can be enabled or disabled.

### Setting the default domain (21:56 – 22:33)
When creating a new user, the **wrong domain appeared first** in the list.
- **Fix: Settings → Domains → select your domain → set it as default.**
- After that, your own domain always appears first, so new users get `name@jobforit.online`.

### A second account for demonstrations (22:33 – 23:06)
The instructor created a test user (**Bipin**) so he could sign in as a normal user and show the effect of each setting.
- This time he **unticked** "require change at first sign-in", so the password was **permanent**.
- **No role** was given, which matters later in Part 9.

> 🏢 **Tip for the real world:** having a **test account** with no admin rights is very useful. It lets you see exactly what a normal user sees.

---

## Part 6 — Signing in from three places (23:10 – 33:30)

- The class connected the test account in **three places**, as in class 1: **Outlook on the web (outlook.office.com)**, the **Outlook desktop app**, and the **mobile app**.
- Signing in needed the **password plus MFA**: scan the QR code in **Microsoft Authenticator**, click **Next**, then enter the code from the phone.
- **Adding more accounts to Outlook desktop:** **File → Add account**. You can add:
  - a second **company** account (the instructor added two, so he could demonstrate permissions between them)
  - accounts from **different companies**, even **ten organisations**
  - personal accounts such as **Gmail**
- 📘 Note: one Outlook profile showing several mailboxes is normal in IT support, where you often have a normal account and an admin account.

---

## Part 7 — Email aliases ⭐ (33:50 – 52:10)

This is one of the most important topics of the class.

### What is an alias? (34:34 – 36:15)
- An **alias** is a **nickname** for an existing mailbox: an **extra email address** that delivers into the **same mailbox**.
- Example: Bipin works in finance. His address is `bipin@jobforit.online`. The company also wants `finance@jobforit.online`.
- Creating a **separate user** for finance would mean **paying another licence** and **signing in separately**. An alias costs **nothing**.

### The rules of an alias

| | Alias |
|---|---|
| Licence needed | **No, free** |
| Has its own mailbox | **No.** Mail lands in the owner's mailbox |
| Can receive email | ✅ **Yes** |
| Can send or reply as the alias | ❌ **No.** Replies always come from the **real address** |
| Can you sign in with it | ❌ No |
| Can two users share the same alias | ❌ No. Every address in the tenant must be unique |
| How many per user | Many |

> 💡 **Explain it like this:** *"It's a nickname. People call me the owner, the tutor, or by my name. It all reaches the same person. But when I reply, my real name goes out."*

### How to add an alias (37:34 – 38:45)
1. **Users → Active users →** click the user.
2. Open **Manage username and email** (the aliases section).
3. Type the alias name, e.g. `finance`, pick the domain, and **add**. Repeat for `sales`.
4. **Save.**

**How to check it worked:** start a new email and type **`sales`** in the To box. If the **person's name** appears, it's their alias. The class tested it: an email sent to `finance@…` arrived in Bipin's mailbox.

### Why companies use aliases (36:15 – 47:01)
- A company website usually lists **many addresses**: `sales@`, `finance@`, `marketing@`, `info@`, and separate addresses for each branch or city (Sydney, Melbourne, Adelaide, USA…).
- Outside, it looks like a **big, well-organised company with many departments**. Inside, several of those addresses can point to **the same mailbox**.
- The instructor showed a real estate company's website, where each suburb has its own address (`blacktown@…`, `leppington@…`, `brisbane@…`), each one delivering to the staff member who covers that area.
- **Nobody wants to pay extra licences just for extra addresses.** *"It acts as an email, but actually it isn't an email. No mailbox and no charge."*
- Combine aliases with **Outlook rules** (class 1): any email sent to `finance@` goes into a Finance folder, `sales@` into a Sales folder.

### Student questions answered (39:14 – 52:10)
- **"Can Bipin reply from finance@?"** **No.** An alias is **receive only, one way**. The reply always goes out from `bipin@…`.
- **"Can the same alias be given to two people?"** **No.** Each address must be unique.
- **"Can we later create a real account called finance?"** Only if you **remove the alias first**, because the address is already in use.
- **"Can our domain also be on Gmail at the same time?"** **No.** The **MX record** points to one provider only. *"One name must be unique all over the world."*
- **"Can an alias be deleted?"** Yes: Active users → the user → **Mail / manage aliases** → delete.
- **"Why not create a real mailbox for finance?"** Then you pay a licence, and someone has to **sign in separately** to a second account. More money, more work.

> 📘 **Note:** if a department really needs to **reply** from the department address, an alias is not the answer. That's what a **shared mailbox** is for (Part 20).

---

## Part 8 — The rest of the user's settings (52:10 – 57:00)

Everything below is found under **Users → Active users → [click the user]**.

| Setting | What it does | The instructor's point |
|---|---|---|
| **Profile photo** | Upload a photo | It follows the account **everywhere**: Outlook, Teams, SharePoint. Another example of SSO. |
| **Reset password** | New temporary password | Everyday helpdesk work |
| **Block sign-in** | Stops the user signing in | Used in offboarding and when an account is compromised |
| **Delete user** | Removes the account | Avoid it (Part 4) |
| **Edit username** | Fix a typo, or move the user to another domain | Big companies often have **several domains** for franchises and brands (e.g. different McDonald's branches) |
| **Aliases** | Add or remove alias addresses | Part 7 |
| **Sign-in activity** | Last **30 days** of sign-ins | For more, go to **Entra ID → user → Sign-in logs**, where you can see every sign-in and whether it succeeded |
| **Sign out of all sessions** ⭐ | Signs the account out of **every device** | *"You went to a friend's house and think you forgot to sign out. Sign out from here."* Essential when a **phone or laptop is lost**. **The data matters far more than the device.** |
| **Alternate email** | A personal email address | Used to contact the person **when they can't reach their work email** |
| **Groups** | Which groups the user belongs to | Covered in Part 19 |
| **Manager** | The user's line manager | Very important for approvals. *"If someone asks for access and you're not sure, CC their manager: 'Your staff member is asking for this, are you aware?' If the manager approves, you have proof and you're on the safe side."* |
| **Contact details** | Job title, department, phone, country | Part of keeping the directory accurate. *"This is your job."* |

---

## Part 9 — Roles revisited, and comparing roles (56:36 – 1:02:50)

### Who gets a role
- **Roles are mostly for IT.** *"A non-IT person doesn't get permissions. We never give them, and we should not."*
- Some roles are for specific jobs: **Billing Administrator** for an accountant, **Exchange Administrator** for someone who only handles email. *"If you get the Exchange admin role, you cannot see Teams."*

### Demonstration: a user with no role (57:14 – 57:56)
The instructor signed in as the test user at **admin.microsoft.com**:
> *"Bipin does not have permission to view or manage this page. Switch to an account that has permission."*

**A normal user cannot open the admin center at all.**

### Giving the Helpdesk Administrator role (57:56 – 1:02:50)
- **Helpdesk Administrator** can: **reset passwords** and **re-authenticate all non-admin users in the same domain**, **manage service requests**, and **monitor service health**. That's all.
- After the role was assigned (it takes a few minutes, and a sign-out and sign-in helps), the test user **could open the admin center**, but:
  - ❌ no **Add a user**, **Add multiple users** or template options
  - ❌ no **delete**
  - ✅ only **reset password**

### The compare roles tool 📌
**Roles → Role assignments →** tick up to **three roles** → **Compare roles**.
- The class compared **Helpdesk Administrator**, **User Administrator** and **Global Administrator** side by side.
- **Global Administrator** has everything ("unlimited"). The other two have a short, specific list.
- This screen is a great way to learn what each role can do.

---

## Part 10 — Office apps: checking and installing (1:03:40 – 1:15:20)

### Checking activations
- **Users → Active users → [user] → Office apps** (the activation tab) shows **which devices** the user has installed and activated Office on, including the **computer name** and **operating system**.
- Use it when someone says *"Word isn't working"* or *"Excel won't open"*. You can see whether they've installed and activated it at all.
- The class confirmed the test user's activation, then checked the computer name with **`hostname`** in Command Prompt. They matched.
- 📌 **You can deactivate a device from here.** Useful when someone has left: *"otherwise he can use this service forever."*

### Helping a user install Office manually
1. The user signs in at **office.com** (or outlook.office.com, or any Microsoft site).
2. Click the **app launcher / More apps**, then **Install apps** (**Apps and devices**).
3. Download and run the installer, then sign in so it activates.

- *"Later we'll push this software from **Intune**"*, so users won't install it by hand. But manual installation is still useful **when one or two machines need it**, or after a system crash or reinstall.

### Per-user MFA from here (1:08:53 – 1:10:58)
- The user page also links to **multifactor authentication**, which opens the **Entra ID** per-user MFA page.
- Interesting detail: the test user's MFA state was **Disabled**, yet Microsoft still asked for the Authenticator app. **That's Microsoft's own enforced security policy, not the company's.**
- If **the organisation** enables it, the state becomes **Enforced**. *"Enforced by the organisation, not by Microsoft."* The instructor recommends the organisation enforcing it, so protection doesn't depend on Microsoft's defaults.

---

## Part 11 — Devices, licences and the Exchange admin center (1:15:20 – 1:18:10)

- **Devices tab:** left for the **Intune** classes. *"We have very big topics on Intune, minimum two classes."*
- **Licences tab:** shows the licence and its apps. Companies often **untick apps** staff don't need.
- **Mail tab:** many email settings can be changed here **or** in the **Exchange admin center**, which has **extra features**.

### Why the numbers don't match 📌
- The Exchange admin center listed **24 mailboxes**, but the admin center listed **61 users**. Why?
- **Only licensed users have a mailbox.** Unlicensed users appear in the user list but not in Exchange.
- **Aliases don't appear either**, because an alias isn't a mailbox. *"These are non-paid."*

---

## Part 12 — Blocking email apps ⭐ (1:18:26 – 1:23:20)

**Where: Users → Active users → [user] → Mail → Manage email apps** (also in the Exchange admin center).

You can allow or block each way of reaching the mailbox:
- **Outlook on the web (OWA)**
- **Outlook desktop (MAPI)**
- **Mobile (Exchange ActiveSync)**
- **IMAP / POP**

Some companies **block webmail** or **block mobile access** for security reasons.

> 🎯 **The instructor's interview question:** *"A user says they can't open their email in the web browser, but the mobile app and the desktop app work fine. What's the reason?"*
> **Answer: the web app (OWA) is blocked in that user's email app settings.**

The class tested it: OWA was unticked for the test user, and a few minutes later the user could no longer open **outlook.office.com**, while the admin center and other apps still worked. **Email itself isn't blocked, only that way of reading it.**

📌 Changes take **a few minutes**, and the browser cache can hide the effect. Test in a **private window**.

---

## Part 13 — Email forwarding ⭐ (1:23:30 – 1:31:00)

**Where: Users → Active users → [user] → Mail → Manage email forwarding**

Turn on forwarding, type the address to forward to, and choose whether to **keep a copy of forwarded email in this mailbox**.

### The two cases the instructor gave

| Case | Situation | Setting |
|---|---|---|
| **Case 1** | The person is **on holiday** but still wants to see what happened while they were away | Forward **and tick "Keep a copy"**. Both mailboxes get the email. |
| **Case 2** | The person **has left**, or wants to be **completely off** during the holiday | Forward **without** a copy. Only the other person gets it. |

The class tested both:
- With **keep a copy**: an email sent to the test user arrived in **both** mailboxes.
- Without it: the email sent to the test user arrived **only in the other mailbox**.

> *"If you keep one copy, when you come back from holiday you know everything that happened. If you don't, it's completely blind."*

📘 **Note:** forwarding to another **internal** address always works. Forwarding to an **external** address (like Gmail) is often **blocked by security policy**, because attackers use it to steal mail. The instructor said he had never tested it.

---

## Part 14 — Setting automatic replies for another user (1:31:04 – 1:32:50)

In class 1 the students set their **own** out-of-office in Outlook. But what if the user **has already left for holiday** and calls you from the airport? You can't sign in as them, because **you don't know their password**.

**Solution: Users → Active users → [user] → Mail → Manage automatic replies.**
- The admin can **turn on the out-of-office message for any user**, without their password.

---

## Part 15 — Hiding a user from the global address list (1:32:54 – 1:43:45)

### What the global address list is
The **GAL (Global Address List)** is the company directory inside Outlook. Any user can open it and see everyone's name and email address.
- In Outlook on the web: **People → search / All company**, which lists every user in the organisation.
- (The instructor spent a while finding this in the new Outlook. It was easy in the old Outlook, and Microsoft has moved it.)

### Why hide someone
- Senior people such as the **CEO, CFO and directors** often shouldn't be visible to everyone.
- *"Otherwise staff email the manager directly asking for a pay rise while he's on holiday."*
- It's also a **security measure**, because an address that can't be found is harder to attack.

### How to hide a user
**Users → Active users → [user] → Mail** (or the Exchange admin center) → untick **Show in global address list** → **Save**.
- It takes a **couple of minutes**. The class confirmed the name disappeared from the directory afterwards.
- **The mailbox still works.** Anyone who **knows** the address can still email them. You've only hidden them from the list.

### Related security tip 📌
Executives often use a **different email pattern** from normal staff. If everyone is `firstname@company.com`, then the CEO might be `lastname.firstname@company.com`.
- **Why:** if the pattern is predictable, attackers can guess the CEO's address and send phishing emails. *"We need to protect them."*

---

## Part 16 — Mailbox delegation ⭐ (1:43:47 – 1:52:40)

**Where: Users → Active users → [user] → Mail → Manage mailbox delegation**

### Why it exists
Senior people have **assistants** who manage their mail. *"Top-level people can't read all their email, so the assistant reads everything, marks the important ones and passes them on."*
**The password must never be shared**, because with SSO that one password opens everything. Delegation gives **mailbox access only**.

### The three permissions

| Permission | What the delegate can do | Who the recipient sees |
|---|---|---|
| **Read and manage** (Full Access) | **Read, organise and delete** the manager's email. **Cannot send.** | — |
| **Send as** | Send email **as the mailbox itself** | Only the **mailbox owner's name**. The recipient **can't tell** someone else sent it. |
| **Send on behalf** | Send with both names | **"Assistant on behalf of Manager"** |

### The instructor's explanations
- **Read and manage:** *"You can read everything, mark the important ones, and tell me. But you cannot reply."* The class demonstrated it: the delegate could open the mailbox, read and delete, but got an error when trying to send.
- **Send as:** *"If someone comes to my desk and types 'no class today' from my computer, everyone thinks I sent it."* Powerful, but **risky**. Only give it to people you trust completely, because **if they write something wrong, you are responsible**.
- **Send on behalf:** ⭐ *"This is the best one."* The message is clearly sent by the assistant with the manager's authority. *"Like when Donald Trump wishes people happy Diwali. The secretary sent it, but the message belongs to Trump."*

### How the delegate opens the mailbox
Once the permission applies (it can take a while), the delegate opens the other mailbox in Outlook. In the web version, the URL shows the **other person's mailbox**, even though the delegate is signed in with their own account.

---

## Part 17 — OneDrive, delivery restrictions, size limits and archive (1:52:43 – 2:00:30)

### OneDrive tab (1:52:43 – 1:53:15)
- Each user gets **1 TB** by default.
- You can **access their files**, and see the **retention period** for a deleted user's OneDrive: **30 days by default, extendable up to a year**.

### Delivery restrictions (1:53:21 – 1:56:00)
**Exchange admin center → Mailboxes → [user] → Mailbox settings → Delivery restrictions** (some of this is also in the admin center's Mail tab).
- You can **choose who is allowed to send email to this mailbox**, or **reject mail from specific senders**.
- **Real use:** protecting **senior managers** so that ordinary staff must go through their **line manager** instead of emailing the boss directly.
- The class blocked two senders from emailing the test mailbox and confirmed the mail was rejected.

### Message size restriction (1:56:00 – 2:00:20)
- You can set the **maximum size** of messages a user can send or receive.
- Test: the limit was set to a tiny size, and the sender got **"delivery has failed to this recipient because of size"**.
- For comparison, **Gmail's limit is 25 MB**, and above that Google turns the attachment into a **Google Drive link**. Microsoft 365 does the same with **OneDrive**.
- 📘 **Note:** Exchange Online's default limit is **35 MB**, and it can be raised to a maximum of **150 MB**. Large files should be shared as **OneDrive/SharePoint links**, not attachments.

### Archive (2:00:27 – 2:02:00)
- **If the mailbox is full, enable the archive.**
- An **online archive** is a second storage area for older mail. Outlook shows it as an extra folder, and mail is moved there automatically by policy, typically **after about a year**.
- *"It's like compressing in Windows"*: it takes pressure off the main mailbox.

---

## Part 18 — Group email: Microsoft 365 groups and distribution lists ⭐ (2:02:04 – 2:15:40)

### The purpose
*"I want to send one email to everybody at the same time. That is group email."* Anyone can email the group address, and every member receives it. **Each member replies individually**, and everyone can see who replied.

### Type 1: Microsoft 365 group (with Teams) — task 16

**Teams & groups → Active teams & groups → Add a group → Microsoft 365 (with Teams)**
1. Name the group (the class used *Mixed class*).
2. Add **owners** and **members**.
3. Choose whether **people can join without approval** or need the owner's approval.
4. **Create.**

What you get:
- ✅ a **group email address** (`mixedclass@jobforit.online`)
- ✅ a **group in Microsoft Teams**, with **group chat** and calls. The class refreshed Teams and the new group appeared.
- ✅ a **separate group mailbox**. **Mail to the group does *not* go to each member's personal inbox.** It appears under **Groups** in Outlook.
- ⚠️ **By default, people outside the organisation can't email the group.** To allow it: group **Settings → tick "Let people outside the organisation email this group"**.

> The class tested this. At first members were looking in their own inbox and thought the mail hadn't arrived. It was in the **group** mailbox.

### Type 2: Distribution list — task 17

**Teams & groups → Add a group → Distribution list**
1. Name it (the class used *Full class*), add owners and members, and create it.

What you get:
- ✅ a **group email address**
- ✅ mail arrives in **each member's own inbox**
- ❌ **no Teams group**
- ❌ **no separate group mailbox**
- ✅ outside senders are allowed

### Comparison

| | **Microsoft 365 group (with Teams)** | **Distribution list** |
|---|---|---|
| Group email address | ✅ | ✅ |
| Where the email lands | **A separate group mailbox** (Groups in Outlook) | **Each member's own inbox** |
| Teams group and chat | ✅ | ❌ |
| External senders | Blocked by default, can be allowed | Allowed |
| **Reply comes from** | **The individual person** | **The individual person** |

**Remember: with both of these, the reply goes out in the individual's own name.** That's the problem the next part solves.

---

## Part 19 — Shared mailboxes ⭐ (2:15:47 – 2:26:40)

### The problem (2:15:47 – 2:19:30)
Five people work in the same department. Customers email `booking@jobforit.online`.
*"Whoever replies, the reply should go from the same email address, not from the individual's name."*

- A **group or distribution list** handles the **incoming** side well. Everyone receives the mail.
- But the **outgoing** side is wrong. Vinod replies as Vinod, Bipin replies as Bipin.

### The solution: a shared mailbox

| | **Group / distribution list** | **Shared mailbox** |
|---|---|---|
| Incoming | All members receive it | All members see the same inbox |
| **Outgoing (reply)** | **The individual's name** | **The shared address** (`booking@…`) |
| Licence | Not needed | **Not needed** |
| Can you sign in to it | N/A | **No** |
| Do members know it was answered | Yes | **Yes**, they all see the same mailbox and the same Sent items |

### Why companies want it
- *"I don't want to put any person in the hassle. **The company will be responsible.**"*
- The customer always gets a reply from `info@` or `booking@`, whoever answered.
- *"Today we hire one person, tomorrow maybe another. I don't want to put the name, I want to put the **department name**."*
- **Outside users can't tell who replied.** **IT can**, by tracking computer name, IP address and the audit logs.
- Use it whenever **more than one person does the same job**: `info@`, `support@`, `booking@`, `sales@`, `accounts@`. For a one-person role, or for tiered support (level 1, 2, 3 as separate people), it isn't needed.

### Creating a shared mailbox (2:24:39 – 2:26:40)
1. In the mailbox list, notice that all existing mailboxes are **user mailboxes**, meaning one individual each.
2. **Teams & groups → Shared mailboxes → Add a shared mailbox** (or **Exchange admin center → Recipients → Mailboxes**).
3. **Name:** *Booking*. **Email:** `booking@jobforit.online`. **Save.**
4. **Add members** (the department's staff). This also gives them permission to use it.
5. **Wait.** The shared mailbox appears **automatically** in each member's Outlook, below their own mailbox. It can take **half an hour to 60 minutes**. *"You don't need to add it yourself."*
6. Test: email `booking@…` from outside. Everyone sees it, one person replies, and **the reply goes out from `booking@…`**.

> *"Now you can crack the interview if you know all these things."*

---

## Quick reference: where each setting lives

**Users → Active users → [click a user] →**

| Tab / link | Settings |
|---|---|
| **Account** | Name, username, **aliases**, job title, department, **manager**, **alternate email**, **roles**, **sign-in activity**, **sign out of all sessions**, block sign-in, delete |
| **Licenses and apps** | Assign or remove licences, turn individual apps on and off |
| **Mail** | **Email apps** (block OWA/mobile/desktop), **forwarding**, **automatic replies**, **mailbox delegation**, **aliases**, **show in global address list**, convert to shared mailbox |
| **OneDrive** | Storage, files, retention |
| **Office apps** | Which devices have Office activated, deactivate a device |
| **Devices** | Intune (later classes) |

**Other places**

| Task | Path |
|---|---|
| Set the default domain | Settings → Domains → select → Set as default |
| Compare admin roles | Roles → Role assignments → tick up to 3 → Compare roles |
| Per-user MFA | Entra ID → Users → Per-user MFA |
| Full sign-in logs | Entra ID → Users → [user] → Sign-in logs |
| Create a group | Teams & groups → Active teams & groups → Add a group |
| Create a shared mailbox | Teams & groups → Shared mailboxes → Add a shared mailbox |
| Mailbox size, delivery restrictions, archive | Exchange admin center → Recipients → Mailboxes → [user] |

## Glossary

| Term | Meaning |
|---|---|
| **Alias** | An extra email address for an existing mailbox. Free, receive only. |
| **Archive (online archive)** | A second mailbox area for older email, used when the mailbox fills up |
| **Delivery restriction** | A rule about who may send email to a mailbox |
| **Distribution list** | A group address whose mail lands in each member's own inbox. No Teams group, no group mailbox. |
| **GAL (Global Address List)** | The company directory of users inside Outlook |
| **Mailbox delegation** | Giving someone access to another person's mailbox without sharing the password |
| **Microsoft 365 group** | A group with an email address, a **group mailbox**, and a **Teams** group |
| **Offboarding** | Remove licence → remove roles → block sign-in. Never delete. |
| **OWA (Outlook Web App)** | Outlook in the browser |
| **Read and manage (Full Access)** | Delegation permission to read, organise and delete, but not send |
| **Send as** | Delegation permission to send as the mailbox, hiding who really sent it |
| **Send on behalf** | Delegation permission that shows "X on behalf of Y" |
| **Shared mailbox** | A department mailbox. No licence, no sign-in, and **replies go out from the shared address**. |
| **Sign out of all sessions** | Signs an account out of every device at once |
| **User mailbox** | An ordinary mailbox belonging to one licensed person |

---

## Practice tasks for the student

1. Create a **test user** with a permanent password and no role. Try to open **admin.microsoft.com** as that user and read the error.
2. Give the test user the **Helpdesk Administrator** role. Sign in again and find what they can and cannot do.
3. Use **Roles → Compare roles** on Helpdesk Admin, User Admin and Global Admin. Write down three differences.
4. Add two **aliases** (`finance@`, `sales@`) to a user. Send mail to each and confirm it arrives. Reply, and check which address the reply comes from.
5. Try to give the **same alias** to a second user. What happens?
6. Set a user's **profile photo** and check that it appears in Outlook and Teams.
7. Look at a user's **sign-in activity**, then **sign out of all sessions**.
8. Add an **alternate email** and a **manager** to a user.
9. Open the **Office apps** tab and see which devices have Office activated. Deactivate one.
10. **Block OWA** for the test user. Wait a few minutes and confirm they can't open outlook.office.com but can still use the app.
11. Set up **forwarding with a copy**, test it, then **without a copy** and test again.
12. Turn on **automatic replies for another user** from the admin center.
13. **Hide a user from the global address list**, then confirm they've disappeared from People → All company.
14. Give another account **Read and manage** on a mailbox. Open the mailbox and try to send. Then switch to **Send on behalf** and see the difference.
15. Set a **message size limit** of a few KB on a test mailbox and send an attachment to it. Read the failure message. Put the limit back.
16. Create a **Microsoft 365 group** with Teams. Send it an email and find where the email lands. Allow external senders and test from Gmail.
17. Create a **distribution list**. Send it an email and compare where that lands.
18. Create a **shared mailbox**, add two members, and test that a reply goes out from the shared address.
19. Perform a full **offboarding** on a test user: remove licence → remove roles → block sign-in. Do **not** delete.

## Review / interview questions (with answers)

1. **What are the three steps of offboarding, and what must you never do?**
   Remove the licence, remove the roles, block sign-in. Never delete the account, because you'd lose the email, OneDrive files, SharePoint documents and Teams chats.
2. **Why remove the licence first?**
   The company pays for every licence every month.
3. **How long can a deleted user be restored?**
   30 days.
4. **Does a blocked, unlicensed account cost money?**
   No.
5. **What is an alias?**
   An extra email address for an existing mailbox. It's free, needs no licence and has no mailbox of its own.
6. **Can a user reply from their alias?**
   No. An alias is receive only. Replies come from the real address.
7. **Can two users have the same alias?**
   No. Every address in the tenant must be unique.
8. **Why do companies use aliases?**
   To publish many department or branch addresses without paying for extra licences.
9. **Can one domain use both Microsoft 365 and Gmail for email?**
   No. The MX record points to one provider.
10. **A user lost their laptop. What do you do straight away?**
    Sign out of all sessions, reset the password, and block sign-in if needed. The data matters more than the device.
11. **A user can't open email in the browser, but the desktop and mobile apps work. Why?**
    Outlook on the web (OWA) is blocked in their email app settings.
12. **How do you let a colleague receive someone's email while they're on holiday, but still keep a copy for them?**
    Set up forwarding and tick "Keep a copy of forwarded email in this mailbox".
13. **A user is already on holiday and forgot their out-of-office. Can you help without their password?**
    Yes. Users → the user → Mail → Manage automatic replies.
14. **What is the global address list, and why hide someone from it?**
    The company directory in Outlook. Senior people are hidden so staff can't email them directly and attackers can't find them easily.
15. **Why does a CEO often have a different email pattern?**
    If the pattern is predictable, attackers can guess the address and send phishing emails.
16. **Name the three mailbox delegation permissions and what each allows.**
    Read and manage: read, organise and delete, but not send. Send as: sends as the mailbox, hiding who really sent it. Send on behalf: shows "X on behalf of Y".
17. **Which delegation permission is the safest and why?**
    Send on behalf, because the real sender is visible.
18. **The Exchange admin center shows fewer mailboxes than there are users. Why?**
    Only licensed users have a mailbox, and aliases aren't mailboxes.
19. **A user says their mailbox is full. What can you do?**
    Enable the online archive (and check the size limits and their large attachments).
20. **What's the difference between a Microsoft 365 group and a distribution list?**
    A Microsoft 365 group has a Teams group and a separate group mailbox. A distribution list only forwards mail to each member's own inbox.
21. **Where does email sent to a Microsoft 365 group land?**
    In the group mailbox, under Groups in Outlook, not in each member's inbox.
22. **Why can't people outside the company email a new Microsoft 365 group?**
    It's blocked by default. Tick "Let people outside the organisation email this group".
23. **What's the difference between a group and a shared mailbox?**
    Incoming mail is similar, but replies from a group go out in the individual's name, while replies from a shared mailbox go out from the shared address.
24. **Does a shared mailbox need a licence? Can you sign in to it?**
    No, and no.
25. **Can anyone find out who actually replied from a shared mailbox?**
    Outside users can't. IT can, through the logs, the computer name and the IP address.
26. **How long can it take for a shared mailbox to appear in a member's Outlook?**
    Up to about an hour.
27. **Which admin role would you give an accountant who only pays the bills?**
    Billing Administrator.
28. **What can a Helpdesk Administrator do?**
    Reset passwords for non-admin users, manage service requests and monitor service health. They can't create or delete users.
