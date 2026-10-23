# Microsoft 365 for IT Support
## Part 3 — Managing Devices and Applications: Intune, Compliance, Policy and Autopilot

---

## Preface to Part 3

Parts 1 and 2 were about **accounts**. What Microsoft 365 is, how licensing works, how to connect a domain, how to create users, how to get them signed in, and then everything that happens to a mailbox afterwards — aliases, delegation, forwarding, groups, shared mailboxes, offboarding.

**Part 3 is about the thing the account signs in from.** The laptop. The phone. The tablet in the warehouse.

This is a different kind of work, and in many organisations it's a different job title — *endpoint engineer*, *desktop support*, *EUC* (end-user computing). But it's the same admin center family, the same identities, the same licences, and for a Level 1 or Level 2 support person it lands in the same ticket queue. The questions it answers are:

- *"We've bought 600 laptops. Who's going to set them all up?"*
- *"A contractor wants work email on her own phone, but she's not letting us manage her phone."*
- *"Someone left their work iPhone in a taxi. What now?"*
- *"Finance need this one application. Nobody else should have it."*
- *"Someone's resigned. Their laptop is going to the new starter on Monday."*
- *"Can you make sure nobody can use the camera on the factory floor tablets?"*
- *"I've joined the laptop to the company but I still can't install anything on it remotely. Why?"*

Every one of those is answered in this part, and the last one in particular catches out people who have been doing the job for a while.

A warning that belongs at the front rather than buried in a chapter. **The tools in this part are destructive.** Part 2's worst mistake was an email going to the wrong person. Here, one wrong click factory-resets somebody's phone, and there is no undo and no restore. Chapter 37 is about exactly this, and it's worth reading before you touch a live tenant.

### How this book is organised

Each chapter contains:

- **What you will learn:** the goals of the chapter.
- **The explanation:** the main content, in plain language.
- 💡 **Explain it like this:** analogies you can use when teaching.
- 🛠️ **Hands-on:** step-by-step tasks.
- 🏢 **In the real world:** how the topic appears in an actual IT job.
- ⚠️ **Careful:** mistakes that are expensive, and the ones the course video itself gets wrong.
- 🎯 **Interview corner:** what employers ask and how to answer.
- ✅ **Check your understanding:** questions with answers at the end of the chapter.

Chapter numbering continues from Part 2, so this part starts at Chapter 28. The examples use the fictional company **Contoso** (`contoso.com`), as before.

---

## Contents

28. [Endpoint Management: What Intune Is and Why It Exists](#chapter-28--endpoint-management-what-intune-is-and-why-it-exists)
29. [The Intune Admin Center](#chapter-29--the-intune-admin-center)
30. [Enrolling Apple Devices](#chapter-30--enrolling-apple-devices)
31. [Enrolling Windows Devices](#chapter-31--enrolling-windows-devices)
32. [Compliance Policies](#chapter-32--compliance-policies)
33. [Configuration Profiles](#chapter-33--configuration-profiles)
34. [Deploying Applications](#chapter-34--deploying-applications)
35. [Targeting: Groups and Assignments](#chapter-35--targeting-groups-and-assignments)
36. [The Device Page: Inventory and Remote Actions](#chapter-36--the-device-page-inventory-and-remote-actions)
37. [Retire, Wipe and Delete](#chapter-37--retire-wipe-and-delete)
38. [App Protection and the BYOD Problem](#chapter-38--app-protection-and-the-byod-problem)
39. [Windows Autopilot and Zero Touch](#chapter-39--windows-autopilot-and-zero-touch)
40. [Troubleshooting Intune](#chapter-40--troubleshooting-intune)
41. [Career: Scenarios and Interview Practice](#chapter-41--career-scenarios-and-interview-practice)

Appendices
- [G. Quick Reference: Where Every Intune Setting Lives](#appendix-g--quick-reference-where-every-intune-setting-lives)
- [H. Glossary for Part 3](#appendix-h--glossary-for-part-3)
- [I. Lab Workbook for Part 3](#appendix-i--lab-workbook-for-part-3)

---

# Chapter 28 — Endpoint Management: What Intune Is and Why It Exists

### What you will learn
- What an endpoint is, and what endpoint management means
- The definition of Intune, in one sentence you can say in an interview
- MDM and MAM, and why the difference matters
- SCCM versus Intune
- Zero Touch Provisioning
- What Intune genuinely cannot do

## 28.1 The problem

Contoso has 400 staff. Forty are remote. Twelve are in Manila, six in Auckland, and one works from a farm with satellite internet. Every one of them has a laptop, most have a work phone, and the warehouse has thirty shared tablets.

Those 800-odd machines all need:

- The right software installed, and kept up to date
- The company's settings applied — Wi-Fi, VPN, printers, security rules
- Monthly operating system patches
- Encryption switched on
- Something sensible to happen when one is lost or stolen
- Setting up on day one, and cleaning off on the last day

Someone has to do all of that. **For a long time, the answer was a person walking to a desk with a USB stick.** That stopped being possible the moment staff worked from home.

## 28.2 What an endpoint is

An **endpoint** is any device that connects to the company: laptop, desktop, phone, tablet. The word exists because "computer" stopped covering it. It's the end point of the network — where the company's data meets a human being.

**Endpoint management** is doing all of the above centrally, over the internet, without touching the device.

## 28.3 The definition

> **Microsoft Intune is a cloud-based endpoint management service that manages devices and the applications on them, remotely, from anywhere.**

The fuller version, close to Microsoft's own wording:

> *"Intune is a cloud-based endpoint management solution that manages user access and simplifies application and device management across your entire organisation. It acts as a control centre for securing corporate data on both company-owned and personally-owned devices."*

**Platforms:** Windows, macOS, iOS, iPadOS and Android, with **limited** Linux support (Ubuntu Desktop and RHEL, mainly for compliance and Edge configuration).

⚠️ **Careful:** You'll hear Linux and ChromeOS listed as if they were equals of Windows and iOS. They aren't. Linux support is narrow. **ChromeOS is not an Intune-managed platform at all** — Intune can read an inventory from the Google Admin console through a connector, but Google manages the Chromebook. In an interview, say *"Windows, macOS, iOS/iPadOS and Android, with limited Linux"*. That is both safe and accurate.

**Names:** Intune has been called **Microsoft Endpoint Manager** and **Microsoft Intune Suite**. The old names survive in the interface and in older documentation. They're the same product.

## 28.4 MDM and MAM

This is the first thing to get straight, and it comes up in interviews constantly.

| | **MDM** | **MAM** |
|---|---|---|
| Stands for | **Mobile Device Management** | **Mobile Application Management** |
| Manages | **The device** | **The application and the company data inside it** |
| You can | Enrol, lock, restart, wipe, update the OS, read the hardware inventory, push settings | Install and remove apps, require a PIN on a work app, block copy-out, encrypt company data, wipe only company data |
| Needs the device enrolled? | **Yes** | **No** — this is the important part |

> 💡 **Explain it like this:** *"MDM manages the box. MAM manages the company data inside the box. If the box belongs to the company, use MDM. If the box belongs to the employee, use MAM."*

That second sentence is the whole of Chapter 38, and it's the answer to the hardest real question in this subject.

## 28.5 SCCM versus Intune

🎯 **Interview corner:** This gets asked in nearly every endpoint interview, because most organisations have both or are migrating between them.

| | **SCCM** (System Center Configuration Manager, now Microsoft Configuration Manager) | **Intune** |
|---|---|---|
| Where the management server lives | **On-premises** — your building | **Microsoft's cloud** |
| What you must provide | A **Windows server** and a **SQL database**, installed, patched, backed up | A **subscription**. Nothing to install. |
| Reaches devices | On the corporate network or over VPN | **Anywhere with internet** |
| Platforms | Windows-centric | Windows, Apple, Android |
| Age | The older product | The current product |

**They do the same job.** The difference is where the server is, and therefore whether a laptop at someone's kitchen table can be managed.

**Running both at once is called co-management**, and it's extremely common — Configuration Manager keeps doing software deployment while Intune takes over compliance and policy, with workloads moved across one at a time. Mentioning co-management unprompted is a good signal in an interview, because it shows you know what real estates look like rather than just what the product brochure says.

> **If you're asked about SCCM and you've only used Intune:** *"I know SCCM theoretically but I've worked practically in Intune. They do the same job, and co-management means a lot of organisations run both, so I'd pick it up quickly."* That is an honest, confident answer. Claiming SCCM experience you don't have will not survive the second question.

## 28.6 Zero Touch Provisioning

Here is the normal way to set up a new starter's laptop:

1. Unbox it
2. Run through Windows setup
3. Install Office. Download it, run the installer, wait.
4. Install Teams, Zoom, the VPN client, the line-of-business app
5. Join it to the company
6. Set the Wi-Fi, the printers, the security policies
7. Block what needs blocking
8. Hand it over

**Two hours, per machine.** For 600 machines, that's 1,200 hours — thirty weeks of one person's life.

**Zero Touch Provisioning (ZTP)** inverts it:

1. **First**, you write every policy and app assignment in Intune. Once.
2. **Then** the user is handed a sealed box.
3. They switch it on, connect to Wi-Fi, and type their username and password.
4. Everything arrives by itself: the software, the settings, the restrictions, the updates.

> 💡 **Explain it like this:** *"It's the difference between cooking each guest a meal to order and setting the table before anyone arrives. The work happens once, before the first guest."*

**The order matters more than anything else in this part of the book.** Write the policies, *then* enrol the devices. Do it the other way round — hand out 300 laptops and start writing policies afterwards — and you spend the next two months chasing machines that are already on people's desks in the wrong state.

🏢 **In the real world:** This is the honest answer to *"what does an endpoint engineer actually do all day?"* They are not installing software on individual computers. **They are writing the policies that install software on every computer.** The job is authorship, not clicking.

## 28.7 What Intune cannot do

Three hard limits, and knowing them is a sign of competence rather than a weakness.

| Limit | Consequence |
|---|---|
| **It cannot touch hardware** | No adding RAM, replacing a battery, fixing a power cable or reseating a drive |
| **The device must be on and online** | If the internet is down, Intune can do nothing whatsoever |
| **It cannot fix a machine that won't boot** | A blue screen or a dead bootloader needs hands |

🎯 **Interview corner:** *"What are the limitations of remote device management?"*
**Good answer:** "Intune covers software, settings, policy and remote actions. What it can't do is hardware, and it can't do anything at all if the device is off or offline — so a machine that won't boot or has a failed drive still needs someone physically present. That's why remote management reduces desk visits rather than eliminating the role."

That answer is better than it looks, because it shows you understand the boundary of your own tooling. Candidates who claim a cloud console can fix anything get caught out.

### ✅ Check your understanding
1. What is an endpoint?
2. Define Intune in one sentence.
3. What's the difference between MDM and MAM?
4. What is the single architectural difference between SCCM and Intune?
5. What is co-management?
6. What order do you do things in, for zero touch to work?
7. Name three things Intune cannot do.

**Answers:** (1) Any device that connects to the company — laptop, desktop, phone, tablet. (2) A cloud-based endpoint management service for managing devices and their applications remotely. (3) MDM manages the whole device and needs it enrolled; MAM manages the app and the company data inside it and does not. (4) SCCM's management server is on-premises; Intune's is in the cloud. (5) Running Intune and Configuration Manager together on the same devices, moving workloads across gradually. (6) Policies first, devices second. (7) Hardware faults, anything while the device is off or offline, and a machine that won't boot.

---

# Chapter 29 — The Intune Admin Center

### What you will learn
- How to get into Intune
- What each tab is for, and which ones you'll live in
- Which admin role you should actually be using

## 29.1 Getting in

**Two routes:**

- **admin.microsoft.com** → scroll the left menu to **All admin centers** → **Intune**
- Or straight to **intune.microsoft.com**

It's a **separate portal** from the Microsoft 365 admin center, but it is not a separate world. Users, groups, tenant branding and licences are all the same objects you already know — single sign-on, one directory.

## 29.2 The tabs

| Tab | What it's for | Will you use it? |
|---|---|---|
| **Devices** | **MDM.** Enrollment, compliance, configuration profiles, every managed device, remote actions. | **This is where you live** |
| **Apps** | **MAM.** Deploying applications, app protection policies, app configuration. | **Constantly** |
| **Endpoint security** | Antivirus, disk encryption, firewall, attack surface reduction, security baselines | Sometimes. Often owned by a security team. |
| **Users** | The same users as Microsoft 365 | For checking a licence or a device's owner |
| **Groups** | The same groups as Microsoft 365 | **Yes — targeting lives here** (Chapter 35) |
| **Tenant administration** | Tenant-wide settings, Company Portal branding, roles | Occasionally |
| **Reports** | Compliance, app install and device health reporting | When someone asks for numbers |
| **Troubleshooting + support** | Per-user diagnostics, the single best-value page in the portal | **More than you'd expect** — see Chapter 40 |

**Devices → Overview** gives you a count by platform. In a new tenant, every number is zero.

## 29.3 Which role you should be using

🛠️ **Hands-on:** Check your own role at **Microsoft 365 admin center → Users → Active users → [you] → Account → Roles.**

| Role | Can do |
|---|---|
| **Global Administrator** | Everything, everywhere — including billing, domains and other admins |
| **Intune Administrator** | Everything in Intune. Nothing outside it. |
| **Help Desk Operator** | Remote actions and read access. Cannot change policy. |

⚠️ **Careful:** Training courses hand out Global Administrator because it removes a variable. **Do not carry that habit into a real tenant.** Microsoft's guidance is a very small number of Global Admins — typically two to four, plus break-glass emergency accounts — and everyone else on the narrowest role that does their job. For device work that role is **Intune Administrator**.

This matters practically, not just as box-ticking. A Global Administrator who mis-clicks can delete a domain, remove another admin, or change the billing account. An Intune Administrator who mis-clicks wipes a phone — bad, but survivable.

🎯 **Interview corner:** *"Which role would you want for this job?"* Answering **"Intune Administrator, and Help Desk Operator for the Level 1 team"** rather than "Global Admin" is a small answer that says a lot about you.

### ✅ Check your understanding
1. What are the two URLs that get you into Intune?
2. Which tab is MDM and which is MAM?
3. Which role should you use for day-to-day device work?
4. Where do you see how many devices of each platform you have?

**Answers:** (1) intune.microsoft.com, or admin.microsoft.com → All admin centers → Intune. (2) Devices is MDM; Apps is MAM. (3) Intune Administrator, not Global Administrator. (4) Devices → Overview.

---

# Chapter 30 — Enrolling Apple Devices

### What you will learn
- Why Apple devices need a certificate and Windows devices don't
- The Apple MDM Push Certificate, and the three rules that govern it
- How a user enrols an iPhone
- The step everybody misses
- Why an old iPhone can't be enrolled at all

## 30.1 Enrollment, and why Apple is different

**Enrollment** is the act of bringing a device under Intune management. Each platform does it differently, and Apple needs something the others don't: **permission from Apple.**

| Platform | Needs approval from the OS vendor? | Why |
|---|---|---|
| **Windows** | ❌ No | Microsoft makes both Windows and Intune |
| **Apple** | ✅ **Yes** — an Apple MDM Push Certificate | Different company, and a strict one |
| **Android** | ✅ Yes | Different company — you connect Intune to Google |

## 30.2 The concept: borrowing Apple's authority

Think about who is actually in charge of an iPhone today.

**Apple is.** Apple can push an iOS update to it. Apple can disable features on it. Apple decides what may be installed on it. At present Apple delegates some of that to the **user** — you get to choose whether to accept an update.

But Contoso **bought** the phone. Contoso wants that authority for itself: to decide what's installed, to block the camera on the factory floor, to wipe it if it's lost.

Apple won't simply hand that over. The company has to ask, and Apple's answer takes the form of a certificate.

> 💡 **Explain it like this:** *"We're taking the brain of every Apple device and moving it into Intune. The certificate is Apple's written permission to do that."*

## 30.3 The Apple MDM Push Certificate

🛠️ **Hands-on:** **Devices → iOS/iPadOS → Enrollment → Apple MDM Push Certificate**

The round trip:

1. In Intune, **agree** to let Microsoft send user and device notifications to Apple.
2. **Download the certificate signing request** from Intune.
3. Go to Apple's push certificates portal and **sign in with the company Apple ID**.
4. **Upload** the request you got from Microsoft.
5. Apple issues a certificate. **Download it.**
6. Back in Intune, **upload the Apple certificate**.

Done. Apple devices can now enrol.

## 30.4 The three rules

| Rule | Detail |
|---|---|
| **One certificate per tenant** | There is exactly one. One person sets it up on behalf of the whole organisation. |
| **One Apple ID, forever** | The Apple ID that created it is the **only** Apple ID that can renew it. |
| **Renew every year** | It expires annually. |

⚠️ **Careful — this is the most expensive mistake in the chapter.**

**Use a shared company Apple ID**, something like `appleid@contoso.com` that the IT team owns, stored in the password manager. Never a personal one.

Here's what happens if you get this wrong. Someone sets up the certificate with their own Apple ID. Two years later they've left the company. The certificate expires. **Every enrolled Apple device in the organisation stops being manageable**, and the only fix is to create a new certificate with a new Apple ID and **re-enrol every single Apple device by hand.** On four hundred iPhones, that is a catastrophic month, and it's entirely avoidable.

**So:** shared Apple ID, documented, in the password manager, with a calendar reminder **30 days before expiry** owned by a team rather than a person.

🛠️ **Hands-on — do this one today:** go and look at whether your tenant has a certificate, whose Apple ID made it, and when it expires. Then put the reminder in. It takes four minutes and it is the highest-value four minutes in this chapter.

**Who does this job?** It's Level 2 work. It's rare — once a year — and it's high-impact, which is exactly the combination that gets forgotten.

## 30.5 How a user enrols an iPhone

🛠️ **Hands-on:** this is what you'd put in a user-facing guide.

1. Open the **App Store**.
2. Search **Intune Company Portal** — type the full name.
3. **Get**, then open it.
4. **Sign in** with the work account.
5. Complete the **four steps**:

| Step | What happens |
|---|---|
| **1. Review privacy** | What the company can and cannot see. Tap Continue. |
| **2. Download the management profile** | **Automatic.** Nothing to do. |
| **3. Install the management profile** | ⚠️ **The step everybody misses.** It does **not** happen in the app. **Leave the app open, go to the iPhone's Settings**, tap **Profile Downloaded** near the top, then **Install → passcode → Install → Trust**. Then return to the app. |
| **4. Final check** | **Automatic.** Takes a little longer. |

Then **Done**. The app shows *"Can access company resources."*

**macOS, iPadOS:** same process — Company Portal, sign in, follow the steps.

**Android:** the same idea, but first connect Intune to Google at **Devices → Android → Enrollment**.

🏢 **In the real world:** Step 3 generates more enrollment tickets than the other three combined, because the user is in an app and the next instruction is outside it. Write your user guide with a **screenshot** of the Settings screen and the words *"this step happens in Settings, not in the app"* in bold. It will halve your ticket count.

Devices appear in **Devices → All devices** within about **five minutes**.

## 30.6 The device that's too old

An iPhone 6 from 2014, running iOS 15, **cannot be enrolled**. The Company Portal app won't even appear in its App Store.

Two facts collide:

- **Microsoft** supports the Company Portal only on recent iOS versions
- **Apple** only supplies new iOS to devices it still supports

On an old enough phone there is no overlap, and there is no workaround.

🏢 **In the real world:** This is a real ticket and the answer is **"you need a newer device"**, not two hours of troubleshooting. Recognising an unsupported-hardware problem early — and saying so clearly and kindly — is a genuine professional skill. The user isn't doing anything wrong; the phone is eleven years old.

### ✅ Check your understanding
1. Why do Apple devices need a certificate when Windows devices don't?
2. How many Apple MDM Push Certificates can a tenant have?
3. What happens if the certificate expires?
4. Why must you use a shared company Apple ID?
5. Which enrollment step happens outside the Company Portal app?
6. A user can't find the Company Portal in the App Store. What's your first thought?

**Answers:** (1) Apple is a different company and controls its own devices, so it must grant the authority; Microsoft owns both Windows and Intune. (2) Exactly one. (3) Every enrolled Apple device becomes unmanageable and must be re-enrolled by hand. (4) Only the creating Apple ID can renew it, so a personal ID leaves with the person. (5) Step 3, installing the management profile, which is done in the iPhone's Settings. (6) The device's iOS is probably too old to be supported.

---

# Chapter 31 — Enrolling Windows Devices

### What you will learn
- Automatic enrollment
- The difference between Entra ID join and Intune enrollment — and why it catches people out
- Enrollment restrictions and the device limit
- Windows Hello for Business

## 31.1 Automatic enrollment

🛠️ **Hands-on:** **Devices → Windows → Enrollment → Automatic Enrollment**

Switch it on, and a Windows device that joins Entra ID **enrols itself in Intune**. No certificate, no vendor approval.

**CNAME validation** on the same page tests whether your DNS has an `enterpriseregistration` record pointing at Microsoft. This is a **convenience**, not a requirement: with it, a user types just their email address during setup and Windows finds the right tenant. Without it, enrollment still works — the user types the full server address. Don't treat a failed CNAME check as a blocker.

A user enrols a Windows device at **Settings → Accounts → Access work or school → Connect**, and signs in.

⚠️ **Careful:** **A device cannot belong to two tenants.** If it's already joined somewhere, you must **Disconnect** first. The error message you get otherwise is not obvious, and this is a common snag with second-hand or re-purposed machines.

## 31.2 Entra ID join vs Intune enrollment ⭐

**This is the single most confused pair of concepts in the subject.** It trips up people with years of experience, and it makes a very good interview question.

| | **Entra ID join** | **Intune enrollment** |
|---|---|---|
| Gives you | **Identity** — the device has a company account, SSO works, Conditional Access can see it | **Management** — policy, apps, compliance, remote actions |
| Needs an Intune licence | ❌ No | ✅ **Yes** |
| Where you see it | Entra portal → Devices | Intune → Devices |
| Can you push software? | ❌ **No** | ✅ Yes |

> 💡 **Explain it like this:** *"Entra ID join gives the device a staff badge. Intune enrollment gives you the keys to it. A device can have a badge and still be none of your business."*

**The symptom to recognise:** you open **portal.azure.com → Entra ID → Devices**, see dozens of devices, and the **MDM** column says **None**. Those devices are joined but unmanaged. They do not appear in Intune at all. You cannot install software on them, restart them or wipe them.

**The usual causes, in order of likelihood:**

1. **No Intune licence** assigned to the user
2. **Automatic enrollment** not switched on
3. The device joined **before** the licence or the setting existed, and hasn't re-enrolled

🏢 **In the real world:** *"I've joined the laptop to the company but I still can't manage it"* is a real ticket with a real diagnosis. **Go to the Entra device list and look at the MDM column.** That one column answers the question in five seconds, and most people don't know it exists.

## 31.3 Enrollment restrictions

🛠️ **Hands-on:** **Devices → Enrollment**

**Device limit restrictions** — how many devices one user may enrol.

- **Default: 5**
- Most organisations reduce it to **1 or 2** — one laptop, maybe one phone
- If a user has reached the limit, their next enrollment simply fails

**Device platform restrictions** — per platform, you set:

| Setting | Options |
|---|---|
| **MDM** | Allow / Block |
| **OS version** | Minimum and maximum |
| **Personally-owned devices** | **Allow / Block** |

That last one is a policy decision with real consequences. Blocking personally-owned devices means only company hardware can enrol — clean and simple, and appropriate for office-based staff who are all issued laptops.

⚠️ **Careful:** It's tempting to conclude that BYOD is dead because everyone gets a laptop. **It isn't.** BYOD is still the norm for phones, for contractors, for frontline retail and hospitality staff, and across much of healthcare and education. Blocking personal enrollment doesn't make those people go away — it means they need **app protection** instead (Chapter 38). The usual answer at a mature organisation is: **company laptops get full MDM; personal phones get MAM.**

## 31.4 Windows Hello for Business

🛠️ **Hands-on:** **Devices → Enrollment → Windows Hello for Business**

Passwordless sign-in to Windows, using:

- A **PIN**
- **Biometrics** — fingerprint or face
- A **security key** — a physical USB device
- **Phone sign-in**

Settings include PIN length, whether upper case, lower case and digits are required, expiry, and **require TPM**.

### Why a 6-digit PIN is not weak

This feels wrong the first time you hear it, and it's a genuinely good interview answer.

| | **Password** | **Windows Hello PIN** |
|---|---|---|
| Where it goes | **To a server.** Can be intercepted, phished, replayed, stuffed from a breach list. | **Nowhere.** It never leaves the device. |
| What it unlocks | An account, from anywhere in the world | A **private key held in the TPM** — the hardware security chip — on **that one machine** |
| If stolen | Attacker signs in from another continent | **Useless** without the physical device |
| Brute force | Limited by the service | **Locked out in hardware** by the TPM after a few attempts |

So a 6-digit Hello PIN is, in practice, **stronger than an 8-character password**, because the attack that actually happens — remote credential theft — doesn't work against it. This is the entire basis of Microsoft's passwordless strategy.

⚠️ **Careful:** You'll hear people insist on long complex Hello PINs because "6 digits is risky". Complexity doesn't hurt, but it's solving a small problem while annoying users. **The setting that matters on that page is `require TPM`.** Without a TPM, the key is held in software and the reasoning above collapses.

🎯 **Interview corner:** *"Isn't a 6-digit PIN less secure than a password?"*
**Good answer:** "No, because it's not the same kind of secret. A password travels to a server and can be phished or replayed from anywhere. A Hello PIN never leaves the device — it unlocks a private key in the TPM, so it's worthless to a remote attacker, and the TPM locks out in hardware after a few wrong tries. The important thing is to require TPM; the PIN length matters much less."

### ✅ Check your understanding
1. What does automatic enrollment do?
2. What's the difference between Entra ID join and Intune enrollment?
3. You see MDM = None in the Entra device list. What does it mean and what are the likely causes?
4. How many devices can a user enrol by default?
5. Can a device be joined to two tenants?
6. Why is a Windows Hello PIN stronger than it looks?

**Answers:** (1) A Windows device that joins Entra ID enrols in Intune by itself. (2) Entra ID join gives identity; Intune enrollment gives management and needs a licence. (3) Joined but unmanaged — usually a missing Intune licence, automatic enrollment switched off, or the device joined before either existed. (4) Five. (5) No — disconnect from the first one first. (6) It never leaves the device; it unlocks a TPM-held private key, so it's useless remotely and locked out in hardware.

---

# Chapter 32 — Compliance Policies

### What you will learn
- What compliance means in Intune
- What you can check
- The thing nobody tells you: compliance alone does nothing
- How Conditional Access gives it teeth

## 32.1 What compliance is

> **A compliance policy is the list of conditions a device must meet before the company treats it as trustworthy.**

A device is then reported as **Compliant** or **Not compliant**.

🛠️ **Hands-on:** **Devices → [platform] → Compliance policies → Create policy**

## 32.2 What you can check

| Category | Examples |
|---|---|
| **Device health** | Not **jailbroken** or rooted; Secure Boot on; BitLocker on |
| **Device properties** | **Minimum OS version**, maximum OS version |
| **System security** | Passcode required, minimum length, complexity, encryption, antivirus present and up to date, firewall on |
| **Microsoft Defender** | Machine risk score below a threshold |

Note what is **not** there: **no hardware requirements.** You cannot require 16 GB of RAM. Compliance checks software and configuration.

**A worked example.** Contoso sets **minimum iOS 17.0**:

- A phone on iOS 26.5 → **Compliant**
- A phone on iOS 15.8 → **Not compliant**

⚠️ **Careful:** When you're learning, it's tempting to set the minimum low so your test devices pass. Don't ship that. **Old OS versions have unpatched vulnerabilities, and keeping them away from company data is the entire point of a minimum-OS policy.** Set it to a version Apple or Microsoft still supports, and move it up as they retire versions.

## 32.3 The part that's usually missed ⭐

Here is the question to ask yourself, and it's the one that separates people who have read about Intune from people who have run it:

**A phone is marked "Not compliant". What actually happens to it?**

**On its own: nothing.** A number in a report changes colour. The user notices nothing. Their email keeps working. The non-compliant device carries on exactly as before.

**A compliance policy is a measurement, not a control.** It labels devices. It does not stop them.

## 32.4 Conditional Access: where the teeth are

**Conditional Access** is an **Entra ID** feature, not an Intune one. A policy says, in effect:

> *"To reach Exchange, SharePoint or Teams, the device must be marked as compliant."*

Now the two halves fit together:

| | Without Conditional Access | With Conditional Access |
|---|---|---|
| The old iPhone is marked non-compliant | A report changes | **Conditional Access blocks it** |
| Effect on the user | None | **No company email on that phone** until it's updated |
| Effect on the company | None | The old device genuinely cannot reach company data |

> 💡 **Explain it like this:** *"The compliance policy is the health check. Conditional Access is the bouncer at the door who reads it. A health check with no bouncer is just paperwork."*

🏢 **In the real world:** Plenty of organisations have compliance policies and no Conditional Access, and believe they're protected. They're not — they have a dashboard. When you join somewhere new, this is a genuinely useful thing to check in your first fortnight.

⚠️ **Careful:** Conditional Access is powerful enough to lock everybody out, including you. Always use **report-only mode** first, always **exclude a break-glass admin account**, and always check the **What If** tool before you switch a policy on.

🎯 **Interview corner:** *"What's the difference between a compliance policy and Conditional Access?"*
**Good answer:** "A compliance policy defines what a healthy device looks like and reports whether each device meets it. On its own that's just reporting. Conditional Access is what enforces it — I'd write a policy requiring a compliant device before accessing Exchange or SharePoint. You need both: compliance measures, Conditional Access enforces."

This answer puts you ahead of most candidates, because most know one half.

### ✅ Check your understanding
1. What is a compliance policy?
2. Name four things it can check.
3. Can it require a minimum amount of RAM?
4. A device is non-compliant. What happens by default?
5. What makes compliance actually enforce anything?
6. What two precautions do you take before enabling a Conditional Access policy?

**Answers:** (1) The conditions a device must meet to be treated as trustworthy. (2) Minimum OS version, jailbreak/root status, passcode requirements, encryption (also antivirus, firewall, risk score). (3) No — no hardware requirements. (4) Nothing except a change in reporting. (5) Pairing it with Conditional Access in Entra ID. (6) Report-only mode first, and exclude a break-glass admin account.

---

# Chapter 33 — Configuration Profiles

### What you will learn
- What a configuration profile is
- Templates versus the settings catalogue
- How to verify a policy landed
- Why nothing happens instantly
- Why removing a profile may not undo it

## 33.1 What a configuration profile is

> **Every setting you could change by hand on one device, you can push to every device at once.**

That's the whole idea. Wi-Fi profiles, VPN, printers, passcode rules, blocked features, browser settings, lock screen messages.

🛠️ **Hands-on:** **Devices → [platform] → Configuration → Create → New policy**

## 33.2 The classic demonstration: block the camera

Worth doing, because the result is instant and visible.

1. **Devices → iOS/iPadOS → Configuration → Create → New policy**
2. **Settings catalogue**
3. Search **camera**
4. **Allow camera → Blocked**
5. Assign to **All devices** (in a lab) or a **group** (in real life)
6. **Devices → All devices → select → Bulk device actions → Sync**

A few minutes later, the camera app is **gone from the device**. Not greyed out — gone.

The first time you do this to a phone in your hand, the subject stops being abstract.

## 33.3 Templates versus the settings catalogue

Two ways to find a setting, and knowing which to reach for is a real time-saver.

| | **Templates** | **Settings catalogue** |
|---|---|---|
| What | Microsoft's **pre-built groups** of related settings — "Device restrictions", "Wi-Fi", "VPN", "Email" | A **searchable list of every setting** the OS exposes. Thousands. No structure. |
| Good for | Common tasks, laid out for you with related options together | Knowing what you want and finding it fast |
| Downside | Only covers what Microsoft grouped | Overwhelming; you must know the setting's name |

> **The practical habit:** start in the **settings catalogue and search**. If you don't know what the setting is called, browse a **template** to learn the vocabulary, then go back to the catalogue.

**What you'll find in there**, as a sample of the range:

| Area | Examples |
|---|---|
| **Hardware** | Camera, torch, sleep/wake button, ringer switch |
| **Passcode** | Required, length, complexity, max failed attempts, expiry |
| **Apps** | Prohibited apps, hidden apps, single-app mode |
| **Printing** | AirPrint on or off; restrict to a specific printer IP |
| **Browser** | A whole Microsoft Edge section — downloads, URL blocklist, homepage |
| **Accessibility** | Zoom, VoiceOver, voice control, mono audio |
| **Appearance** | Lock screen message, wallpaper, device name |

## 33.4 Verifying that it worked

**Two ends to check, and you need both.**

| From | Where | Shows |
|---|---|---|
| **The admin side** | The profile → **Device status** | Succeeded / Error / Pending / Not applicable, per device |
| **The device side** | **Company Portal app → Devices → [device] → Check status** | Forces an **immediate** sync |

**Check status in the Company Portal is the fastest way to make a policy land.** Teach it to your users — it turns *"it hasn't worked"* into *"oh, there it is"* without a ticket.

### Reading the four statuses

| Status | Meaning |
|---|---|
| **Succeeded** | Applied |
| **Error** | It tried and failed. **Investigate this one.** |
| **Pending** | The device hasn't checked in yet. **Wait, or sync.** |
| **Not applicable** | The setting doesn't exist on this device or OS version. **Not a failure.** |

⚠️ **Careful:** **Not applicable** is not an error, and beginners burn hours chasing it. An iPad-only setting on an iPhone, or a setting Apple removed in a newer iOS, reports as Not applicable. It usually just means your policy is broader than your fleet.

## 33.5 Why nothing happens instantly

Intune works on a **check-in** schedule. Devices phone home periodically and collect new policy.

| Platform | Normal check-in |
|---|---|
| iOS / iPadOS | about every **8 hours** |
| Android | about every **8 hours** |
| Windows | about every **8 hours** |
| macOS | about every **8 hours** |

**Freshly enrolled devices check in much more often** — roughly every 15 minutes for the first few hours — then settle into the normal rhythm.

**So when a policy "doesn't work", the first question is not "is my policy wrong" — it's "has the device checked in yet".**

🏢 **In the real world:** This is the difference between a confident support person and a flustered one:

> ❌ *"I don't know why it's not working, let me try again."*
> ✅ *"It's applied — the device will pick it up within a few hours. If you want it now, open Company Portal, tap your device, and tap Check status."*

The second answer closes the ticket. And resist the urge to start re-editing a policy two minutes after pushing it: check **Device status** first, and if it says **Pending**, your policy is fine.

## 33.6 Removing a profile may not undo it

⚠️ **Careful — a genuine Intune trap.**

You'd expect deleting a configuration profile to put everything back. **Sometimes it does. Sometimes it doesn't.** Some settings revert when management is removed; others stay at whatever they were last set to. The jargon is that such settings **"tattoo"** the device.

**The reliable way to reverse a policy is to set the value back explicitly:**

1. Change **Allow camera** from **Blocked** back to **Allowed**
2. Push it
3. **Confirm on a device**
4. *Then*, if you like, delete the profile

Deleting and hoping is how you end up with thirty devices whose cameras never came back and no profile left to explain why.

### ✅ Check your understanding
1. What is a configuration profile?
2. When would you use a template rather than the settings catalogue?
3. What are the four statuses on a profile's Device status page?
4. What does "Not applicable" mean?
5. How often does a device normally check in?
6. What's the fastest way for a user to pull a policy now?
7. What's the reliable way to reverse a policy?

**Answers:** (1) A set of settings pushed to devices centrally. (2) When the task is common and you want related settings grouped, or when you don't yet know what a setting is called. (3) Succeeded, Error, Pending, Not applicable. (4) The setting doesn't exist on that device or OS version — not a failure. (5) Roughly every 8 hours, more often just after enrollment. (6) Company Portal → Devices → the device → Check status. (7) Set the value explicitly back and push it; don't just delete the profile.

---

# Chapter 34 — Deploying Applications

### What you will learn
- The four app types
- How to deploy an app
- Required versus available
- The mistake everyone makes once
- How in-house Windows software is packaged

## 34.1 The four app types

🛠️ **Hands-on:** **Apps → [platform] → Add →** choose a type

| Type | What it is | Example |
|---|---|---|
| **Store app** | From the App Store, Google Play or Microsoft Store. Most things you need are here. | Zoom, Firefox, a VPN client |
| **Web link / web app** | A **shortcut to a URL** that appears as an app icon | The staff intranet, the expenses portal |
| **Line-of-business (LOB) app** | **The company's own software**, uploaded as an installer | The in-house booking system |
| **Microsoft 365 apps** | Office as a managed bundle | Word, Excel, Outlook, Teams |

> 💡 **Explain it like this:** *"Store app is from the shop. Web link is a bookmark that pretends to be an app. Line-of-business is something your company wrote. Microsoft 365 apps is Office."*

## 34.2 Deploying a store app

1. **Apps → iOS/iPadOS → Add → iOS store app**
2. **Search** the store and pick the app
3. Review the details
4. **Assignments** — choose who gets it
5. Create

On a managed phone a notification arrives: *"Contoso is about to install and manage GlobalProtect from your App Store. Your account will not be charged."*

The notification can be suppressed, and in a real tenant **the user cannot cancel it** — they don't have the rights. (In a lab where everyone is a Global Administrator, they can, which is misleading.)

⚠️ **Careful:** Deploy sparingly. Every required app installs on every targeted device, consumes storage and bandwidth, and slows the first-run experience. Push what people need, not everything you can think of.

## 34.3 Required versus available

An assignment has an **intent**, and getting it wrong is a common and visible mistake.

| Intent | What happens |
|---|---|
| **Required** | Intune **installs it**, whether the user asked or not |
| **Available for enrolled devices** | It appears in the **Company Portal** for the user to install **if they want** |
| **Uninstall** | Intune **removes it** |

> **The rule of thumb:** **Required** for what everyone must have — antivirus, the VPN client, Office, the line-of-business app. **Available** for what some people need — Visio, a design tool, a specialist utility.

🏢 **In the real world:** Making a 4 GB design suite **Required** for all staff is a memorable mistake. Four hundred devices start a 4 GB download simultaneously, the office internet dies, and your name is attached to it. **Available** would have been correct.

## 34.4 The mistake everyone makes once

⚠️ **Creating an app, policy or profile does nothing until you assign it.**

Every object in Intune has an **Assignments** tab. An unassigned object sits there forever, looking complete, doing nothing. The app list will tell you — it shows **"Not assigned"** — but it's easy to miss when you're clicking through.

**So when something hasn't worked, check two things, in this order:**

1. **Is it assigned?**
2. **Has the device checked in?**

Those two cover the large majority of "Intune isn't working" reports.

## 34.5 Packaging in-house Windows software

Store apps are easy. Your company's own application is the real work.

🛠️ **Hands-on — the Windows LOB process:**

1. Get the installer and everything it needs in one folder
2. Run the **Microsoft Win32 Content Prep Tool** over that folder — it produces a single **`.intunewin`** file
3. Upload the `.intunewin` to **Apps → Windows → Add → Windows app (Win32)**
4. Supply the **install command** — e.g. `setup.exe /quiet /norestart`
5. Supply the **uninstall command**
6. Supply a **detection rule** — a file that exists, a registry key, or an MSI product code
7. Set **requirements** — OS version, architecture, disk space
8. Assign it

**The detection rule is the step beginners skip, and it's the one that matters.** It's how Intune answers *"is this app already installed?"* Without it, Intune has no idea, so it reinstalls endlessly or reports failure on a machine where the app is working fine.

🎯 **Interview corner:** *"How would you deploy our in-house application to 300 laptops?"*
**Good answer:** "I'd package it with the Win32 Content Prep Tool into an .intunewin file, upload it to Intune, and set the silent install and uninstall commands. The important part is the detection rule — a file version or registry key — so Intune can tell whether it's already installed rather than reinstalling on every check-in. I'd set it as Required and target a pilot group first, check the install report, then widen the assignment."

Mentioning the pilot group unprompted is worth as much as the technical detail.

### ✅ Check your understanding
1. Name the four app types.
2. What's the difference between Required and Available?
3. Which would you use for Office? For Visio?
4. Two things to check when a deployment hasn't worked?
5. What does the Win32 Content Prep Tool produce?
6. What is a detection rule and why does it matter?

**Answers:** (1) Store app, web link, line-of-business, Microsoft 365 apps. (2) Required installs automatically; Available offers it in the Company Portal. (3) Office Required; Visio Available. (4) Is it assigned, and has the device checked in. (5) A `.intunewin` package. (6) How Intune detects whether the app is already installed — without it, Intune reinstalls repeatedly or misreports.

---

# Chapter 35 — Targeting: Groups and Assignments

### What you will learn
- Why "All devices" is a lab answer
- Which group type works for devices
- Device groups versus user groups
- Dynamic groups
- Pilot-group discipline

## 35.1 Why All devices is wrong

Assigning everything to **All devices** is fine for a demonstration and wrong for an organisation. Real requirements look like:

- The warehouse tablets have no camera. Nobody else is affected.
- Finance gets the accounting package. Nobody else.
- The design team needs the 4 GB suite. The other 380 people don't.
- Contractors get email, nothing else.

That's **targeting**, and targeting means **groups**.

## 35.2 Which group type ⭐

Part 2 covered four kinds of group. Only one works here.

| Group type | Can it target Intune policy at **devices**? |
|---|---|
| **Security group** | ✅ **Yes — this is the one** |
| Mail-enabled security group | ❌ No |
| Microsoft 365 group | ❌ Not for devices — that's for collaboration and email |
| Distribution list | ❌ No |

> **Remember it as:** *"Microsoft 365 groups are for email and Teams. Security groups are for policy."*

🛠️ **Hands-on:** **Microsoft 365 admin center or Entra ID → Groups → New group → Security**

## 35.3 Device groups versus user groups

Both exist, both are security groups, and **which one you choose changes the behaviour**.

| | **Device group** | **User group** |
|---|---|---|
| Members are | **Devices** | **People** |
| The policy follows | **The hardware**, whoever signs in | **The person**, whichever device they use |
| Use it for | **Device configuration**, compliance, required apps | **App protection**, available apps, user-based settings |

**Two examples that make it concrete:**

- *"Block the camera on warehouse tablets"* → a **device** group. It's about those tablets, regardless of who holds one.
- *"Require a PIN on Outlook for everyone in Finance"* → a **user** group. It's about those people, on whatever phone they're carrying.

⚠️ **Careful:** Picking the wrong one is the usual reason a policy applies to the wrong things. Before you create a group, ask: **is this rule about the machine, or about the person?**

## 35.4 Dynamic groups

Adding devices to a group by hand doesn't scale past a few dozen. **Dynamic groups** maintain their own membership from a rule.

| Rule | Membership |
|---|---|
| `device.deviceOSType -eq "iPad"` | Every iPad, automatically |
| `user.department -eq "Finance"` | Everyone in Finance, as the HR data changes |
| `device.deviceOwnership -eq "Company"` | Every corporate-owned device |
| `device.displayName -startsWith "WH-"` | Every device named `WH-…` |

A new iPad enrols and is in the group minutes later. Someone transfers out of Finance and drops out of the group without anyone doing anything.

🏢 **In the real world:** Dynamic groups driven by **HR attributes** are how joiners, movers and leavers are handled at scale. The device-naming trick — `WH-` for warehouse, `LAB-` for lab machines — is a cheap and very common way to get targeting out of a naming convention.

## 35.5 Pilot groups

⚠️ **Never assign a new policy to everyone first.**

The pattern:

1. Create a **pilot group** — yourself, a few willing colleagues, a test device
2. Assign the policy **to the pilot group**
3. **Verify** it works and nothing broke
4. **Widen** the assignment

Policies also support **exclusions**, so you can say "all staff **except** the executive assistants" or "all devices **except** the pilot group".

🏢 **In the real world:** A badly-worded Edge policy pushed to 400 devices at 9am is a very bad morning, and the fix is slow because every device must check in to receive the correction. The same policy pushed to five devices is a shrug and an edit. **Pilot first** is the single habit that separates people who get trusted with production from people who don't.

🎯 **Interview corner:** *"How would you roll out a new device restriction?"*
**Good answer:** "I'd write it, assign it to a small pilot security group including my own test device, verify it applies and doesn't break anything, then widen it in stages — maybe one department, then everyone — checking the device status report at each stage. For the group I'd use a dynamic security group where I can, so membership maintains itself."

### ✅ Check your understanding
1. Which group type targets Intune policy?
2. Device group or user group: "block the camera on warehouse tablets"?
3. Device group or user group: "require a PIN on Outlook for Finance"?
4. What is a dynamic group?
5. What are the four steps of a pilot rollout?

**Answers:** (1) Security group. (2) Device group. (3) User group. (4) A group whose membership is maintained automatically from a rule, e.g. all iPads or everyone in Finance. (5) Pilot group, assign to it, verify, then widen.

---

# Chapter 36 — The Device Page: Inventory and Remote Actions

### What you will learn
- What Intune can and cannot see on a device
- Personal versus corporate ownership
- The inventory, and why IMEI matters
- Every remote action, and when to use it
- Autopilot reset

## 36.1 The tabs

🛠️ **Hands-on:** **Devices → All devices → [click a device]**

| Tab | Shows |
|---|---|
| **Overview** | Compliance state, last check-in, primary user, ownership, and the action buttons |
| **Properties** | Device name, **ownership**, device category, scope tags |
| **Hardware** | The full inventory |
| **Discovered apps** | Every application Intune can see |
| **Device compliance** | Each compliance policy and whether this device passes |
| **Device configuration** | Each profile and its result — Succeeded / Error / Pending / Not applicable |
| **App configuration** | App-specific settings |
| **Group membership** | Which groups this device is in |

When something isn't working on one device, **Device configuration** and **Device compliance** on that device's page tell you more, faster, than anything else in the portal.

## 36.2 Personal versus corporate

**Properties → Device ownership: Personal / Corporate.**

| | **Personal** | **Corporate** |
|---|---|---|
| **App inventory** | **Only company-deployed apps.** Personal apps are deliberately hidden. | **All installed apps** |
| **Available actions** | Fewer | More, including full wipe |
| **Enrollment restrictions** | Can be blocked entirely | Always allowed |

## 36.3 What Intune cannot see ⭐

This matters more than it first appears, because it's the question every user asks when you tell them to enrol their phone — and the one most support people answer badly.

**Intune cannot see:**

- Call history
- SMS or iMessage content
- Photos
- Browsing history
- Personal email
- Personal contacts and calendars
- The contents of personal apps

**On a personally-owned device it doesn't even list personal apps**, by design.

**Intune can see:** the hardware inventory, company-deployed apps, compliance state, and — on a corporate device — the full app list.

🏢 **In the real world:** *"Can my employer read my texts?"* is the single most common reaction to being asked to enrol a phone, and the honest answer is **no**. Being able to say precisely what the company **can** see is what makes people agree. Microsoft publishes this list; knowing it is a small thing that earns a lot of trust.

⚠️ **Careful:** Don't overstate the company's reach, even casually. "We can see everything you do" is both false and the reason enrollment projects stall.

## 36.4 The inventory

**Hardware** tab. A real example:

| Field | Value |
|---|---|
| Model | iPhone 16 Pro Max |
| Serial number | ✓ |
| **IMEI** | ✓ |
| Total storage | 256 GB |
| Free storage | 165 GB |
| Battery level | 11% |
| Phone number | ✓ |
| Carrier | Vodafone |
| Cellular technology | GSM |
| OS version | 26.5 |
| Last check-in | Today |

**IMEI** is the one to know. It's a phone's permanent hardware serial — it doesn't change when the SIM changes — and it's what you give the carrier and the police when a company phone is stolen, so the handset can be blacklisted from every network.

🏢 **In the real world:** **Intune is also your asset register.** When finance asks "what phones do we own, who has them, and how old are they", the answer is in here and can be exported. That's a question people usually answer with a stale spreadsheet.

## 36.5 The remote actions

| Action | What it does | When |
|---|---|---|
| **Sync** | Force a check-in now | Constantly, while troubleshooting |
| **Restart** | Reboot remotely | Finishing an update, clearing a fault |
| **Rename** | Change the device name | Naming conventions, reassignment |
| **Remote lock** | Lock the screen | Device left unattended or possibly lost |
| **Remove passcode** | Clear the passcode | User locked out |
| **Retire** | Remove company data and management | **A BYOD device when someone leaves** (Chapter 37) |
| **Wipe** | **Factory reset** | **Lost, stolen, or a company device being reassigned** |
| **Delete** | Remove the Intune record | Cleaning up stale records |
| **Fresh start** (Windows) | Reinstall Windows, removing manufacturer pre-installed software | A machine clogged with vendor bloatware |
| **Autopilot reset** (Windows) | Wipe user data **but stay enrolled** | **Reassigning a laptop** |
| **Quick / Full scan** (Windows) | Run Defender remotely | Suspected malware |
| **Collect diagnostics** (Windows) | Pull logs | Investigating a fault |
| **Remote assistance** | See the screen (needs Remote Help) | Guiding a user |
| **Send custom notification** | Push a message to the device | See below |

## 36.6 Autopilot reset ⭐

This answers a weekly real-world question: *"Someone's left. Their laptop goes to the new starter on Monday."*

| | **Wipe** | **Autopilot reset** |
|---|---|---|
| User data | Gone | Gone |
| Apps and settings | Gone | Gone |
| **Still enrolled in Intune?** | ❌ **No** — must be enrolled again from scratch | ✅ **Yes** |
| Next user's experience | Full setup, by hand or via Autopilot registration | **Signs in to a configured, managed machine** |

**Autopilot reset is the device equivalent of the offboarding procedure in Part 2.** Clean for the next person, still owned and managed by you.

## 36.7 Custom notifications

**Devices → Send custom notification.** Title, message, target. It arrives as a push notification on the device.

Not a toy. Real uses:

- *"Your device needs updating by Friday or you'll lose access to email."*
- *"Planned maintenance tonight from 10pm."*
- *"Please restart to finish installing updates."*

🏢 **In the real world:** This reaches a managed phone **without needing the user's personal number or personal email**. For frontline, retail and shift staff who don't sit at a desk and don't read company email, it may be the only channel that works.

### ✅ Check your understanding
1. Name four things Intune cannot see on a personal device.
2. What does changing a device from Personal to Corporate affect?
3. What is IMEI and when do you need it?
4. Difference between Wipe and Autopilot reset?
5. Which action do you use when a laptop is being reassigned?
6. Give two real uses for a custom notification.

**Answers:** (1) Call history, SMS content, photos, browsing history (also personal email, contacts, personal app contents). (2) Mainly what app inventory Intune shows, which actions are available, and enrollment restrictions. (3) A phone's permanent hardware serial; you give it to the carrier and police to blacklist a stolen handset. (4) Both remove user data, but Autopilot reset keeps the device enrolled and managed. (5) Autopilot reset. (6) Update deadlines and planned maintenance notices.

---

# Chapter 37 — Retire, Wipe and Delete

### What you will learn
- What each of the three destructive actions really does
- Which to use when
- The mistake that involves lawyers

This chapter is short, and it's the one to read twice. **These actions cannot be undone.**

## 37.1 The three actions

| Action | What it removes | What survives | Device still managed? |
|---|---|---|---|
| **Retire** | Company data, company apps, company email profile, management | **All personal data — photos, apps, accounts, messages** | No |
| **Wipe** | **Everything. Full factory reset.** | Nothing | No |
| **Delete** | The **device record in Intune** | Whatever is currently on the device | No |

**The distinction that matters: Retire removes company data only. Wipe removes everything.**

> 💡 **Explain it like this:** *"Retire is handing back your office keys and your laptop bag. Wipe is burning the house down. Delete is crossing the device off the list and walking away."*

## 37.2 Which one, when

| Situation | Action | Why |
|---|---|---|
| Employee leaves, **personal phone** | **Retire** | They keep their phone and their life on it. The company gets its data off. |
| Employee leaves, **company phone being reassigned** | **Wipe** | The company owns it and the next person needs it clean |
| Device **lost or stolen** | **Wipe**, immediately | Data matters far more than hardware |
| Device **destroyed** or scrapped | **Delete** | Tidy the record; there's nothing to act on |
| Stale records for devices that no longer exist | **Delete** | Housekeeping |

## 37.3 The mistake

⚠️ **Wiping an employee's personal phone on their last day.**

They resign. Someone opens Intune, finds their phone, and clicks **Wipe** because it sounds thorough.

Their family photos are gone. Their children's baby pictures are gone. Their personal messages, their notes, their non-work life — gone, with no backup if they didn't have one, and **no undo.**

The company had every right to its own data and **no right whatsoever to the rest.** This ends up with HR, and sometimes with lawyers.

**The correct action was Retire.** It removes company data and leaves everything else untouched. It takes exactly as long to click.

> **The rule:** **Personal device → Retire. Company device → Wipe.** Before clicking either, check the **ownership** field on the Properties tab, and if you're not certain, **ask**. Thirty seconds of checking against an irreversible mistake is not a difficult trade.

## 37.4 What the Delete warning actually says

Read it carefully, because people paraphrase it wrongly:

> *"If you delete these devices, you will no longer be able to view or manage them from the Intune portal. The device will no longer be allowed to access your corporate resources. **Company data may be wiped from the device if the device tries to check in later.**"*

Three precise words in there:

- **may** be wiped — not will
- **company** data — not everything
- **if the device tries to check in later** — a device that never checks in again keeps what it has

So **Delete is not a reliable way to get data off a device.** If you need the company data gone, use **Retire** (or **Wipe**, for company hardware) and confirm it reported success.

## 37.5 The safety habits

1. **Check ownership before any destructive action.** Properties → Device ownership.
2. **Read the device name and the primary user out loud** before you confirm. Device lists are long and names are similar.
3. **Never practise on a real device.** Use a VM or a spare.
4. **Don't hand out Global Administrator.** Help Desk Operator can do remote actions without being able to rewrite policy.
5. **Know the ticket.** *"Can you wipe Sarah's phone"* needs a second question: **whose phone is it, and what are we trying to achieve?**

🎯 **Interview corner:** *"An employee resigns and has company email on their personal iPhone. Walk me through what you do."*
**Good answer:** "First I'd check the device ownership in Intune to confirm it's personally owned. Then **Retire**, not Wipe — Retire removes the company data, apps and email profile and leaves their personal data alone. Wiping a personal device would factory-reset it and destroy their photos, which we've no right to do. I'd confirm the retire reported success, and separately complete the account offboarding — remove the licence, remove roles, block sign-in."

Linking it back to Part 2's offboarding is what makes this a complete answer.

### ✅ Check your understanding
1. What does Retire remove, and what does it leave?
2. What does Wipe do?
3. What does Delete actually do?
4. Employee leaves with company email on their own phone — which action?
5. A company iPhone is stolen — which action?
6. What do you check before any destructive action?
7. Is Delete a reliable way to remove company data?

**Answers:** (1) Company data, apps, email profile and management; it leaves all personal data. (2) Full factory reset. (3) Removes the Intune record; company data **may** be wiped **if** the device checks in again. (4) Retire. (5) Wipe, immediately. (6) The device's ownership — personal or corporate — and the primary user. (7) No — it depends on the device checking in again; use Retire or Wipe.

---

# Chapter 38 — App Protection and the BYOD Problem

### What you will learn
- The problem MDM cannot solve
- App protection policies
- MAM without enrollment
- Selective wipe

## 38.1 The problem

A contractor starts at Contoso on a three-month engagement. She needs email and Teams. She has her own iPhone.

**You ask her to enrol it in Intune.** She says no — and she's right to. Enrolling means the company can see her app inventory, push policy to her personal phone, and factory-reset it. For a three-month contract on a phone she paid for, that's not a reasonable ask.

**Neither side is being unreasonable.** The company can't have its data sitting unprotected on an unmanaged phone. She can't hand over control of her own device.

**MDM cannot solve this**, because MDM manages the whole device.

## 38.2 App protection policies

🛠️ **Hands-on:** **Apps → App protection policies → Create policy**

An app protection policy attaches to **the app**, not the device. It protects the **company data inside** Outlook, Teams, Word, Edge and other managed apps.

| Setting | Effect |
|---|---|
| **Require PIN to access** | A separate PIN to open the work app |
| **Require encryption of org data** | Company data encrypted inside the app |
| **Block backup to iCloud / Google** | Company data can't go to a personal cloud backup |
| **Restrict copy and paste** | Can't copy company text into WhatsApp |
| **Block Save As to personal storage** | Can't save a company file to a personal cloud drive |
| **Block third-party keyboards** | Stops keyboards that ship keystrokes to someone else's servers |
| **Block screen capture** (Android) | No screenshots of company data |
| **Require minimum app version** | Old vulnerable app versions can't open company data |
| **Selective wipe** | **Remove only the company data** from the apps |

## 38.3 MAM without enrollment ⭐

**This is the answer to the contractor, and the idea most people haven't met.**

Because the policy attaches to the app rather than the device, **it works on a device that Intune does not manage at all.**

She installs Outlook. She signs in with her work account. Intune applies the app protection policy **to Outlook only**:

- Work email needs a PIN
- Company data can't be copied into personal apps
- Company data can't be backed up to her personal iCloud
- Her phone is **not enrolled**, not managed, not visible as a device, and **cannot be wiped**

On her last day, you perform a **selective wipe**: the company data disappears from Outlook and Teams, and **nothing else on her phone is touched.**

> 💡 **Explain it like this:** *"MDM is owning the house. MAM is renting one room in it, and being able to clear out your own room without touching the rest."*

| | **MDM** | **MAM without enrollment** |
|---|---|---|
| Device enrolled | ✅ Yes | ❌ **No** |
| You can wipe the device | ✅ Yes | ❌ No |
| You can see the device's apps | ✅ Yes | ❌ No |
| You can require a PIN on the work app | ✅ Yes | ✅ **Yes** |
| You can stop company data leaving the app | ✅ Yes | ✅ **Yes** |
| You can remove company data on exit | ✅ Yes | ✅ **Yes (selective wipe)** |
| The user will agree to it | Sometimes | **Almost always** |

🏢 **In the real world:** This is how most organisations handle contractors, consultants, board members, volunteers, and any employee who declines to enrol a personal phone. The standard shape of a mature policy is:

- **Company-owned laptops and phones** → full **MDM**
- **Personally-owned phones** → **MAM** only

🎯 **Interview corner:** *"A contractor wants work email on her own phone but won't let us manage it. What do you do?"*
**Good answer:** "I'd use an app protection policy rather than enrolling the device — MAM without enrollment. The policy applies to Outlook and Teams on her phone: a PIN to open the work app, encryption of company data, no copy-out to personal apps, no backup to personal iCloud. Her phone stays unmanaged and we can't wipe it. At the end of the contract I'd do a selective wipe, which removes the company data from those apps and leaves her personal data alone."

**This single answer will put a candidate ahead of most of the field**, because it shows you understand that device management is partly a negotiation with human beings.

### ✅ Check your understanding
1. Why can't MDM solve the contractor problem?
2. What does an app protection policy protect?
3. What is MAM without enrollment?
4. Name four things an app protection policy can enforce.
5. What is a selective wipe?
6. What's the standard split between company and personal devices?

**Answers:** (1) MDM manages the whole device, and the contractor won't hand over her personal phone. (2) The company data inside managed apps. (3) App protection applied to apps on a device that is not enrolled or managed. (4) A PIN on the work app, encryption of company data, blocking copy-out, blocking personal cloud backup (also third-party keyboards, minimum app version). (5) Removing only the company data from the managed apps, leaving personal data untouched. (6) Company-owned devices get MDM; personal phones get MAM.

---

# Chapter 39 — Windows Autopilot and Zero Touch

### What you will learn
- What Autopilot is, and what it is not
- How devices get registered
- Deployment profiles: user-driven versus self-deploying
- OOBE and the Enrollment Status Page
- Autopilot versus Copilot, and Autopilot versus Update rings

## 39.1 The problem, with real numbers

Contoso buys **600 laptops**.

Setting one up by hand takes **two hours**: unbox, Windows setup, join the company, install Office and the VPN and the line-of-business app, apply settings, hand over.

600 × 2 hours = **1,200 hours**. Thirty weeks of one person doing nothing else.

## 39.2 What Autopilot does

**Windows Autopilot registers a device with your organisation before anyone opens the box.**

🛠️ **Hands-on:**

1. You buy from Dell, HP or Lenovo.
2. The vendor supplies a **CSV** of **hardware hashes and serial numbers** — or registers the devices to your tenant directly.
3. You import it: **Devices → Enrollment → Windows Autopilot → Devices → Import**.
4. The devices are now **known to Contoso while still in their boxes.**
5. A user switches one on, connects to Wi-Fi, signs in with their work account.
6. The device joins Entra ID, enrols in Intune, pulls every policy and app, and names itself.

**Two hours becomes about fifteen minutes, and none of them are yours.**

## 39.3 What Autopilot is not ⚠️

Two confusions, both common, both worth being precise about.

| | What it actually is |
|---|---|
| **Windows Autopilot** | **Device provisioning.** Getting a new Windows device set up and joined automatically. |
| **Microsoft Copilot** | **AI assistance** in Microsoft 365 apps. **Completely unrelated.** The names are similar and people say the wrong one constantly. |

And:

| | What it actually is |
|---|---|
| **Windows Autopilot** | **Day one.** Getting a new device configured. |
| **Windows Update for Business / Update rings** | **Every month after that.** Deploying OS updates, patches and drivers from Intune. |

⚠️ **Careful:** *"Autopilot patches Windows every month"* is a wrong answer and you will hear it said confidently. **Autopilot sets a device up once. Update rings keep it patched forever.** If you only remember one correction from this part of the book, make it this one.

🛠️ **Hands-on — Update rings**, since they're the other half: **Devices → Windows → Update rings for Windows 10 and later**. You create "rings" — a pilot ring that gets updates quickly, a broad ring that gets them a week or two later — so a bad update is caught by twenty people rather than four hundred. Same pilot discipline as Chapter 35.

## 39.4 OOBE

**OOBE — Out-of-Box Experience** — is the setup wizard the first time a Windows device starts:

- Which language?
- Which country or region?
- Add another keyboard?
- Connect to Wi-Fi?
- Accept the licence terms
- Sign in

An Autopilot **deployment profile** decides how much of that the user sees.

## 39.5 The two deployment modes

🛠️ **Hands-on:** **Devices → Enrollment → Windows Autopilot → Deployment profiles → Create profile**

| | **User-driven** (default) | **Self-deploying** |
|---|---|---|
| The user | Picks language, region and keyboard, connects Wi-Fi, **signs in** | **Picks nothing at all** |
| You pre-set | Optionally some of it | **Region, language, keyboard** |
| Device is assigned to | **The user who signs in** | **Nobody** — no primary user |
| Use for | **Normal staff laptops** | **Kiosks, digital signage, shared devices, meeting-room PCs** |
| Requires | — | **TPM 2.0** |

**Device name template** is the other setting worth knowing. Instead of naming 600 laptops by hand, you give a pattern — `CONTOSO-%SERIAL%` — and each device names itself from its own serial number. That naming convention then feeds the dynamic groups in Chapter 35, so a device lands in the right groups before anyone touches it.

## 39.6 The Enrollment Status Page

**Devices → Enrollment → Windows Autopilot → Enrollment Status Page**

The ESP is what the user sees **during** Autopilot: *"Setting up your device… Installing apps… 3 of 7."*

Its real value is a setting: **block the user from reaching the desktop until required apps and policies have finished installing.**

| | **Without ESP** | **With ESP** |
|---|---|---|
| The user sees | A desktop that looks ready | **Honest progress** |
| What's happening | Apps still installing in the background | Same, but visibly |
| What the user does | Opens Word, it's missing, **calls the helpdesk** | **Waits**, because they can see why |

🏢 **In the real world:** The ESP turns a support ticket into a progress bar. On a rollout of any size it pays for the ten minutes it takes to configure.

## 39.7 Zero touch, closing the loop

Once the policies and app assignments exist, **a new device needs nothing from you.**

Enrol a second iPhone after setting up the first and watch: the camera is already blocked, the apps install themselves, the compliance policy already applies. The user typed a username and a password and nothing else.

**The one condition:** the policies have to stay in place. Delete the profile and new devices stop inheriting it.

**And the order, one final time: policies first, devices second.** That's not a preference, it's the mechanism. There is nothing for a device to inherit if you haven't written it yet.

🎯 **Interview corner:** *"We're rolling out 600 new laptops. How would you approach it?"*
**Good answer:** "Autopilot. I'd have the vendor register the devices to our tenant, or import the CSV of hardware hashes. Before any device arrives I'd write the configuration profiles, compliance policies and app assignments, and set up dynamic groups driven by a device naming template. I'd use user-driven mode for staff laptops and self-deploying for any shared or kiosk devices. I'd turn on the Enrollment Status Page so users see progress rather than calling us, and I'd pilot the whole thing on five devices before the shipment lands."

### ✅ Check your understanding
1. What does Autopilot do?
2. How do devices get registered?
3. Autopilot versus Copilot?
4. What actually deploys monthly Windows updates?
5. What is OOBE?
6. User-driven versus self-deploying?
7. What does the Enrollment Status Page do, and why does it reduce tickets?
8. What's the one condition for zero touch to keep working?

**Answers:** (1) Registers new Windows devices to the organisation so they configure themselves on first start-up. (2) The vendor registers them, or you import a CSV of hardware hashes and serial numbers. (3) Autopilot is device provisioning; Copilot is AI — unrelated. (4) Windows Update for Business / Update rings. (5) The Out-of-Box Experience — the first-run setup wizard. (6) User-driven: the user picks region, language and Wi-Fi and signs in. Self-deploying: the user picks nothing, used for kiosks and shared devices. (7) Shows setup progress and can block the desktop until required apps install, so users wait instead of reporting missing software. (8) The policies must stay in place.

---

# Chapter 40 — Troubleshooting Intune

### What you will learn
- A diagnostic order that works
- The four statuses and what each one means for you
- The portal page nobody uses
- The five faults you'll actually see

## 40.1 The order

When something in Intune "isn't working", go through this in order. It resolves the large majority of cases, and it stops you editing a policy that was never wrong.

| # | Check | Where |
|---|---|---|
| **1** | **Is it assigned?** | The policy or app → **Assignments** |
| **2** | **Has the device checked in?** | The device → **Overview → Last check-in** |
| **3** | **Is the user licensed?** | M365 admin center → Users → [user] → **Licenses and apps** |
| **4** | **Is the device actually managed?** | Entra → Devices → the **MDM** column |
| **5** | **What does the status say?** | The policy → **Device status** |
| **6** | **Is the setting even applicable?** | The device → **Device configuration** |
| **7** | **Do I have the rights?** | M365 admin center → Users → [you] → **Roles** |

**Steps 1 and 2 alone account for most reports.** Do them before anything else, every time.

## 40.2 Reading the statuses

| Status | Means | Do |
|---|---|---|
| **Succeeded** | Applied | Nothing |
| **Pending** | Device hasn't checked in | **Wait, or Sync.** The policy is fine. |
| **Not applicable** | The setting doesn't exist on this device or OS | **Nothing.** Not a failure. |
| **Error** | It tried and failed | **Investigate.** Open the device, read the detail. |

⚠️ **Careful:** Two traps here, and both waste real hours. **Pending is not failure** — re-editing a policy two minutes after pushing it, because it still says Pending, is how you end up with four broken versions of a working policy. **Not applicable is not failure** either — it usually means the policy is broader than the fleet.

## 40.3 The page nobody uses

🛠️ **Hands-on:** **Troubleshooting + support → Troubleshoot**, then pick a user.

It shows, on one page, for that person:

- Their **licences** — including whether they have an Intune one
- Their **devices**, and the management state of each
- **Group memberships**
- **Compliance** status
- **Assigned policies** and apps, and the result of each
- **Enrollment failures**, with the reason

This is the fastest route from *"it's not working for Sarah"* to an actual answer, and most people never open it. Start here when a problem is specific to one person.

## 40.4 The five faults you'll actually see

| Symptom | Usual cause | Fix |
|---|---|---|
| **"The policy isn't applying"** | Not assigned, or the device hasn't checked in | Check Assignments; **Sync** or **Check status** |
| **"I joined the laptop but can't manage it"** | **No Intune licence**, or automatic enrollment off | Entra → Devices → **MDM** column confirms it. Assign the licence, turn on automatic enrollment, re-enrol. |
| **"Enrollment fails"** | Device limit reached, platform blocked, device already in another tenant, or OS too old | Check **Device limit restrictions** and **Platform restrictions**; **Disconnect** from the old tenant |
| **"Not authorised"** | Wrong admin role | Grant **Intune Administrator** — not Global Administrator |
| **"The app installed but shows as failed"** | **Missing or wrong detection rule** | Fix the detection rule — file version, registry key or MSI product code |

## 40.5 What to say to the user

Half of troubleshooting is the sentence you say out loud.

| Instead of | Say |
|---|---|
| *"I don't know why it's not working."* | *"It's applied — the device picks it up within a few hours. To get it now: Company Portal, tap your device, tap Check status."* |
| *"It should be working."* | *"The report says pending, which means your device hasn't checked in yet. Let me push a sync."* |
| *"We can see everything on your phone."* | *"We can see the hardware details and company apps. We can't see your photos, messages, browsing or personal apps."* |
| *"Just wipe it."* | *"Is that a personal or company phone? If it's personal I'll retire it, which removes the company data and leaves everything of yours alone."* |

🏢 **In the real world:** The right-hand column is what gets someone promoted from Level 1 to Level 2. The technical knowledge is the same; the difference is that the user hangs up informed instead of worried.

### ✅ Check your understanding
1. What are the first two things you check?
2. What does Pending mean, and what do you do?
3. Where do you confirm a device is joined but unmanaged?
4. Which portal page gives you everything about one user at once?
5. An app installed but reports failed. Likely cause?
6. A user asks whether you can read their texts. What do you say?

**Answers:** (1) Is it assigned, and has the device checked in. (2) The device hasn't checked in — wait or sync; the policy is fine. (3) Entra ID → Devices → the MDM column. (4) Troubleshooting + support → Troubleshoot. (5) A missing or incorrect detection rule. (6) No — Intune can see hardware details and company apps, not photos, messages, browsing or personal apps.

---

# Chapter 41 — Career: Scenarios and Interview Practice

## 41.1 What you can now do

After Part 3, you can honestly claim:

- Explain endpoint management, Intune, MDM and MAM
- Compare SCCM and Intune, and explain co-management
- Set up the Apple MDM Push Certificate and explain its three rules
- Enrol iOS, Android, macOS and Windows devices
- Diagnose a device that's Entra-joined but unmanaged
- Write compliance policies and explain why Conditional Access is what enforces them
- Write configuration profiles using templates or the settings catalogue
- Deploy store apps, web links and in-house applications
- Target policy correctly with device and user security groups, including dynamic ones
- Read a device's inventory and perform every remote action
- Choose correctly between retire, wipe and delete
- Solve the BYOD problem with app protection and MAM without enrollment
- Plan a 600-device rollout with Autopilot, deployment profiles and the ESP
- Troubleshoot in a sensible order, and explain it to a user in plain language

That is a genuine junior-to-mid endpoint skill set.

## 41.2 Scenario practice

Work through these out loud before an interview. The answer is in the chapter named.

| # | Scenario | Chapter |
|---|---|---|
| 1 | *"We've bought 600 laptops arriving next month."* | 39 |
| 2 | *"A contractor wants work email on her own iPhone but won't let us manage it."* | 38 |
| 3 | *"Someone left their work phone in a taxi."* | 37 |
| 4 | *"An employee resigned. Work email is on their personal phone."* | 37 |
| 5 | *"A laptop needs to go to a new starter on Monday."* | 36 |
| 6 | *"Finance need an app nobody else should have."* | 35 |
| 7 | *"I've joined the laptop to the company but can't install software on it."* | 31 |
| 8 | *"Our compliance dashboard is all green. Are we protected?"* | 32 |
| 9 | *"The camera must be disabled on the warehouse tablets."* | 33, 35 |
| 10 | *"I pushed a policy twenty minutes ago and nothing's happened."* | 33, 40 |
| 11 | *"The Apple certificate expires next week and the person who set it up has left."* | 30 |
| 12 | *"A user says we're spying on their phone."* | 36 |
| 13 | *"How do we deploy our own in-house application?"* | 34 |
| 14 | *"We need shared iPads in reception that nobody signs into."* | 39 |
| 15 | *"Last month's Windows update broke a line-of-business app."* | 39 |

## 41.3 Interview quick answers

**"What is Intune?"**
A cloud-based endpoint management service for managing devices and the applications on them remotely — Windows, macOS, iOS, iPadOS and Android, with limited Linux.

**"MDM or MAM?"**
MDM manages the device and needs it enrolled. MAM manages the app and the company data inside it, and works even on devices you don't manage.

**"SCCM or Intune?"**
Same job. SCCM's management server is on-premises; Intune's is in the cloud, so it reaches devices anywhere. Running both is called co-management, and plenty of organisations are mid-migration.

**"Do you know SCCM?"**
Theoretically, but my practical experience is Intune. They do the same job, so I'd pick it up quickly.

**"Autopilot or Copilot?"**
Autopilot provisions new Windows devices. Copilot is AI. Unrelated — and neither does monthly patching, that's Update rings.

**"Retire or wipe?"**
Retire removes company data and leaves personal data. Wipe is a factory reset. Personal device, retire. Company device, wipe.

**"Why isn't my policy applying?"**
Check it's assigned, then check the device has checked in. Devices check in roughly every 8 hours; force it with Sync, or Check status in the Company Portal.

**"Compliance policy or Conditional Access?"**
Compliance defines and reports what a healthy device looks like. Conditional Access enforces it by blocking non-compliant devices. You need both.

**"Which admin role do you want?"**
Intune Administrator for policy work, Help Desk Operator for the Level 1 team. Global Administrator should be two or three people, not a device team.

**"What are the limits of remote management?"**
Hardware, and anything while the device is off or offline. A failed drive or a machine that won't boot still needs someone there.

## 41.4 What to build before the interview

A trial tenant and a Windows VM cost nothing, and being able to say *"I've done this"* beats *"I've read about this"* every time.

1. Start a **Microsoft 365 Business Premium trial**
2. Enrol a **Windows VM** and, if you can, a **spare phone**
3. Write a **compliance policy** and watch a device fail it, then pass it
4. Write a **configuration profile**, push it, verify it, then **reverse it properly**
5. Deploy a **store app** as Required and another as Available, and compare what the user sees
6. Create a **dynamic device group** and target something at it
7. Create an **app protection policy** and test it on an **unenrolled** phone
8. Create an **Autopilot deployment profile** in both modes
9. **Retire** one device and **wipe** another, and note the difference
10. Break something on purpose, then fix it with the Chapter 40 order

Then you can answer *"tell me about your Intune experience"* with specifics.

---

# Appendix G — Quick Reference: Where Every Intune Setting Lives

**intune.microsoft.com**

### Devices

| Task | Path |
|---|---|
| Every managed device | Devices → All devices |
| Count by platform | Devices → Overview |
| **Apple MDM Push Certificate** | Devices → iOS/iPadOS → Enrollment → Apple MDM Push Certificate |
| Android (Google connection) | Devices → Android → Enrollment |
| **Windows automatic enrollment** | Devices → Windows → Enrollment → Automatic Enrollment |
| **CNAME validation** | Devices → Windows → Enrollment |
| **Device limit** (default 5) | Devices → Enrollment → Device limit restrictions |
| **Allow/block personal devices** | Devices → Enrollment → Device platform restrictions |
| **Windows Hello for Business** | Devices → Enrollment → Windows Hello for Business |
| **Co-management** (with SCCM) | Devices → Windows → Enrollment → Co-management settings |
| **Compliance policy** | Devices → [platform] → Compliance policies → Create policy |
| **Configuration profile** | Devices → [platform] → Configuration → Create → New policy |
| **Update rings** (monthly patching) | Devices → Windows → Update rings for Windows 10 and later |
| **Autopilot — import devices** | Devices → Enrollment → Windows Autopilot → Devices → Import |
| **Autopilot — deployment profile** | Devices → Enrollment → Windows Autopilot → Deployment profiles |
| **Enrollment Status Page** | Devices → Enrollment → Windows Autopilot → Enrollment Status Page |
| **Bulk actions** | Devices → All devices → select → Bulk device actions |
| **Custom notification** | Devices → Send custom notification |

### One device

| Task | Path |
|---|---|
| Personal vs **corporate** | [device] → Properties → Device ownership |
| **IMEI**, storage, battery, carrier | [device] → Hardware |
| Every installed app | [device] → Discovered apps |
| Compliance results | [device] → Device compliance |
| Profile results | [device] → Device configuration |
| Groups it belongs to | [device] → Group membership |
| **Sync / Restart / Rename / Remote lock / Remove passcode** | [device] → Overview, action buttons |
| **Retire / Wipe / Delete** | [device] → Overview, action buttons |
| **Autopilot reset / Fresh start / Scan / Collect diagnostics** (Windows) | [device] → Overview |

### Apps

| Task | Path |
|---|---|
| **Deploy an app** | Apps → [platform] → Add → choose app type |
| **App protection policy** (MAM) | Apps → App protection policies → Create policy |
| App configuration | Apps → App configuration policies |
| Install reports | Apps → Monitor → App install status |

### Troubleshooting

| Task | Path |
|---|---|
| **Everything about one user** | Troubleshooting + support → Troubleshoot → pick a user |
| Enrollment failures | Troubleshooting + support → Troubleshoot |
| Reports | Reports → Device compliance / Device management |

### Outside Intune

| Task | Path |
|---|---|
| **Create a security group** | M365 admin center or Entra → Groups → New group → **Security** |
| **Dynamic group rule** | The group → Dynamic membership rules |
| **Joined but unmanaged?** | portal.azure.com → Entra ID → Devices → the **MDM** column |
| **Conditional Access** | Entra ID → Protection → Conditional Access |
| A user's licence | M365 admin center → Users → [user] → Licenses and apps |
| A user's role | M365 admin center → Users → [user] → Account → Roles |
| A user's country | M365 admin center → Users → [user] → Edit properties |

### On the device

| Task | Where |
|---|---|
| **Enrol** iOS / Android / macOS | **Intune Company Portal** app → sign in → complete the steps |
| **Install the iOS management profile** | iPhone **Settings → Profile Downloaded → Install → Trust** |
| **Force a sync** | Company Portal → Devices → [device] → **Check status** |
| **Unenrol** | Company Portal → Devices → [device] → Sign out / Remove |
| Enrol **Windows** | Settings → Accounts → Access work or school → **Connect** |
| Leave a tenant (Windows) | Settings → Accounts → Access work or school → **Disconnect** |

---

# Appendix H — Glossary for Part 3

| Term | Meaning |
|---|---|
| **Apple MDM Push Certificate** | Apple's permission for Intune to manage Apple devices. **One per tenant, one Apple ID, renewed yearly.** |
| **App protection policy** | A **MAM** policy protecting company data **inside an app** — PIN, encryption, no copy-out, selective wipe |
| **Assignment** | Who or what a policy, profile or app applies to. **Nothing happens until it's assigned.** |
| **Autopilot (Windows Autopilot)** | Provisioning new Windows devices automatically from their hardware hashes. **Not** OS patching. |
| **Autopilot reset** | Wipe a Windows device's user data **but keep it enrolled and managed** |
| **Bundle ID** | An iOS app's permanent unique identifier, e.g. `com.facebook.Facebook` |
| **BYOD** | Bring Your Own Device |
| **Check-in** | When a device contacts Intune for new policy. Roughly every 8 hours; faster just after enrollment. |
| **Co-management** | Running Intune and Configuration Manager together, moving workloads across gradually |
| **Compliance policy** | The conditions a device must meet to be trusted. **Reports only — Conditional Access enforces.** |
| **Conditional Access** | The **Entra ID** feature that blocks access from non-compliant or untrusted devices |
| **Configuration profile** | Settings pushed to devices — block the camera, set passcode rules, configure Wi-Fi |
| **Copilot** | Microsoft's **AI** assistant. Unrelated to device management. |
| **DDM (Declarative Device Management)** | Apple's newer model: the server declares a desired state and the device achieves it |
| **Delete** (device action) | Remove the Intune **record**. Company data **may** be wiped **if** the device checks in again. |
| **Detection rule** | How Intune decides whether an app is already installed. Required for Win32 apps. |
| **Device limit restriction** | How many devices one user may enrol. **Default 5.** |
| **Discovered apps** | The applications Intune can see on a device |
| **Dynamic group** | A group whose membership maintains itself from a rule |
| **Endpoint** | Any device connecting to the company — laptop, desktop, phone, tablet |
| **Enrollment** | Bringing a device under Intune management |
| **Enrollment Status Page (ESP)** | The Autopilot progress screen; can block the desktop until setup finishes |
| **Entra ID join** | Giving a device a company **identity**. **Not** the same as Intune enrollment. |
| **Fresh start** | Reinstall Windows, removing manufacturer pre-installed software |
| **Hardware hash** | The device fingerprint used to register it with Autopilot |
| **IMEI** | A phone's permanent hardware serial. Used to blacklist a stolen handset. |
| **Intune Administrator** | The right role for device work. Full Intune rights, nothing outside Intune. |
| **Intune Company Portal** | The app users install to enrol, see company apps, and force a sync |
| **`.intunewin`** | The package format for a Windows Win32 app, produced by the Content Prep Tool |
| **Line-of-business (LOB) app** | A company's own in-house application |
| **MAM** | **Mobile Application Management** — managing the app and the company data in it |
| **MAM without enrollment** | App protection on a device that is **not** enrolled or managed. The BYOD answer. |
| **MDM** | **Mobile Device Management** — managing the whole device |
| **MDM = None** | In the Entra device list: the device has an identity but **is not managed** |
| **Microsoft Endpoint Manager** | Old umbrella name for Intune plus Configuration Manager. Still in the UI. |
| **Not applicable** | The setting doesn't exist on that device or OS. **Not a failure.** |
| **OOBE** | **Out-of-Box Experience** — the first-run setup wizard on a new Windows device |
| **Pending** | The device hasn't checked in yet. **Not a failure.** |
| **Personal vs Corporate** | A device's recorded ownership. Affects inventory visibility and available actions. |
| **Pilot group** | A small group you assign a new policy to first, before widening it |
| **Required vs Available** | Required installs automatically; Available offers the app in the Company Portal |
| **Retire** | Remove **company** data and management, **leaving personal data intact** |
| **SCCM / Configuration Manager** | The **on-premises** predecessor to Intune |
| **Selective wipe** | Remove **only** company data from an app |
| **Self-deploying mode** | An Autopilot profile where the user chooses nothing. Kiosks and shared devices. Needs TPM 2.0. |
| **Settings catalogue** | A searchable list of every available setting, unstructured |
| **Sync** | Force a device to check in now |
| **Tattoo** | A setting that persists after its profile is removed |
| **Template** (configuration) | A pre-built group of related settings |
| **TPM** | The hardware security chip holding the key behind a Windows Hello PIN |
| **Update rings / Windows Update for Business** | What **actually** deploys monthly OS updates and patches from Intune |
| **User-driven mode** | The default Autopilot profile. The user picks region, language, Wi-Fi, then signs in. |
| **Win32 Content Prep Tool** | Microsoft's utility that packages a Windows installer into a `.intunewin` file |
| **Wipe** | **Full factory reset.** Lost, stolen or reassigned company devices. |
| **Windows Hello for Business** | Passwordless Windows sign-in with PIN, fingerprint, face or security key, backed by TPM |
| **ZTP (Zero Touch Provisioning)** | Writing policies first, so a new device configures itself when the user signs in |

---

# Appendix I — Lab Workbook for Part 3

Use a **practice tenant**, a **virtual machine** and, if possible, a **spare phone**. **Do not practise on your own phone.** Tick each one when you can do it **without looking at the book**.

| # | Lab | Chapter | ✔ |
|---|---|---|---|
| 1 | Open Intune and name which tab is **MDM** and which is **MAM**. | 29 | ☐ |
| 2 | Check your own **admin role**. Say which role you *should* be using for device work. | 29 | ☐ |
| 3 | Find whether your tenant has an **Apple MDM Push Certificate**, whose Apple ID made it, and when it expires. Set a reminder 30 days before. | 30 | ☐ |
| 4 | **Enrol an iOS device** with the Company Portal. Write down the four steps and mark which happens in Settings. | 30 | ☐ |
| 5 | Use **Check status** in the Company Portal. | 30, 33 | ☐ |
| 6 | Turn on **Windows automatic enrollment**. | 31 | ☐ |
| 7 | **Enrol a Windows VM**. Time it. Then calculate 600 of them. | 31, 39 | ☐ |
| 8 | Open **Entra → Devices** and read the **MDM** column. Find a device that is joined but unmanaged, and explain why. | 31 | ☐ |
| 9 | Set the **device enrollment limit** to 2. Try to enrol a third device. | 31 | ☐ |
| 10 | **Block personally-owned** Windows devices in platform restrictions. | 31 | ☐ |
| 11 | Configure **Windows Hello** with a PIN policy and **require TPM**. Explain why TPM is the important setting. | 31 | ☐ |
| 12 | Write a **compliance policy** with a minimum OS **above** your test device. Confirm **Not compliant**. Then lower it and confirm it passes. | 32 | ☐ |
| 13 | Explain out loud what **actually happens** to a non-compliant device with no Conditional Access. | 32 | ☐ |
| 14 | Find a **Conditional Access** policy requiring a compliant device. (Read it. Don't enable it without report-only mode.) | 32 | ☐ |
| 15 | Write a profile to **block the camera**. Push it. Confirm the app disappears. | 33 | ☐ |
| 16 | **Reverse it properly** — set Allow camera back to Allowed, push, confirm. Don't just delete the profile. | 33 | ☐ |
| 17 | Find the **same setting twice**: via a **template** and via the **settings catalogue**. | 33 | ☐ |
| 18 | Set a **lock screen message** and confirm it appears. | 33 | ☐ |
| 19 | Read a profile's **Device status** page and explain all four statuses. | 33, 40 | ☐ |
| 20 | Find an app's **bundle ID** and write a policy to **hide** it. | 33 | ☐ |
| 21 | Deploy a free **store app** as **Required**. Watch the notification arrive. | 34 | ☐ |
| 22 | Deploy a second app as **Available**. Find it in the Company Portal and install it as the user. | 34 | ☐ |
| 23 | Create an app and **don't assign it**. Read what the app list says. Then assign it. | 34 | ☐ |
| 24 | Create a **security group** with **device** members. Target an app at it. Confirm other devices don't get it. | 35 | ☐ |
| 25 | Create a **dynamic device group** — e.g. all iOS devices. Watch a device join it. | 35 | ☐ |
| 26 | Create a **pilot group**, assign a policy to it only, verify, then widen the assignment. | 35 | ☐ |
| 27 | Read your test device's **Hardware** tab. Find the **IMEI**, free storage and battery level. | 36 | ☐ |
| 28 | Switch the device from **Personal** to **Corporate**. Compare **Discovered apps** before and after. | 36 | ☐ |
| 29 | List four things Intune **cannot** see. Practise saying it to a worried user. | 36 | ☐ |
| 30 | **Rename** the device remotely, **restart** it, then **sync** it. | 36 | ☐ |
| 31 | Send a **custom notification** and confirm it arrives. | 36 | ☐ |
| 32 | **Retire** one device and **wipe** another. Write down exactly what happened to each. | 37 | ☐ |
| 33 | Read the **Delete** warning text and explain the words "may", "company" and "if". | 37 | ☐ |
| 34 | Write an **app protection policy** requiring a PIN on Outlook. | 38 | ☐ |
| 35 | Test it on a device that is **not enrolled**. Explain why it works. | 38 | ☐ |
| 36 | Perform a **selective wipe** and confirm personal data is untouched. | 38 | ☐ |
| 37 | Create an **Autopilot deployment profile** in **user-driven** mode. | 39 | ☐ |
| 38 | Create a second in **self-deploying** mode. Write down the difference a user sees. | 39 | ☐ |
| 39 | Set a **device name template** and confirm a device names itself. | 39 | ☐ |
| 40 | Configure the **Enrollment Status Page** to block the desktop until apps install. | 39 | ☐ |
| 41 | Create an **Update ring** with a pilot group and a broad group. Explain how it differs from Autopilot. | 39 | ☐ |
| 42 | **Enrol a second device** and confirm it inherits every policy and app **without you doing anything**. | 39 | ☐ |
| 43 | Open **Troubleshooting + support → Troubleshoot** for one user and read everything it tells you. | 40 | ☐ |
| 44 | **Break something on purpose** — unassign a policy, or remove a licence — then diagnose it with the Chapter 40 order. | 40 | ☐ |
| 45 | Write a Windows profile to **block downloads in Edge**. Test the download **before**, sync, test **after**. | 33, 40 | ☐ |
| 46 | Add a site to the Edge **URL blocklist**. Confirm it's blocked in Edge, then open it in another browser and explain why that works. | 33 | ☐ |

---

*End of Part 3. Next: SharePoint and Teams.*
