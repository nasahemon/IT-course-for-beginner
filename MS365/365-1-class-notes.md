# Microsoft 365 — Class 1: Introduction, Licences, Domain, Users, Outlook & Admin Roles

Teaching notes for class 1 of the Microsoft 365 course. The whole video (~2 h 42 min) is covered in order.

---

## How to use this document

- Each section follows the video **in order**, with **timestamps** so you can check the recording.
- The transcript was auto-generated and had many errors. They are corrected here, e.g. "Accent Online" is **Exchange Online**, "inter ID" is **Entra ID**, "view IP" is **VoIP**, "helpdex" is **Helpdesk**.
- Class chatter is left out: connection problems, roll calls, temporary passwords, MFA codes.
- 📘 **Note** boxes are short explanations or corrections I added. They weren't said in the video.

### Class overview

| Time | Topic |
|---|---|
| 0:00 – 11:00 | What Microsoft 365 is and its services |
| 11:00 – 16:05 | Single sign-on, Office 365 vs Microsoft 365, business vs personal email and Teams |
| 16:05 – 30:30 | **Licences** (personal, Business, Enterprise, Government, Education, Frontline) + interview tip |
| 30:30 – 44:30 | Free trial, logging in to the admin center, buying a domain |
| 44:30 – 1:07:50 | **Adding the domain to M365 and DNS records** (MX, TXT, CNAME, SPF), getting the licence |
| 1:07:50 – 1:16:30 | **Onboarding a user**, first login, **MFA**, test email |
| 1:16:30 – 1:31:10 | **Assigning licences in bulk**, **creating users in bulk (CSV)**, **bulk password reset** |
| 1:31:10 – 2:00:40 | Helping new users sign in: real **troubleshooting** |
| 2:00:40 – 2:07:40 | Outlook on desktop and mobile |
| 2:07:40 – 2:36:20 | Outlook tasks: **signature**, **automatic replies**, **rules** |
| 2:36:20 – 2:42:08 | **Admin roles** and wrap-up |

---

## Part 1 — What is Microsoft 365? (0:00 – 1:29)

### Opening message (0:00)
- This is a **completely new topic**. Even someone who started today can follow it.
- It is loosely related to earlier classes, but **you can work with Microsoft 365 on its own**.
- *"If you know only this one, even you can get a job."*

### Definition (0:25 – 1:29)
- *"Nowadays Microsoft 365 almost does everything for the business."*
- Microsoft 365 is a **cloud app suite**, a **complete-package business suite**.
- **Cloud business suite** means whatever the company needs, it gets from **one point**. *"It is like a big shopping centre."*
- It is a **SaaS** product. **SaaS = Software as a Service** means **you don't need to buy the hardware**.
- Everything is application-based. Organisations **rent** it and use it.

📘 **Note: the three cloud models (useful background)**

| Model | You rent | Example |
|---|---|---|
| IaaS | Servers, storage, network | Azure Virtual Machines |
| PaaS | A platform to run your own code | Azure App Service |
| **SaaS** | A finished application | **Microsoft 365**, Gmail |

---

## Part 2 — The services inside Microsoft 365 (1:29 – 7:55)

The instructor asked: *"What is the minimum requirement for an organisation?"* and then went through what every business needs.

| Business need | Microsoft 365 service | What the instructor said |
|---|---|---|
| **Business email** | **Exchange Online** | Every organisation needs business email. If anyone sends an email, it comes to my mailbox and I can reply. We'll create our own email addresses today, and anyone can email us from anywhere. (1:29 – 2:18) |
| **VoIP & remote support** | **Microsoft Teams** | VoIP means **telephone system, audio call, video call, meeting, file sharing, screen sharing**, and **remote control** to support customers. (2:27 – 3:16) |
| **Identity management** (username & password) | **Microsoft Entra ID** | Where we **create usernames and passwords**, **set up multi-factor authentication**, and **grant roles and permissions to groups**. *"Every company needs username and password. That is called **Active Directory**. The **cloud version** is called **Entra ID**."* (3:18 – 3:48, 7:21) |
| **Device & app management** | **Microsoft Intune** | Onboard **iPhone, Android, laptop**. As an IT person you can **install software from anywhere, restart, update and control the computer**, all from a **single dashboard**. (3:52 – 4:22) |
| **Storage** | **OneDrive** & **SharePoint** | **OneDrive = personal** storage. **SharePoint = business** storage. *"A very important one."* (4:29 – 4:50) |
| **Security** | Microsoft Defender etc. | Part of M365, but **not part of our course**. (4:55 – 5:31) |
| **Office apps** | **Microsoft 365 apps** | Word, Excel, PowerPoint and **up to 30+ apps**. (5:31 – 5:51) |

### The only thing missing: a printer (6:18 – 6:54)
- A student guessed it. **The only thing Microsoft 365 doesn't give an organisation is a printer.**
- *"You can rent everything, but you cannot rent the printer."* You still need the hardware with you. That's why personal printers are still popular.

### Why this matters for your career (7:01 – 7:55)
- *"If you know Microsoft 365 only, you can manage the entire organisation."*
- Every company needs business email, a telephone system, usernames and passwords, device and app management, storage, security and business apps. **All are in Microsoft 365.**

### Student Q&A: what does "security" mean here? (7:57 – 8:48)
- Security means things like **blocking access** or **restricting users from logging in from another country**. This is done by **cybersecurity** people.
- *"We are not cybersecurity engineers, we are **IT support engineers**."* So security isn't covered, but **the licence automatically gives these services**.
- Once you know all of this, you can later **upgrade your career to cybersecurity**.

### Recap by the instructor (8:55 – 10:59)
- Microsoft 365 is a **complete cloud-based business suite**. Whatever the organisation needs comes from one place, like a shopping centre.
- **No hardware needed**: *"no server, no routers, no networking required."*
- Log in from a **browser**. You can even work from a **personal computer**. The company may give you a device, or you use your own.
- Call a mobile, call another person, organise meetings. *"You don't need Zoom, everything is here."*
- With Intune you can **install and uninstall apps, write policies and remotely update computers**. You don't need to be physically present, *"as long as the device has internet and power."*

---

## Part 3 — Single sign-on, Office 365 vs Microsoft 365 (11:02 – 12:43)

### Single sign-on (SSO) (11:02 – 11:57)
- A student asked whether Microsoft 365 and Azure are linked. **Yes.**
- **SSO (Single Sign-On):** *"One username and password replicates to every Microsoft product."*
- Users created in Azure (from the earlier Azure classes) are the **same users** in Microsoft 365. **You don't recreate usernames and passwords**, and policies come across automatically.
- 📘 **Note:** They're the same because Azure and Microsoft 365 share the same **Entra ID** directory.

### Office 365 vs Microsoft 365 (12:03 – 12:43)
- **No difference in name.** *"Office 365 is the older name, Microsoft 365 is the new name."* Microsoft 365 added some extra features, like security and more admin panels.
- **Interview tip:** If an interviewer asks *"Do you have experience with Office 365?"*, **say yes**. It is the same thing you learned as Microsoft 365.

---

## Part 4 — Business vs personal email and Teams (12:49 – 16:04)

### Can a big company with 1,000+ staff use it? (12:49 – 13:05)
- Yes. *"You can create even millions of users. You just need to pay."*

### Business email vs personal email (13:05 – 14:00)

| | **Personal email** | **Business email** |
|---|---|---|
| Example | `yourname@outlook.com`, `@hotmail.com` | `yourname@yourcompany.com` |
| Whose name is in the address | **Microsoft's** | **Your company's** |
| Cost | **Free** | **Paid** (per user) |
| Storage | Very limited | More |
| Security | None | Yes |
| **Admin panel** (create users etc.) | **No** | **Yes** |

- **Exchange Online** is Microsoft's mail server. **Outlook.com** is the free personal version.

### Microsoft Teams: business version (14:05 – 16:04)
- The course uses **Teams (business)**, not the personal version.
- The instructor showed his own Teams:
  - **Meetings**, screen sharing, recording.
  - An integrated **telephone system**: *"Someone can call this number from the USA and it rings me here."*
  - **Chat**, calling any staff member, scheduling and rescheduling meetings.
  - **Remote screen sharing and remote support**.
- **Everything in the course is the business version.** Free personal accounts have limited features, limited storage, no security and no admin panel.

---

## Part 5 — Licences (16:05 – 30:30) ⭐ important

*"This is cloud, which means we rent all the services. That's why we need to know the licences. It's not free."*

> The prices below are what the instructor said in class (AUD, approximate). Prices change. Check Microsoft's website before quoting them.

### 1. Personal & Family: NOT for business (16:22 – 18:34)
- **Microsoft 365 Personal:** about **AUD 159/year**. Sign in on up to **5 PCs**, all Office apps, **1 TB** OneDrive (the free account has only **5 GB**).
- **Microsoft 365 Family:** about **AUD 179/year**.
- Gives the apps and storage, but **no business features**.
- In Australia, the USA and Europe people **pay** for Office. Cracked copies are uncommon there.
- If a customer asks *"I just want Word/Excel at home"*, suggest Personal or Family.

### 2. Business plans: up to 300 staff (18:38 – 23:31)
*"If your organisation has up to 300 staff, go with Business."*

| Plan | What you get | What's missing | Price said in class |
|---|---|---|---|
| **Business Basic** | Business **email**, **storage**, **web versions** of Word/Excel/PowerPoint (use in the browser only) | **Can't download apps**, **no security, no Intune** | ~AUD 9 per user/month (~6–7 USD) |
| **Business Standard** | Everything in Basic **plus downloadable desktop apps** (install Word, Excel etc. on the computer) | Still **no security, no Intune** | About **double** Basic |
| **Business Premium** ⭐ | Everything in Standard **plus Intune** (device & app management), **security**, identity management | Nothing we need | Highest of the three |

- **Web apps** means you can use Word, Excel and PowerPoint **in the browser**, but you **can't install them** on the computer.
- Why is Standard double the price of Basic? Because you're also paying for the desktop apps. Buying them separately (like the ~AUD 179/year personal plan) costs more.
- **Business Premium is the best.** *"Most companies are using Business Premium."* Companies manage computers from the cloud and need basic security.
- **The class practises on Business Premium.**

### 3. Enterprise plans: more than 300 staff (23:36 – 25:26)
- **E3, E5, E7**. E7 is *"the most expensive and the last option. It has everything Microsoft provides."*
- Prices said in class: **E5 ≈ AUD 85/user/month**, **E7 ≈ AUD 148/user/month**.
- Example: 1,000 staff on the top plan is about AUD 148,000 **per month**, for licences alone.
- Only big companies can afford them, e.g. Cisco, Microsoft, Google and large enterprises.

### 4. Government plans (25:26 – 26:15)
- **G3, G5**. **Only government agencies can buy these.**

### 5. Education plans (28:24 – 28:41)
- **A1, A3, A5** for colleges and universities. You don't need to learn these in detail.

### 6. Frontline plans (30:30 – 30:45)
- **F plans** (e.g. F1, F3) for **frontline workers** such as hospital, police and army staff. A student shared a licensing map in the chat. You don't need to memorise it.

### Why use the cloud? The instructor's analogies (26:34 – 28:22)
- One provider replaces separate companies for **email hosting, website hosting** and so on.
- *"If you have money, why cook at home? Go to the restaurant."*
- **Security:** a restaurant must follow **food compliance**, so it's safer. Microsoft has more security engineers than any single company.
- *"You don't need to buy the car. Uber is coming. Don't buy a house for a holiday, use Airbnb. Experience a Lamborghini for one day instead of buying it."* **That's the cloud.**

### ⭐ Interview tip on licences (28:41 – 29:37)
- In an interview at a **regional or small company**, don't say *"we used an Enterprise licence"*. They won't believe you, because a small company doesn't use E5.
- **Say: "Our company uses Business Premium, and we manage devices with Intune."** Everything taught in the course is covered by that licence.
- Education sector uses **A** plans, government uses **G** plans, very big companies use **E** plans. **Starting your career, Business Premium is the best answer.**

**Summary so far (29:39):** what Microsoft 365 is, its services, and its licences.

---

## Part 6 — Free trial and logging in to the admin center (30:59 – 44:27)

### Free trial (30:59 – 32:21, 39:37 – 41:07, 43:04 – 44:27)
- Search Google for **"Microsoft 365 Business Premium trial"** and click **Try free**.
- **One card = one trial = 25 licences** for **one month**, free.
- The trial **can be extended** (the instructor said up to another two months, about three months in total). *"More than enough for our class."*
- A payment card is needed. **Cancel before the trial ends**, or you'll be charged. *"Put it in a calendar and set an alarm a couple of days before."*
- The same card can be used for an **Azure** trial and a **Microsoft 365** trial. They're separate products. Each product gives a trial **only once** per card.
- The Business Premium trial includes: **Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, OneDrive, SharePoint, email, Intune, security.**
- After sign-up you land in the **Microsoft 365 admin center**.
- Students don't need their own trial. **They practise on the instructor's tenant**, and everyone gets the same admin dashboard. You can add your own company for practice if you want.

### Logging in to the admin center (33:09 – 34:36)
- **admin.microsoft.com** (the best way). It now redirects to **admin.cloud.microsoft**.
- Or go to **office.com** and click **Admin**.
- In a real company, IT creates your username and password. **Only IT staff get the admin dashboard**, not normal users.
- Students won't see the admin dashboard until they are given a role (Part 16).

### Marketplace (34:40 – 35:14)
- Inside the admin center there's a **Marketplace**, where you can buy or try anything Microsoft offers.
- *"Like the food court in a big shopping centre."*

---

## Part 7 — Buying a domain name (35:29 – 39:12, 44:44 – 45:48)

- The class uses a domain bought the week before: **jobforit.online**.
- Everyone's email will be **firstname@jobforit.online**.
- Domains can be bought from **GoDaddy**, **Crazy Domains**, **Namecheap**, or any domain seller. Pick the cheapest or best one.
- Costs: **.online ≈ $2**. **.com costs more** (~$30–40).
- **Microsoft doesn't sell domain names.** You buy the name elsewhere and connect it to Microsoft 365.
  - *"Like a veggie restaurant that says: we don't sell alcohol, but you can bring it from outside and drink it here."*

---

## Part 8 — Adding the domain to Microsoft 365 and DNS records (42:01 – 1:07:09) ⭐ important

**First job in a new tenant: add the company domain.**
**Path: Admin center → Settings → Domains → Add domain**

### Why DNS records are needed (46:53 – 47:52)
- When you add the domain, **Microsoft gives you some DNS records** to add at **GoDaddy** (or wherever the domain is hosted).
- *"They don't trust each other by default."* The records prove you own the domain.
- The instructor's analogy: in an office in Nepal or India, *"take this copy, go to room number X, get it signed, then come back here."* Microsoft gives you a code, you put it at GoDaddy, then Microsoft checks it and says everything is fine.

### What is DNS? (48:02 – 49:47)
- **DNS = Domain Name System** (a student said "domain name server").
- **Devices only understand IP addresses.** Names like *facebook.com* exist only to make life easy for humans.
- Phone analogy: *"Can you call me without my name, if you have my number? Yes. Can you call me with only my name and no number? No."* The name is meaningless to the device without the number (IP).
- DNS is the **translator**, the middleman between names and IP addresses.

### The four DNS records Microsoft 365 needs (49:49 – 51:31)

| Record | Stands for | What it does |
|---|---|---|
| **MX** | Mail Exchange | **Sends and receives email.** *"Without this record, you cannot send or receive email."* |
| **TXT** | Text | **Verifies the domain**, proving the name is yours |
| **CNAME** | Canonical name (shortcut name) | **Autodiscover**: Outlook finds the mail settings automatically. *"If you type 'Binod', the rest of the address comes automatically."* |
| **TXT (SPF)** | Sender Policy Framework | **Outlook protection**: says which servers may send email for your domain (anti-spoofing) |

📘 **Note:** Autodiscover's main job is letting Outlook find the mailbox settings automatically when you add an account.

### Two ways to add the records (52:11 – 53:22, 1:04:06 – 1:07:09)

**Option 1: automatic (easiest)**
- In the Microsoft wizard, choose your DNS host (GoDaddy), **sign in to GoDaddy**, and click **Connect**.
- *"You don't need to do anything. You don't even need to touch it."* Microsoft adds the records itself.

**Option 2: manual**
1. In Microsoft 365, copy each record's details: **type, host name, value, priority, TTL**.
2. In GoDaddy go to your domain → **DNS** → **Add new record**.
3. Example MX record:
   - **Type:** MX
   - **Host name:** @
   - **Value:** (copied from Microsoft)
   - **Priority:** 0
   - **TTL:** 1 hour
4. **Save**. Repeat for the TXT, CNAME and SPF records.

### Domain status must be "Healthy" (55:25 – 56:44, 1:00:28 – 1:02:59)
- After adding the records, the domain status must show **Healthy**. **If it isn't healthy, email won't work.**
- It **takes some time** for DNS changes to replicate. Wait and refresh.
- The instructor also made the domain the **default (primary)** domain, so new users get `@jobforit.online` instead of `@….onmicrosoft.com`.
- He had a **browser cache** problem during the demo. Refreshing or using another browser window fixed it.

### Revision of the domain steps (1:05:07 – 1:07:09)
1. Buy the name at GoDaddy (or any seller).
2. M365 admin center → **Settings → Domains → Add domain** → type the name.
3. If the domain is at GoDaddy, **sign in to GoDaddy** and the records are added automatically.
4. If not, **copy each record** and add it manually.

---

## Part 9 — Getting the licence (56:46 – 59:08, 1:07:24 – 1:07:49)

**Path: Admin center → Marketplace → All products → Microsoft 365 Business Premium → Details → Start free trial**
- You get **25 licences**, **$0 now**, **one month free**.
- Either get the trial from Google (Part 6) or from the Marketplace. **Both give the same trial.**

**Student question: bank OTP (59:22 – 1:00:16).** A student asked about the OTP their bank sends for card payments. That OTP is **the bank's own security feature**, not Microsoft's. You can manage it in your banking app's card settings.

---

## Part 10 — Onboarding a new user (1:07:52 – 1:09:47) ⭐ important

*"The first job is onboarding."* When a company hires someone, **creating their account is IT's job**. This is called **onboarding**.

**Path: Admin center → Users → Active users → Add a user**

1. **Basics:** first name, last name, display name, **username** (e.g. `roshan@jobforit.online`).
2. **Password.** You have two choices:
   - **Auto-generate password:** the system creates one.
   - **Let me create the password:** type your own.
   - **"Require this user to change their password when they first sign in"** makes it a **temporary** password. Leave it unticked for a **permanent** password.
3. **Product licences:** *"The very important part is the licence."* Assign **Business Premium**, so the user gets everything.
4. **Roles:** give **no admin role** to a new starter. Roles can be given later.
5. **Finish.** The user now has a **temporary username and password**.

Then **guide the user**. Share the password and help them sign in to **Outlook, Teams, OneDrive and SharePoint**. *"The system gives us the account, but we need to guide them."* Start by checking Outlook.

---

## Part 11 — First login, MFA and testing email (1:09:47 – 1:16:30)

### First login (1:09:47 – 1:12:37)
1. Go to **outlook.office.com**.
2. Type the **username** (`firstname@jobforit.online`) and the **temporary password**.
3. You're asked to **change the password**. **Current password** = the temporary one. **New password** = your own **strong** password.

### MFA setup: "You need to secure your account" (1:12:37 – 1:14:56)
After the password, Microsoft asks you to **secure your account**. This is **MFA (multi-factor authentication)**.

1. On your phone, download **Microsoft Authenticator**. Make sure it's **Microsoft** Authenticator, not another authenticator app.
2. On the computer, click **Next** until a **QR code** appears.
3. In the app tap **+ (plus)** → **Work or school account** → **Scan QR code**.
4. Scan the QR code on the computer screen with the **phone camera**, then click **Next**.
5. Enter the **number/code** shown to approve the test sign-in.
6. *"This is for security reasons."* Now you're in Outlook.

### Test email (1:15:02 – 1:16:30)
- *"First let's test whether email is working."*
- Everyone **sends an email from their personal Gmail** to the new business address.
- It arrived: *"Now this email is 100% working."*
- 📘 **Note:** This proves email from the internet reaches the mailbox, which means the **MX record** is correct.

---

## Part 12 — Assigning licences (1:16:33 – 1:20:07) ⭐ important

- **Only users with a licence get a mailbox.** In class, only the licensed users (with Business Premium) could get email.
- You can see who has which licence in **Users → Active users**.

**Assign licences in bulk:**
1. **Users → Active users** → **tick the users** (the class did 9 at once).
2. Click **… (more) → Manage product licences**.
3. Choose:
   - **Assign more**: add a licence and keep the existing ones.
   - **Replace**: *"kick out the previous one and add the new one."*
4. Select **Microsoft 365 Business Premium** → **Save changes**.
5. Check the licence column to confirm.

---

## Part 13 — Creating many users at once with a CSV file (1:20:10 – 1:28:11) ⭐ important

*"If the organisation has many new staff, don't do it one by one."* For example, colleges and universities enrol many students at once. Creating a couple of users manually is fine, but many by hand is slow and error-prone.

**Path: Admin center → Users → Active users → Add multiple users**

1. Choose to upload a **CSV** file.
2. If you're not sure of the format, **download the blank CSV with the required headers** (or the **sample CSV**). *"This is the best one if you don't know anything."*
3. The template has columns like: **Username, First name, Last name, Display name, Job title, Department, Office number, Office phone, Mobile phone, Fax…** Delete the columns you don't need.
4. Fill in the rows (the class used Job title = *IT Support*).
5. **Build the username with an Excel formula** instead of typing each one:
   ```
   =CONCATENATE(B2,"@jobforit.online")
   ```
   (B2 = the first-name cell.) In class the **"@"** was forgotten at first. Make sure it's inside the quotes. Drag the formula down for all rows.
6. **Save as CSV** → **Browse** → upload → **Next**.
7. **Assign the licence** (Business Premium) → **Finish**.

---

## Part 14 — Resetting passwords (1:28:11 – 1:31:09, 1:36:19 – 1:36:50)

**Reset many passwords at once:**
1. **Users → Active users** → tick all the new users.
2. Click **Reset password**.
3. Set **one temporary password** for all of them, and keep **"require change at next sign-in"** on.
4. Share it with the users. They must change it when they first sign in.

**Reset one user's password** (e.g. they forgot it): find the user → click **Reset password** → give the new temporary password.

---

## Part 15 — Helping users sign in: real troubleshooting (1:31:10 – 2:00:40)

Getting every student signed in took about 30 minutes. It's a realistic picture of first-day IT support. The instructor said: *"Your customers will call you any time they have an issue. That's why no theory is required here. Everything is practical."*

| Problem seen in class | Cause | Fix |
|---|---|---|
| "No account found with that username" | Typed the **wrong domain** (`.com` instead of `.online`) | Type the exact username: `firstname@jobforit.online` |
| "Your account is temporarily locked" | **Too many wrong passwords** | Admin **resets the password** |
| Password rejected when changing | Doesn't meet the **password policy** | Use a **strong** password (long, with upper case, lower case, numbers and symbols) |
| User confused by "current password" | — | Current password = **the temporary one** the admin gave |
| User signs in but has no mailbox | **Licence given to the wrong person** (two users with similar names, *Kabita* and *Kavita*) | Check the name carefully and assign the licence to the right user |
| Page keeps showing old or wrong info | **Browser cache**, or already signed in with another account | Use an **Incognito / private window** |
| "Authenticator registration has timed out" | Took too long to scan | Click **Next** / try again. Scan within the time limit. |
| Phone can't scan the QR code | Camera problem | Choose **"Can't scan image?"** and **enter the code manually** in the app |
| Wrong authenticator app installed | Another app, not Microsoft's | Install **Microsoft Authenticator** |
| Forgot the Authenticator app PIN | — | Delete and **reinstall the app**, then register again |
| Joining the class from a mobile | Can't be guided or share a screen | Join from a **computer** |

### How an admin checks whether a user has set up MFA (1:38:10 – 1:39:48, 1:55:19 – 1:57:09)
1. Admin center → **Admin centers → Microsoft Entra** (or **portal.azure.com**, which redirects there).
2. **Users** → search for the user → **Authentication methods**.
3. If they've registered, you'll see their **phone / Microsoft Authenticator** (e.g. "iPhone 13").
4. If nothing is registered, MFA isn't set up yet.
5. **To make a user set up MFA again** (new phone, broken setup): **delete / revoke** the existing method there. The user then registers again at next sign-in.

### Other points
- An admin can see **where a user is signing in from** (location) in the sign-in logs. The instructor saw a student signing in from Australia.
- Microsoft lets users **postpone MFA setup for up to 14 days** ("Not now"). After that it's required.
- **Summary by the instructor (1:58:14):** *"Typing a username and password is not IT, it's like Facebook. But what is the requirement nowadays when logging in? **Multi-factor authentication**. Security is required to set up or log in to a business account."*
  - Download **Microsoft Authenticator** → tap **+** → **Work or school account** → either **Sign in** or **Scan QR code**.
  - Sign in to Outlook on the web at **outlook.office.com**.

---

## Part 16 — Outlook on desktop and mobile (2:00:43 – 2:07:40)

*"You need to help other staff connect Outlook everywhere they want."*

### Outlook desktop app
1. Open **Outlook** on the computer → **Add account** (or *another account*).
2. Type the **username** → **password** → **MFA**: open Microsoft Authenticator, tap the account and enter the **code** it shows.
3. Tick **"Don't ask again"** and it won't ask for MFA again on that device for a while (the instructor said 7 days).
4. The same mailbox now appears in the desktop app.

### Outlook mobile app
- Install **Outlook** on the phone → **Add account** → same username, password and MFA.
- **No DNS setup is needed** on the user's side. Just add the account.

📘 **Note:** One user saw *"does not have permission to access the new Outlook"*. Switching to the classic Outlook, or waiting for the admin to allow new Outlook, fixes it.

---

## Part 17 — Outlook task 1: email signature (2:07:43 – 2:13:32)

*"This is your job: help other staff set up their signature."*

**Path (web or app): Settings ⚙ → Account → Signatures**
1. Click **New signature** and give the signature a **name**. This is only the name of the signature, not the person.
2. Type the signature, for example:
   ```
   Kind regards,
   Binod
   IT Engineer, Job For IT
   binod@jobforit.online
   www.jobforit.online
   Mobile: 04xx xxx xxx
   ```
3. ⭐ **Set the defaults:** choose this signature for **"For new messages"** and **"For replies/forwards"**. These are the **two dropdowns** the instructor stressed.
   - Without this, the user must insert the signature manually each time. *"Some students do it this way. It should come automatically."*
4. **Save**, then send a test email and check that the signature appears on a **new** email and on a **reply**.

---

## Part 18 — Outlook task 2: automatic replies (out of office) (2:13:40 – 2:18:47)

**What it is:** when you're on holiday, Outlook automatically replies with a message like *"I'm on holiday, please contact another person."* Setting this up is a common IT support task.

**Path: Settings ⚙ → Account → Automatic replies**
1. **Turn on** automatic replies.
2. Tick **"Send replies only during a time period"** and set the **start and end** (e.g. from 5 PM today to 5 PM tomorrow, or a whole week).
3. Write the message, e.g.:
   > Hi, I am on holiday for one week until the end of May. For any IT-related issue please contact Aman at aman@jobforit.online. I will get back to you when I return.
4. ⭐ Also tick **"Send replies outside your organisation"**. *Outside* means Gmail, Yahoo or other companies. Without this, only colleagues get the reply.
5. **Save** and test by emailing that user.

---

## Part 19 — Getting support (2:21:37 – 2:26:18)

- Students who need extra help should contact the **support team** (former students who are now working). They're free, can be tagged or called in the group any time, and can give extra classes.
- *"If you want to get a job, you need to get a lot of support."*

---

## Part 20 — Outlook task 3: rules (2:26:24 – 2:36:17) ⭐ very important

**What a rule is:** Outlook **automatically sorts incoming email**.
- *"Surendra is my manager. I don't want to miss his email, so I want a separate folder for him."*
- Put sales emails in one folder. Move junk and marketing emails away. The inbox has too many emails to find the important ones by hand.

**Path: Settings ⚙ → Mail → Rules → Add new rule**

### Example 1: manager's emails into their own folder
1. **Name:** *Manager email*
2. **Condition:** **From** → Aman (the "manager")
3. **Action:** **Move to** → **create a new folder** → *My manager*
4. Tick **Run rule now** to move existing emails too. In class, 2 old emails moved immediately.
5. **Save** and test: Aman sends an email, and it goes straight to *My manager*, not the Inbox.

### Example 2: a whole department into one folder
- **Edit** the rule (or make a new one), add **several senders** (Aman, Kabita, Vishnu), and move them to a new folder called **IT Department**.
- You can create **sub-folders** under Inbox for each department (sales, marketing, IT…).

### Example 3: marketing emails by keyword
1. **Name:** *Sales or marketing*
2. **Condition:** **Subject or body includes** → *sales, marketing, offer, discount* (any keywords you choose)
   - A student asked whether it checks only the subject. **You can choose subject, body, or both.**
3. **Action:** **Mark as junk** (or move to a folder, or delete, whichever you prefer)
4. Test: send an email with "sales" in the subject. It went to **Junk**.
5. One test email didn't match because the keyword was typed differently (misspelled or odd capitals). **Add the variations you expect**, because the rule only matches the words you enter.

- There are **many more conditions and actions** (*"thousands of options"*). Practise making your own.

---

## Part 21 — Admin roles (2:36:17 – 2:40:55) ⭐ important

- **Old students** can already see the admin dashboard. **New students** can't yet, so they need a role.
- *"How to add an IT role."* There are mainly **four options**. These three were explained:

| Role | What it can do | Instructor's comment |
|---|---|---|
| **Helpdesk Administrator** | **Only reset passwords**, and only for **non-admin** users | *"In a couple of weeks you'll get this permission."* |
| **User Administrator** | **Create, delete and manage users**, reset passwords, manage **groups**, filters, service requests | **Given to new students now** so they can do everything the instructor does with users |
| **Global Administrator** | **Everything.** Also called super admin. | *"It is the **master key**."* New students get it **next week** |

📘 **Note:** Giving each person only the lowest role they need is called **least privilege**. That's why nobody gets the master key on day one.

### How the instructor assigned the role (2:38:19 – 2:40:22)
- He first tried to give the role to several users at once from the user list: *"I think you cannot give it in bulk."*
- So he went to **Roles**:
  1. Admin center → **Roles → Role assignments**
  2. Select **User Administrator**
  3. **Assigned → Add users** → add the new students → **Add**
- 📘 One user at a time: **Users → Active users → user → Manage roles → Admin center access → tick the role → Save**.

### Logging in as an admin (2:40:39 – 2:42:08)
- Go to **admin.microsoft.com**. *"You will see the dashboard, but it might take a couple of minutes."*

---

## Part 22 — Wrap-up (2:41:12 – 2:42:08)

- Tomorrow: **revise everything** and go a bit faster.
- **5 days** for this topic, with **many practice questions**.
- Practise, **re-watch the video**, and get help from the support team.
- *"This is very important. Start applying for jobs immediately after this course."*
- Remaining: Microsoft 365 this week, then **Intune** next week. *"Small topics, but very important topics."*

---

## Quick reference: URLs

| URL | What |
|---|---|
| **admin.microsoft.com** (→ admin.cloud.microsoft) | Microsoft 365 admin center |
| **office.com** | M365 home page → *Admin* tab for admins |
| **outlook.office.com** | Outlook on the web |
| **portal.azure.com** / **entra.microsoft.com** | Entra ID: users, authentication methods (MFA) |

## Quick reference: admin center paths

| Task | Path |
|---|---|
| Add domain | Settings → Domains → Add domain |
| Get trial / buy licence | Marketplace → All products → Business Premium → Start trial |
| Add one user | Users → Active users → Add a user |
| Add many users | Users → Active users → Add multiple users (CSV) |
| Bulk licences | Users → Active users → select → Manage product licences → Assign more / Replace |
| Reset password (one or many) | Users → Active users → select → Reset password |
| Assign admin role | Roles → Role assignments → role → Add users |
| Check a user's MFA | Entra → Users → user → Authentication methods |

## Quick reference: Outlook paths

| Task | Path |
|---|---|
| Signature | Settings → Account → Signatures (set both defaults!) |
| Out of office | Settings → Account → Automatic replies (tick "outside your organisation") |
| Rules | Settings → Mail → Rules → Add new rule |

## Glossary

| Term | Meaning |
|---|---|
| **Microsoft 365 / Office 365** | Same thing (new and old names): Microsoft's cloud business suite |
| **SaaS** | Software as a Service. You rent the software, no hardware needed. |
| **Exchange Online** | Microsoft's cloud email server |
| **Teams** | Chat, meetings, calls, telephone system, screen sharing |
| **Entra ID** | Cloud version of Active Directory: users, passwords, MFA, roles |
| **Intune** | Device and app management (MDM/MAM) |
| **OneDrive / SharePoint** | Personal storage / business storage |
| **SSO** | Single sign-on: one username and password for all Microsoft products |
| **Tenant** | A company's own Microsoft 365 space (the instructor's company in class) |
| **DNS** | Translates names to IP addresses |
| **MX / TXT / CNAME / SPF** | Email delivery / domain verification / autodiscover / email protection |
| **Onboarding** | Creating accounts and setting up a new staff member |
| **Temporary password** | One-time password the user must change at first sign-in |
| **MFA** | Multi-factor authentication: password + Microsoft Authenticator |
| **Licence** | Gives a user a mailbox, apps and services. No licence means no email. |
| **Role** | Admin permissions: Helpdesk, User Admin, Global Admin |

---

## Practice tasks for the student

1. Sign in at **outlook.office.com**, change the temporary password, and set up **MFA** with Microsoft Authenticator.
2. Send an email **from Gmail** to your business address, and reply.
3. Add your business account to **Outlook desktop** and **Outlook mobile**.
4. Create a **signature** and set it as default for new messages **and** replies. Test both.
5. Set up **automatic replies** for tomorrow, for inside **and** outside the organisation. Test from Gmail.
6. Create **3 rules**: (a) a sender → own folder, (b) several senders → department folder, (c) keywords → Junk.
7. (With User Admin) **Create one user** manually with a temporary password and a Business Premium licence.
8. Create **5 users with a CSV** file, using the `CONCATENATE` formula for usernames.
9. **Assign licences** to several users in bulk, and try **Replace** vs **Assign more**.
10. **Reset passwords** for several users at once.
11. In **Entra ID**, check a user's **Authentication methods** to see if MFA is set up.
12. Look at **Settings → Domains** and find the **MX, TXT, CNAME and SPF** records for the domain.

## Review / interview questions (with answers)

1. **What is Microsoft 365?**
   A complete cloud-based (SaaS) business suite. Email, telephone/Teams, identity, device management, storage, security and Office apps from one place.
2. **Is Office 365 different from Microsoft 365?**
   No, it's the same product. Office 365 is the old name.
3. **What's the one thing Microsoft 365 can't give a business?**
   A printer.
4. **Which service gives business email? Which gives VoIP and remote support? Which gives identity? Which manages devices?**
   Exchange Online, Teams, Entra ID and Intune.
5. **What is Entra ID?**
   The cloud version of Active Directory. Usernames, passwords, MFA, roles and groups.
6. **What is the difference between OneDrive and SharePoint?**
   OneDrive is personal storage. SharePoint is business storage.
7. **What is SSO?**
   Single sign-on. One username and password works across all Microsoft products.
8. **What is the difference between @outlook.com email and business email?**
   Outlook.com is free and uses Microsoft's name, with limited storage, no security and no admin panel. Business email uses the company's domain, is paid, and has an admin panel.
9. **What is the maximum number of users on a Business plan?**
   300. More than that needs Enterprise (E3/E5/E7).
10. **What's the difference between Business Basic, Standard and Premium?**
    Basic: email, storage and web apps. Standard: plus downloadable desktop apps. Premium: plus Intune and security.
11. **In an interview, which licence should you say your company uses? Why?**
    Business Premium. It's what small and medium companies use and it covers Intune. Saying Enterprise at a small company isn't believable.
12. **Which licence types are for government, education and frontline workers?**
    G (G3/G5), A (A1/A3/A5) and F.
13. **How many licences does the Business Premium trial give, and for how long?**
    25 licences for one month (it can be extended).
14. **What URL is the admin center?**
    admin.microsoft.com.
15. **Does Microsoft sell domain names?**
    No. Buy the name from GoDaddy (or similar) and connect it to Microsoft 365.
16. **What is DNS?**
    It translates human-friendly names to the IP addresses devices understand.
17. **What do the MX, TXT, CNAME and SPF records do?**
    MX sends and receives email. TXT verifies the domain. CNAME is for autodiscover. SPF protects against spoofing.
18. **The domain isn't "Healthy". What happens?**
    Email won't work. Check the DNS records and wait for them to replicate.
19. **What is onboarding? What's the most important step when creating a user?**
    Setting up a new staff member's account. The most important step is assigning the licence.
20. **How do you create 200 users at once?**
    Add multiple users with a CSV file. Download the template and build the usernames with CONCATENATE.
21. **What's the difference between "Assign more" and "Replace" in Manage product licences?**
    Assign more adds a licence and keeps the existing ones. Replace removes the old licence and gives the new one.
22. **A user says "account temporarily locked". What do you do?**
    It's caused by too many wrong passwords. Reset their password.
23. **A user signs in but has no mailbox. What do you check?**
    Their licence. Check it was assigned to the right person.
24. **A user got a new phone and can't do MFA. What do you do?**
    In Entra ID → user → Authentication methods, delete the old method. They register again at next sign-in.
25. **Which app is used for MFA? What are the steps?**
    Microsoft Authenticator. Tap + → Work or school account → Scan QR code.
26. **A user's signature only appears when they insert it manually. Why?**
    The default signature for new messages and replies/forwards isn't set.
27. **Outside customers don't get a user's out-of-office message. Why?**
    "Send replies outside your organisation" isn't turned on.
28. **What is an Outlook rule? Give an example.**
    It sorts incoming email automatically. For example, move all email from the manager into a "My manager" folder.
29. **What can a Helpdesk Admin, User Admin and Global Admin each do?**
    Helpdesk Admin resets passwords for non-admins. User Admin creates and manages users and groups. Global Admin can do everything (the master key).
30. **Why not give every IT person Global Admin?**
    Least privilege: each person gets only the access they need.
