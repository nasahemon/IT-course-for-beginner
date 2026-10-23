# Microsoft 365 — Class 3: Microsoft Intune — Managing Devices and Applications (MDM & MAM)

Teaching notes for class 3 of the Microsoft 365 course. The whole video (~2 h 13 min) is covered in order.

---

## How to use this document

- Each section follows the video **in order**, with **timestamps** so you can check the recording.
- The auto-generated transcript was rough. Corrections are applied silently in the text. The main ones:

| Transcript says | Actually means |
|---|---|
| "in devices", "in point", "in point manager" | **endpoint**, Microsoft **Endpoint** Manager |
| "JTA", "zero toss", "zero torch", "0 transfer", "ZT0" | **ZTP — Zero Touch Provisioning** |
| "inter ID" | **Entra ID** |
| "Microsoft 35" | **Microsoft 365** |
| "restarts" (as in "wherever you restarts working from") | **your staff** |
| "any decks", "an index", "FIFA official app" | **AnyDesk** |
| "Rebex", "Cisco Rebex" | **Cisco Webex** |
| "Jam Pro", "jam like a iris" | **Jamf Pro** |
| "Global Protect" | **GlobalProtect** (Palo Alto VPN client) |
| "OOB" | **OOBE — Out-of-Box Experience** |
| "status space" | **Enrollment Status Page** |
| "IMI number" | **IMEI** |
| "ape bundle", "ape name" | **app bundle ID**, **app name** |
| "male enabled security group" | **mail-enabled security group** |
| "portal.ago.com", "theportal.ago.com" | **portal.azure.com** |
| "work or SQL account" | **work or school account** |
| "GPU updates last force" | **`gpupdate /force`** |
| "T9 Management" | **Tenant administration** |
| "job for IT", "Zofer ID", "job variety company" | the class tenant, **jobforit.online** |

- Class chatter is left out: Zoom problems, roll calls, student names where they don't matter, the Apple ID that was read out loud.
- 📘 **Note** boxes are short clarifications I added. They weren't said in the video.
- ⚠️ **Correction** boxes are places where the instructor said something loosely or wrongly. **Read these out** — two of them (Autopilot vs Copilot, and retire vs wipe vs delete) are common interview questions and the video would teach them wrong.
- ⭐ marks a topic the instructor flagged as interview material or spent real time on.

### Class overview

| Time | Topic |
|---|---|
| 0:02 – 13:17 | **What Intune is**: endpoint management, SCCM vs Intune, MDM vs MAM, zero-touch provisioning, licensing |
| 13:17 – 15:00 | The **Intune admin center** and its tabs |
| 15:00 – 17:30 | The plan for the class, and why practising on personal phones is risky |
| 17:30 – 27:10 | **Apple MDM Push Certificate** ⭐ — the trust between Apple and Microsoft |
| 27:10 – 40:20 | **Enrolling an iPhone** with the Intune Company Portal app |
| 40:20 – 45:10 | **Compliance policies** ⭐ — minimum OS version |
| 45:10 – 50:00 | The **individual device page**: personal vs corporate, remote lock, inventory |
| 50:00 – 54:00 | **Configuration profiles** ⭐ — blocking the camera on every iPhone |
| 54:00 – 1:06:30 | More configuration: **templates vs settings catalogue** |
| 1:06:33 – 1:07:15 | Student question: **Jamf Pro vs Intune** |
| 1:07:15 – 1:15:04 | **Hiding an app** (Facebook) and why sync takes time |
| 1:15:04 – 1:20:46 | **Deploying applications** ⭐ |
| 1:20:46 – 1:23:14 | **Targeting with security groups** ⭐ |
| 1:23:14 – 1:25:05 | The **app types** in Intune |
| 1:25:05 – 1:31:50 | **Device actions**: delete, retire, wipe, restart, custom notification ⭐ |
| 1:31:50 – 1:38:50 | Per-device review, and an **iOS update policy** |
| 1:38:50 – 1:40:40 | **App protection policies** (MAM) ⭐ |
| 1:40:40 – 1:42:40 | **Zero touch proved**: new devices inherit everything |
| 1:42:40 – 1:44:50 | Removing the test devices |
| 1:44:50 – 1:51:00 | **Windows enrollment settings**, device limit, Windows Hello |
| 1:51:00 – 1:59:00 | **Windows Autopilot** ⭐ — 600 laptops |
| 1:59:00 – 2:02:00 | **Deployment profiles** and OOBE: user-driven vs self-deploying |
| 2:02:00 – 2:05:35 | **Windows device actions**: rename, restart, sync, reset |
| 2:05:35 – 2:10:25 | **Windows configuration**: blocking downloads in Edge |
| 2:10:25 – 2:13:03 | **Blocking websites** in Edge, and what's next |

### The task list from this class

The instructor worked through these in order. They make a complete practice list.

| # | Task |
|---|---|
| 1 | Open the **Intune admin center** and find the Devices and Apps tabs |
| 2 | Create the **Apple MDM Push Certificate** (one per tenant, renewed yearly) |
| 3 | **Enrol an iOS device** using the Intune Company Portal app |
| 4 | Write a **compliance policy** (minimum OS version) |
| 5 | Read a device's **inventory**: IMEI, storage, battery, carrier |
| 6 | Change a device from **personal to corporate** |
| 7 | **Remote lock** a device and **remove its passcode** |
| 8 | Write a **configuration profile** to block the camera |
| 9 | **Push / sync** a policy and verify it with **Check status** in the Company Portal |
| 10 | Use the **device restrictions template** (passcode rules, prohibited apps) |
| 11 | Use the **settings catalogue** (AirPrint, lock screen message, accessibility) |
| 12 | **Hide an app** using its bundle ID |
| 13 | **Deploy a store app** to all devices (GlobalProtect, Firefox) |
| 14 | Create a **security group with device members** and target a policy at it only |
| 15 | Send a **custom notification** to devices |
| 16 | **Rename**, **sync**, **restart**, **retire**, **wipe** and **delete** a device |
| 17 | Write an **iOS update policy** with a target version and time |
| 18 | Create an **app protection policy** (MAM) |
| 19 | Turn on **Windows automatic enrollment** and set the **device limit** |
| 20 | Set **enrollment restrictions** (allow or block personally-owned devices) |
| 21 | Configure **Windows Hello** (PIN rules, biometrics, security key) |
| 22 | **Enrol a Windows device** by joining it to Entra ID |
| 23 | Import devices into **Windows Autopilot** from a CSV of serial numbers |
| 24 | Create an **Autopilot deployment profile** (user-driven vs self-deploying) |
| 25 | Write a **Windows configuration policy** to block downloads in Edge |
| 26 | **Block websites** in Edge by URL |

---

## Part 1 — What Microsoft Intune is (0:02 – 13:17)

### The one-sentence definition

> **Microsoft Intune is a cloud-based endpoint management service that lets you manage devices and applications remotely, from anywhere.**

The instructor gave a longer version, which is close to Microsoft's own wording and worth memorising:

> *"Microsoft Intune is a cloud-based endpoint management solution that manages user access and simplifies application and device management across your entire organisation. It acts like a control centre for securing corporate data on both company-owned and personally-owned devices."*

### The two halves: MDM and MAM ⭐

The instructor stressed this twice. **"Two things are very important: application and devices."**

| Acronym | Stands for | What it manages |
|---|---|---|
| **MDM** | **Mobile Device Management** | The **device** — the whole machine. Enrol it, lock it, wipe it, restart it, update its OS, read its hardware details. |
| **MAM** | **Mobile Application Management** | The **app and the data inside it** — install it, remove it, block copy-and-paste out of it, require a PIN to open it, wipe only the company data from it. |

> 📘 **Note:** This is the cleanest way to explain the difference: **MDM manages the box, MAM manages the company data inside the box.** MAM matters most when the device belongs to the employee and the company has no right to wipe the whole thing.

### Which platforms

Windows, macOS, iOS, iPadOS, Android and Linux.

> ⚠️ **Correction:** The instructor repeatedly listed **Linux** and **Chrome / Chromebook** alongside the rest as if they were equal. They aren't:
> - **Linux** support in Intune is narrow. It covers **Ubuntu Desktop** and **RHEL** for compliance policies, Microsoft Edge configuration and some app settings. You cannot manage a Linux box the way you manage a Windows one.
> - **ChromeOS** is **not** an Intune-managed platform. Intune can read a ChromeOS inventory through a connector to the Google Admin console, but the Chromebook itself is managed by Google, not by Intune. The instructor said *"they are planning, it's coming very soon"* — treat that as his expectation, not a fact.
>
> For an interview, say **"Windows, macOS, iOS/iPadOS and Android, with limited Linux support."** That's the safe and accurate answer.

### What you can do remotely

The instructor's list, which is really the IT support job description:

- **Install, uninstall and update applications**
- **Update the operating system**
- **Restart** the device
- **Scan for viruses**
- **Push settings and policies**
- **See the remote screen** (remote assistance)
- **Lock** the device, **remove the passcode**, **wipe** it

### The one condition, repeated four times

> **The device must be powered on and connected to the internet.**

*"It doesn't matter where your staff is working from — USA, Canada, Europe, Nepal, India. If they call and say they need software, you can install it from Australia."*

### What Intune cannot do, and why that's good news

The instructor spent nearly two minutes on this and clearly enjoys it.

- Intune **cannot touch hardware**. You cannot add RAM, replace a power cable or fix a dead battery from the cloud.
- If the **internet is down**, Intune can do nothing at all.
- If the machine **blue-screens** (BSOD) and won't boot, Intune can't help.

> *"That's why IT support jobs still exist. AI cannot replace us… you need a physical person to go and change the RAM, change the power cable, fix the internet."*

> 📘 **Note:** This is a genuinely good interview answer when someone asks about the limits of remote management. "Intune covers software, settings and policy. Hardware faults, network outages and a machine that won't boot still need someone on site." It shows you understand the boundary rather than overselling the tool.

### SCCM vs Intune ⭐ interview question

| | **SCCM** (System Center Configuration Manager) | **Intune** |
|---|---|---|
| Where it runs | **On-premises** — in your own building | **Cloud** |
| What you need | Your own **server** and **SQL database**, installed and maintained | A **subscription**. Nothing to install. |
| Age | The older product | The current product |
| Job | Endpoint management | Endpoint management |

Both are endpoint management tools doing the same job. The difference is only **where the management server lives**.

> **The instructor's exact interview advice:** *"If somebody asks 'do you know SCCM?', you can say: I know it theoretically, but practically I have worked on Intune. Both are the same, I can easily manage."*

> 📘 **Note:** Two extra facts that make this answer stronger:
> - SCCM is now called **Microsoft Configuration Manager**, and Intune plus Configuration Manager together are branded **Microsoft Intune suite** (the old umbrella name was **Microsoft Endpoint Manager**, which is why the instructor keeps saying it).
> - Running both at once is called **co-management**, and it's a real tab in the admin center — you'll see it in Part 21. Many large organisations are still in exactly that halfway state, so mentioning co-management shows you know the real world.

### Zero Touch Provisioning (ZTP) ⭐

A student asked for this to be explained and the instructor answered it three separate times, so it clearly matters to him.

**The problem it solves.** Normally, setting up a new starter's laptop means: install Office (download, run the installer), install Zoom (go to the download centre, download, install), set the Wi-Fi, set the policies, block what needs blocking. Every machine. By hand.

**What zero touch means instead.** The company writes all the policies and app assignments **first, before anyone joins**. Then:

1. A new starter is given a laptop or phone.
2. They **type their username and password**.
3. Everything arrives by itself — the software, the settings, the restrictions, the OS updates.

> *"They don't need to even touch. When they log in, everything automatically comes. That's why it's called zero touch provisioning."*

The instructor demonstrated this for real at 1:40:52 — see Part 19.

### Autopilot and Copilot ⚠️

The instructor mentioned both at 7:29 and then kept mixing them up for the rest of the class.

> ⚠️ **Correction — teach this carefully, the video gets it wrong:**
>
> | Name | What it actually is |
> |---|---|
> | **Windows Autopilot** | A **device provisioning** service. You register a new PC's serial number, and when it's first switched on it configures itself and joins the company automatically. **It does not install Windows and it does not do Windows Update.** |
> | **Microsoft Copilot** | **AI assistance** built into Microsoft 365 apps. Completely unrelated to device management. |
> | **Windows Update for Business / Update rings** | The feature that **actually** deploys monthly OS updates, patches and drivers from Intune. |
>
> At 7:38 the instructor says *"Autopilot means it's updating Windows OS… we will write the Windows Update policy every month and it's automatically updated, even the operating system, it fixes the patches."* That describes **Update rings**, not Autopilot. Later, from 1:57:50 onward, he repeatedly says **"Copilot"** when he means **"Autopilot"** — *"if you have thousands of devices you need to go with the Copilot"*. He means Autopilot every time.
>
> If a student answers "Autopilot patches Windows every month" in an interview, that's a wrong answer. The correct split is: **Autopilot = getting a brand-new device set up. Update rings = keeping it patched.**

### The feature list

The instructor's summary of what Intune covers:

- **MDM** — all device types
- **MAM** — application management and deployment
- **Windows Autopilot** — provisioning at scale
- **Apple Business Manager** — the Apple equivalent
- **Conditional access** — e.g. block sign-in from a particular country or network
- **BitLocker** — disk encryption policy
- **Cloud-based patching** — OS, drivers and security updates
- **BYOD** — *"bring your own device"*: an employee enrols their personal phone and gets company access on it

### Licensing

- **Business Premium includes Intune.** Everything in this class is covered by the licence the class already bought.
- Intune is also sold on its own as **Intune Plan 1** and **Intune Plan 2**, which are cheaper than a full Microsoft 365 licence — *"but you are not getting the email, you are just managing the devices only."*
- Enterprise (E3/E5), frontline worker and education plans include it at various levels.

> 📘 **Note:** The licence point comes back to bite the class at 1:55:38, and it's worth flagging now. In an earlier class they joined 16 devices to **Entra ID**. Those devices appear in the Entra portal but show **MDM = None**, and they do **not** appear in Intune at all — because at the time there was no Intune licence. **Entra ID join and Intune enrollment are two different things.** Joining Entra ID gives the device an identity. Intune enrollment gives you management. You need the licence for the second one.

---

## Part 2 — The Intune admin center (13:17 – 15:00)

**Two ways in:**
- From **admin.microsoft.com**, scroll down the left menu to **Microsoft Intune** (listed under "All admin centers").
- Or go straight to **intune.microsoft.com**.

It opens a **separate admin dashboard**, called the **Microsoft Intune admin center** (the instructor called it the "Endpoint admin centre" — the old name was Microsoft Endpoint Manager admin center).

### The tabs, and which ones matter for this course

| Tab | What it's for | This course? |
|---|---|---|
| **Devices** | **MDM** — enrollment, compliance, configuration, every managed device | ✅ **Yes — this is the main one** |
| **Apps** | **MAM** — deploying and protecting applications | ✅ **Yes** |
| **Endpoint security** | Antivirus, disk encryption, firewall, attack surface reduction | ❌ *"This is for cyber security, not for us"* |
| **Users** | The same users as in Microsoft 365 | Already covered |
| **Groups** | The same groups as in Microsoft 365 | Already covered |
| **Tenant administration** | Tenant-wide settings, branding, customisation | Already covered |
| **Reports** | Compliance and deployment reporting | Lightly |

> *"This is SSO — single sign-on. All users are coming from the same place, groups from the same place, the tenant and the logo and the customisation all from the same place. The extra features we need to practise here are **Apps**, which is MAM, and **Devices**, which is MDM."*

### The enrollment dashboard

**Devices → Overview** shows a count by platform. At the start of class every one was **zero**: Android 0, iOS/iPadOS 0, Linux 0, macOS 0, Windows 0.

By the end of the class there were nine iPhones and one Windows machine.

---

## Part 3 — The plan, and a warning about personal devices (15:00 – 17:30)

The instructor explained how he'd run the class, and the reasoning is worth keeping.

**The plan:**
1. Do **Apple/iOS first**, live, together, with everyone watching.
2. Write a few policies, install a few apps, prove it works.
3. **Delete every phone from Intune before the end of the class.**
4. Then move to **Windows**, where you can practise as much as you like.
5. Tomorrow: finish Windows, then start **SharePoint and Teams**.

**Why delete the phones:**

> *"If somebody wipes from here, they will erase everything from your mobile device… everybody here is a global administrator and they can misuse the devices, intentionally or unintentionally. That's why I'm not taking that challenge. I want to do everything under my supervision and then I'll remove the devices."*

**Why Windows is the safe place to practise:** the demo Windows machine is a **VMware virtual machine**. *"I can reset, I can format, I can do whatever. I'm very confident over here. But iPhone is very risky."*

> 📘 **Note:** Two real lessons hide inside this housekeeping, and both are worth saying out loud to a student:
>
> 1. **Never test MDM policies on your own personal phone.** Use a virtual machine, a spare device, or a tenant where you're the only administrator. A mistaken **Wipe** on an enrolled personal phone factory-resets it, and there is no undo.
> 2. **"Everybody is a global administrator" is a classroom convenience, not a real configuration.** A real tenant has a very small number of Global Administrators. Device work is done with the **Intune Administrator** role, which can manage devices and policies but can't touch billing, domains or other admins. Microsoft's guidance is two to four Global Admins with break-glass accounts, everyone else on least privilege. The instructor acknowledges this himself at 1:19:31: *"in real, users don't have power to cancel. At the moment we are all global administrators, we have all power."*

---

## Part 4 — The Apple MDM Push Certificate ⭐ (17:30 – 27:10)

This took ten minutes and is one of the two or three things from this class most likely to come up in an interview. The conceptual explanation is excellent.

### The concept: you are borrowing Apple's authority

The instructor built it up slowly:

1. **Apple controls every Apple device.** *"Our iPhone, our Mac, everything is managed by Apple. They have full control. They can push us updates. If they want, they can break the iPhone, they can break iCloud. They have all the features."*
2. At the moment Apple gives the **user** a choice — *"the user has a choice to upgrade or not, it's up to them."*
3. **But the company bought the device.** *"If we buy our devices, it belongs to my company and I want to get control of that device."*
4. So the company has to **ask Apple for that authority**. *"They are not giving it directly. If you say 'I want to manage on behalf of my company', you need to get the approval from them."*

> 💡 **The instructor's analogy, used twice and worth repeating:** *"We are taking the brain of all the Apple devices and bringing it to Intune, and controlling from here. That's why we needed permission from Apple. Apple says 'I don't have any problem' — then we can do it."*

### Why only Apple needs this

| Platform | Approval needed? | Why |
|---|---|---|
| **Windows** | ❌ No | *"Windows is already part of it"* — Microsoft owns both Windows and Intune |
| **Apple** (iOS, iPadOS, macOS) | ✅ **Yes** — an Apple MDM Push Certificate | Different company, and *"Apple is a very strict company"* |
| **Android** | ✅ Yes | Different company again — you connect Intune to **Google** (Managed Google Play) with a Google account |

### How to do it

**Devices → iOS/iPadOS → Enrollment → Apple MDM Push Certificate.** The page says plainly: *"A certificate is required to manage Apple devices."*

The round trip is:

1. In Intune, **agree** to let Microsoft send user and device notifications to Apple.
2. **Download the request file** from Intune.
3. Go to Apple's push certificate portal and **sign in with the company Apple ID**.
4. **Upload** the file you got from Microsoft.
5. Apple issues a certificate. **Download it.**
6. Come back to Intune and **upload the Apple certificate**.

The instructor summarised the loop himself at 26:05: *"We went to Intune, the Apple tab, enrollment, downloaded a certificate from Intune, logged into Apple, uploaded that certificate, Apple gave us another certificate, we downloaded it and brought it back to Intune and uploaded it."*

### The three rules ⭐

The instructor hammered these, and then the class hit all three live.

| Rule | Detail |
|---|---|
| **One certificate per tenant** | You cannot have two. Only **one representative on behalf of the company** sets it up. |
| **One Apple ID, forever** | Whichever Apple ID created it must be the one that **renews** it. |
| **Renew every year** | The certificate the class saw expired **30 May 2027**. *"You need to renew it every year."* |

**What went wrong in class, and why it's a useful lesson.** The instructor tried to create the certificate and it wouldn't take — the page kept saying the ID didn't match the existing request. He checked the file, suspected a leading space in the Apple ID, tried again. Then a student spoke up: **he had already done it earlier.** That was the whole answer. The tenant already had its one certificate, created under a different Apple ID, so nothing the instructor did would work.

A student then asked whether he should delete it and start again. The answer:

> *"If you delete, we need to restart. Leave it. Only one ID, one person on behalf of the organisation."*

> 📘 **Note — this is the single most important practical point in Part 4.** Use a **shared company Apple ID** (something like `appleid@company.com` that the IT team owns), never a personal one. The instructor used his own Apple account as the example and said *"I'm just giving an example, the company has their own Apple account."* Here's why it matters:
>
> - If the person who created it **leaves the company** and nobody has their Apple ID, you cannot renew the certificate.
> - When it **expires**, **every enrolled Apple device stops being manageable** and has to be **re-enrolled by hand**. On a few hundred iPhones that is a very bad month.
> - So: shared Apple ID, documented, in the password manager, with a **calendar reminder 30 days before expiry**.

**How to check whether it's already done:** Devices → iOS/iPadOS → Enrollment → Apple MDM Push Certificate. It will show the status and the expiry date.

**Who does this job?** A student asked whether it's Level 1, 2 or 3. The instructor: *"Level 2, definitely. But you need to understand how it works."*

---

## Part 5 — Enrolling an iPhone with the Company Portal (27:10 – 40:20)

Everyone did this together, live.

### The steps

1. Open the **App Store** on the phone.
2. Search for **Intune Company Portal** (type the full name — searching for just "company portal" is less reliable).
3. **Get / install** it, and open it.
4. **Sign in with the company Microsoft 365 account** — the same username and password used everywhere else in the course.
5. The app shows **four steps** to complete. Tap **Begin**, and **trust** the connection when asked.

| Step | What happens |
|---|---|
| **1. Review privacy** | Read what the company can and cannot see. Tap Continue. |
| **2. Download the management profile** | **Automatic** — the phone downloads it by itself. |
| **3. Install the management profile** | ⚠️ **This is the step everyone misses.** It is **not** done inside the app. **Leave the app open, go to the iPhone's Settings**, and tap **Profile Downloaded** near the top. Then **Install**, enter the passcode, **Install** again, and **Trust**. Then go **back to the Company Portal app**. |
| **4. Final check** | **Automatic.** Takes a little longer than the others. Nothing to tap. |

Then **Done**. The app now shows the device as managed: *"Can access company resources."*

### What the app shows afterwards

Manufacturer (Apple), model, OS version, the company name, device details, and whatever terms and conditions the company has published.

> *"Now my device is under the control of jobforit. Now I don't need to do anything, we'll manage everything from there."*

### The same process for everything else Apple

- **macOS** — download Company Portal for Mac, sign in. *"Same process, because it is Apple."*
- **iPad** — same.
- **Android** — same idea, but you first connect Intune to Google: **Devices → Android → Enrollment**, agree, and connect with a Google account. Nobody in the class had Android, so this wasn't demonstrated.

### Devices appearing in the console

Devices start appearing in **Devices → All devices** within about **four or five minutes**. By 38:33 there were nine.

The instructor's rule for the class, stated twice: **"Don't touch anything."** Everyone was a Global Administrator, and anything one person did would hit everyone's phone.

### The iPhone 6 problem

One student couldn't find the app. The reason turned out to be the device: an **iPhone 6**, released 2014, running **iOS 15.8.7**.

The current Intune Company Portal requires a much newer iOS, so the app wasn't offered in the App Store. The instructor's advice: *"Either update the OS, or find another phone."* The phone came up again in Part 6, where the compliance policy excluded it too.

> 📘 **Note:** This is realistic and worth teaching as a pattern, not a one-off. **Microsoft supports the last few iOS major versions, and Apple only supplies new iOS to devices it still supports.** On an old phone those two facts collide and there is no fix except a newer phone. In a real job this is a common ticket, and the answer is a hardware refresh, not troubleshooting. Knowing when to stop troubleshooting is part of the skill.

---

## Part 6 — Compliance policies ⭐ (40:20 – 45:10)

### What compliance means

> **A compliance policy is the list of conditions a device must meet before the company treats it as trustworthy.** The instructor's phrasing: *"Compliance is whether the device meets the hardware requirement or the operating system requirement. That is the terms and conditions."*

A device is then reported as **Compliant** or **Not compliant**.

**Where:** **Devices → iOS/iPadOS → Compliance policies → Create policy.**

### What you can check on iOS

| Section | Examples |
|---|---|
| **Email** | Require a managed email profile |
| **Device health** | **Jailbroken devices** blocked |
| **Device properties** | **Minimum OS version**, maximum OS version |
| **System security** | Passcode required, length, complexity, encryption |

Note what's **not** there: *"You can go with the minimum operating system, but **no minimum hardware**."* Compliance checks software and configuration, not CPU or RAM.

### What was done in class

The instructor checked the room's OS versions — most phones were on **iOS 26.5**, a couple on 26.2 and 26.4, one on 15.8.7.

He set **minimum OS version = 17.0.0.0** and assigned it to **all devices**.

The effect:
- Everything on iOS 17 or above → **compliant**
- The iPhone 6 on 15.8.7 → **not compliant**, excluded

> *"If I wrote 'not supporting lower than 26.5', this device would be kicked out from here. It says 'you are not following the company policy'."*

### ⚠️ What he said next, and why it matters

> *"But in the real world, don't do that. If you have a very low-level operating system, a hacker can easily get in."*

He deliberately set a low bar (17.0) so the class could see devices pass, and then told them not to copy it. **Teach the warning alongside the demo.** Old iOS versions have unpatched vulnerabilities; the whole point of a minimum-OS compliance policy is to keep them off company data.

> 📘 **Note — the bit the video leaves out, and it's the most valuable part.** Marking a device "not compliant" does nothing on its own. It's just a label in a report. Compliance only has teeth when you pair it with **Conditional Access** in Entra ID: *"require device to be marked as compliant"* before the account can reach Exchange, SharePoint or Teams.
>
> **With Conditional Access:** the old iPhone is marked non-compliant → Conditional Access blocks it → **no company email on that phone** until it's updated.
> **Without Conditional Access:** the old iPhone is marked non-compliant → a number in a report changes → **nothing else happens at all.**
>
> This is a strong thing for a student to say in an interview, because most candidates only know half of it: *"A compliance policy defines what a healthy device looks like. Conditional Access is what enforces it."*

---

## Part 7 — The individual device page (45:10 – 50:00)

**Devices → All devices → click a device.**

### Personal vs corporate ownership

**Properties → Device ownership: Personal / Corporate.**

The instructor switched his own phone to **Corporate** to demonstrate. His explanation: *"If you move it to corporate, they have more flexibility to monitor. They can see where you are logging in from, what you are accessing."*

> ⚠️ **Correction:** That overstates it. Intune does **not** read your browsing or watch what you do. What ownership actually changes:
>
> | | **Personal** | **Corporate** |
> |---|---|---|
> | **App inventory** | Intune lists **only company-deployed apps**. Personal apps are deliberately hidden. | Intune lists **all installed apps** |
> | **Available actions** | Fewer | More, including full wipe |
> | **Enrollment restrictions** | Can be blocked entirely (see Part 21) | Always allowed |
>
> What Intune never sees, on either setting: call history, SMS content, photos, browsing history, personal email, or the contents of personal apps. Microsoft publishes this list, and it's worth knowing — *"can my employer read my texts?"* is the single most common question a user asks when they're told to enrol their phone. The honest answer is no, and being able to say exactly what the company **can** see is what makes people agree to enrol.

### The device actions

Across the top of a device's page:

| Action | What it does |
|---|---|
| **Sync** | Force the device to check in now instead of waiting |
| **Restart** | Reboot it remotely |
| **Remote lock** | Lock the screen. The user needs their passcode to get back in. |
| **Remove passcode** | Clear the passcode (useful when someone is locked out) |
| **Rename** | Change the device name |
| **Retire** | Remove company data and management, leave personal data |
| **Wipe** | **Factory reset** |
| **Delete** | Remove the device record from Intune |

### Wipe, and the credit card analogy

> *"If you wipe from here, everything is deleted and you get a fresh iPhone, like when you bought it the first time."*

**The real use case:** a lost or stolen device.

> 💡 **The instructor's analogy:** *"If you lose your credit card, you call the bank and cancel the card immediately. Same thing — if you lose the device, wipe it immediately. At least you are only losing $600. For a company, the device is nothing. **The data is what's important.**"*

### The inventory — what Intune can read

**Hardware** tab. The instructor went through his own phone's values, and this list is a good demonstration of how much detail MDM gives you:

| Field | His device |
|---|---|
| Model | iPhone 16 Pro Max |
| Serial number | ✓ |
| **IMEI** | ✓ *"This is a very important one"* |
| Total storage | 256 GB |
| Free storage | 165 GB |
| **Battery level** | 11% |
| Phone number | ✓ |
| **Carrier** | Vodafone |
| Cellular technology | GSM |
| Last check-in | Today |

> 📘 **Note:** **IMEI** is the point to dwell on. It's the permanent hardware serial of a phone, it doesn't change when you swap the SIM, and it's what you give the police and the carrier when a company phone is stolen — the carrier can blacklist the IMEI so the handset can't be used on any network. The practical lesson: **Intune is also your asset register.** When the finance team asks "what phones do we own and who has them", the answer is in here.

**Remote assistance** showed as *"not configured"* — this needs a separate Remote Help licence.

---

## Part 8 — Configuration profiles: blocking the camera ⭐ (50:00 – 54:00)

This was the moment the class landed.

### What a configuration profile is

> *"Configuration means whatever setting you can do on your own iPhone, **I can do from here, for every device at once.**"*

**Where:** **Devices → iOS/iPadOS → Configuration → Create → New policy.**

### The demonstration

The instructor picked the camera because it's instant and visible. He created a profile, searched the settings for **camera**, found **"Allow camera"**, set it to **blocked** / **not allowed**, and assigned it to **all devices**.

Then he pushed it: **Devices → All devices → select the devices → Bulk device actions → iOS/iPadOS → Sync.**

Then everyone checked their phone — and the **camera app had disappeared**.

> *"Camera, gone. You cannot take that camera back."*
> *"Sir, we are over here, we are not physically present."*
> *"Yes. We are controlling from here."*

### How to verify, from both ends

| From | How |
|---|---|
| **The admin side** | The configuration profile's **Device status** page: how many Succeeded, how many Error, how many Pending |
| **The device side** | Open the **Company Portal app → Devices → your device → Check status**. This forces an immediate sync. |

**Check status in the Company Portal is the fastest way to make a policy land.** The instructor used it repeatedly throughout the class whenever the class got impatient.

The result for this push: **8 succeeded, 1 error**. He showed the class how to find which device errored and check it.

> 📘 **Note — why nothing happens instantly, and what to tell a user.** Intune works on a **check-in** schedule, not instantly. Typical intervals:
>
> | Platform | Normal check-in |
> |---|---|
> | iOS / iPadOS | about every **8 hours** |
> | Windows | about every **8 hours** |
> | Android | about every **8 hours** |
> | macOS | about every **8 hours** |
>
> Freshly enrolled devices check in far more often — roughly **every 15 minutes for the first few hours**, then settle into the normal rhythm.
>
> So when a policy "doesn't work", the first question is **has the device checked in yet**, not "is the policy wrong". Force it with **Sync** from the console or **Check status** in the Company Portal. The class saw this the hard way in Part 11, where a policy took so long they moved on and came back to it.
>
> **This is a real helpdesk skill:** telling a user *"it's applied, it'll land within a few hours, or tap Check status in Company Portal to pull it now"* is a much better answer than *"I don't know why it's not working."*

---

## Part 9 — More configuration: templates vs the settings catalogue (54:00 – 1:06:30)

### The two ways to find a setting ⭐

This is the practical navigation skill, and the instructor gave it as a tip.

| Approach | What it is | When to use it |
|---|---|---|
| **Templates** | Microsoft's **pre-built groups** of related settings — "Device restrictions", "Email", "VPN", "Wi-Fi". Organised, curated, finite. | You're doing something common and want it laid out for you |
| **Settings catalogue** | A **searchable list of every setting** Apple exposes, with no structure. Thousands of them. | You know what you want and need to find it fast |

> **The instructor's tip, in his own words:** *"Go to the Create tab, select iOS, and it's up to you — either template or settings catalogue. I think go with the settings catalogue, give any name, then search for whatever you want to do."*

### What he showed in the Device restrictions template

- **Passcode** — require a passcode, block simple passcodes, minimum length, maximum failed attempts before the device wipes
- **Prohibited apps** — a list of apps that must not be installed. *"We can restrict YouTube on the corporate device. You can even hide YouTube — they cannot even download YouTube."*
- **Show / hide apps** — the allow-list and hide-list (used properly in Part 11)
- **Face ID / Touch ID** — *"Everything. Whatever setting you can do on your iPhone, we can do from here."*

### What he showed in the settings catalogue

Searching turned up, among thousands:

- **App lock / single-app mode** — lock the device to one application
- **Accessibility** — enable zoom, VoiceOver, voice control, mono audio
- **Hardware controls** — disable torch, disable the sleep/wake button, disable the ringer switch
- **Microsoft Edge settings** — a whole section of its own
- **AirPrint** — *"Do you want to allow AirPrint? If you say false, you can remove it. You can give a specific IP address so they can print only to that printer."*
- **Lock screen message** — text shown on the lock screen
- **Security / passcode** — force PIN, maximum failed attempts, require alphanumeric

### Targeting one department

A student asked how to apply something to one department rather than everyone:

> *"If you want to go for one department, create a group. If you create a group, it works for that department only."*

This is picked up properly in Part 13.

### Remote lock from the list view

You don't have to open a device. **Devices → All devices → select → Remote lock** works straight from the list. The instructor demonstrated it again later at 1:31:52, where the phone locked by itself a few seconds after he clicked.

---

## Part 10 — Student question: Jamf Pro vs Intune (1:06:33 – 1:07:15)

A student with previous experience asked which is more popular, **Jamf Pro** or **Intune**, and said he used to use Jamf Pro to manage Apple devices and finds Intune has similar features.

**The instructor's answer:** *"Intune is very, very popular nowadays, especially in Australia."*

> 📘 **Note:** Both answers are right, and the distinction is worth knowing because it comes up in interviews at Apple-heavy workplaces:
>
> | | **Jamf Pro** | **Intune** |
> |---|---|---|
> | Covers | **Apple only** — macOS, iOS, iPadOS, tvOS | **Everything** — Windows, Apple, Android, some Linux |
> | Depth on Apple | Deeper. Supports Apple-specific features sooner. | Good and improving, slightly behind Jamf on new Apple features |
> | Typical buyer | Design, media, education, Apple-first companies | Anywhere already paying for Microsoft 365 |
> | Cost | Separate product, separate licence | **Already included in Business Premium / E3 / E5** |
>
> Many organisations run **both**: Intune for Windows, Jamf for Macs, with Jamf feeding compliance data back to Intune through a connector. The licence argument is usually what decides it — if you're already paying for Business Premium, Intune costs nothing extra.

---

## Part 11 — Hiding an app, and why sync takes time (1:07:15 – 1:15:04)

### Hiding Facebook

The instructor used **Device restrictions template → Show or hide apps → Hidden apps**, and this is where the class learned that hiding an app needs more than its name.

**What you have to supply for each app:**

| Field | For Facebook |
|---|---|
| **App bundle ID** | `com.facebook.Facebook` |
| **App name** | Facebook |
| **Publisher** | Meta |
| **App Store URL** | the App Store link |

> 📘 **Note:** The **bundle ID** is the thing to understand. It's the app's permanent unique identifier on iOS — `com.facebook.Facebook`, `com.zhiliaoapp.musically` (TikTok), `com.google.ios.youtube`. The display name is not enough, because names change and are not unique.
>
> **How to find one:** open the app's App Store page, take the numeric ID from the URL, and look it up via the iTunes lookup API, or read it from an enrolled device's discovered-apps inventory in Intune. In a real job you keep a list of the bundle IDs your organisation blocks.

The instructor noted this is the same idea as **Group Policy** on Windows — a central rule naming an application precisely.

### The waiting

Then the policy didn't arrive. For six minutes.

> *"Facebook is still on my iPhone… let's give it some time… is it gone for anyone?"* — *"No."* — *"It says 0 succeeded. It takes a little bit of time."*

He synced from the console, synced from the Company Portal, and eventually moved on to apps and came back later. The instructor's own conclusion at 2:12:58: *"It takes a little bit of time. Maybe if you come tomorrow it will work."*

> 📘 **Note:** This wasn't a mistake — it's how Intune behaves, and it's worth being honest with a student about it. See the check-in table in Part 8. The lesson: **plan around the delay.** Don't promise a user an instant change, and don't start re-editing a policy after two minutes because you think it failed. Check the **Device status** report first; if it says Pending, the policy is fine and the device simply hasn't checked in.

### The role problem

A student couldn't apply anything — *"it says you are not authorised."* The instructor checked: **Users → Active users → [the student] → Roles**. The student had **User Administrator**, not Global Administrator. He changed it, and it worked.

> 📘 **Note:** Diagnostically this is a good example. **"Not authorised" almost always means a role problem, not a broken product.** The right role for device work is **Intune Administrator** — not Global Administrator. The instructor handed out Global Admin because it was a classroom and it was quicker, but in a real job, giving someone Global Admin to fix an Intune permission error would be a finding in a security audit.

---

## Part 12 — Deploying applications ⭐ (1:15:04 – 1:20:46)

### How to deploy an app

**Apps → iOS/iPadOS → Add →** choose the app type **→** pick the app **→** assign it.

The instructor deployed three, to all devices:

| App | Why he picked it |
|---|---|
| **GlobalProtect** (Palo Alto VPN) | A realistic corporate app |
| **Firefox** | *"I think nobody has Firefox"* — so the arrival would be visible |
| **AnyDesk** | Pushed by a student, which made the point nicely |

> *"I want to select all devices. That's it. Done. How easy?"*

### What happened on the phones

Within a minute or two, notifications arrived:

> *"jobforit is about to install and manage GlobalProtect from your App Store. Your account will not be charged."*

Then Firefox. Then AnyDesk, pushed by a student — *"somebody pushed AnyDesk, anyway, I agree."*

Two asides from the instructor that are worth keeping:

- **You can suppress the notification.** *"You can bypass the notification. But I wanted to show you, that's why the notification is coming."*
- **In a real tenant the user couldn't cancel.** *"In class everybody is a global administrator, so you can cancel it yourself. In real, users don't have the power to cancel."*

And a practical warning: *"Don't enforce many applications — the mobile is already slow."*

### Assignment is not optional

Firefox showed **"Not assigned"** at first. The instructor had created the app but hadn't completed the assignment step.

> 📘 **Note:** Worth saying explicitly because it's the most common beginner mistake in Intune: **creating a policy or app does nothing until you assign it.** Every policy, profile, compliance rule and app has an **Assignments** tab, and an unassigned object sits there doing nothing forever. When something "doesn't work", check two things in this order: **(1) is it assigned, (2) has the device checked in.** That covers the large majority of cases.

---

## Part 13 — Targeting with security groups ⭐ (1:20:46 – 1:23:14)

### Why you need a group

Assigning to **All devices** is fine for a demo and wrong for a company. Real targeting is: *"IT department gets these apps, Finance gets those, contractors get neither."*

That requires a **group**.

### Which group type ⭐

The instructor referred back to the four group types from class 2 and made a specific point:

| Group type | Can it target Intune policies at **devices**? |
|---|---|
| **Security group** | ✅ **Yes — this is the one** |
| Mail-enabled security group | ❌ No |
| Microsoft 365 group | ❌ Not for devices — *"that's for email purposes"* |
| Distribution list | ❌ No |

> *"Microsoft 365 is for email purposes. For device management you need a security group. A mail-enabled security group does not have the feature of managing devices — **only the security group has the feature of managing devices.**"*

### What was done in class

He created a security group called **IT devices**, set an owner, and then — the key step — added **devices as members, not users**. Two enrolled iPhones went in.

Then he created an app assignment (Cisco Webex) and, instead of **All devices**, selected the **group**. Only those two phones got it.

> *"This time I'm not going to select all. I'm going to select the group. If you want to select a department, you need to create the group, and only that group will get it."*

> 📘 **Note:** One distinction the video skips, and it matters when you start designing this for real:
>
> - A group with **device** members → used to target **device configuration**, compliance and required apps. The policy follows **the hardware**, whoever signs in.
> - A group with **user** members → used to target **app protection** policies and available apps. The policy follows **the person**, whichever device they use.
>
> So "block the camera on warehouse tablets" is a **device** group. "Require a PIN on Outlook for everyone in Finance" is a **user** group. Picking the wrong one is why a policy applies to the wrong things.
>
> Also worth knowing: groups can be **dynamic**, with a membership rule such as "every iOS device" or "everyone whose department is Finance", so membership maintains itself. That's how this is done at scale rather than adding devices by hand.

---

## Part 14 — The app types in Intune (1:23:14 – 1:25:05)

When you add an app you must choose its **type**. The instructor went through the list.

| Type | What it is | Example |
|---|---|---|
| **Store app** | From the App Store, Google Play or the Microsoft Store. *"Most of the applications we need, the store has."* Free or paid. | Firefox, Zoom, GlobalProtect |
| **Web link / web app** | A **shortcut to a URL** that appears like an app icon. *"Like a bookmark — when you click it, it automatically opens."* | The staff intranet |
| **Line-of-business (LOB) app** | **The company's own software**, uploaded as an installer file (.ipa, .apk, .msi, .intunewin) | An in-house booking system |
| **Microsoft 365 apps** | The Office suite as a managed bundle | Word, Excel, Outlook, Teams |

A student asked how a company deploys its own in-house application. The answer: **line-of-business**, and for Windows that means **packaging**.

> *"That is called packaging and deployment. We'll do the packaging and deployment as well."* — he deferred the demo to the Windows class.

> 📘 **Note:** The Windows packaging step is worth naming now so the student recognises it later. Windows LOB apps are wrapped with the **Microsoft Win32 Content Prep Tool**, which turns an installer plus its files into a single **`.intunewin`** package. You upload that, then tell Intune the **install command**, the **uninstall command** and a **detection rule** (a file, a registry key or an MSI product code) so Intune can tell whether the app is already there. That's the piece beginners miss: without a detection rule, Intune doesn't know if the install worked.

---

## Part 15 — Device actions: retire, wipe, delete ⭐ (1:25:05 – 1:29:31)

The instructor summarised the whole iOS workflow and then explained the destructive actions with an analogy. **This is an interview favourite** — and the video gets part of it wrong, so read the correction.

### The instructor's analogy

| Action | His explanation |
|---|---|
| **Retire** | *"The guy is still part of the company but not using the device anymore. Like the army — if they retire, sometimes they can be called again."* |
| **Delete** | *"You are out of the company. If that guy left the company, they never call back, no allowance, nothing."* |
| **Wipe** | *"You can wipe out the device from here."* |

The retire/delete distinction as *"still with us"* vs *"gone"* is memorable, and the employment framing is a reasonable way in. But the technical meanings are different from what the analogy implies.

> ⚠️ **Correction — the accurate definitions. Teach these, and use the analogy only as a memory hook:**
>
> | Action | What it removes | What survives | When you use it |
> |---|---|---|---|
> | **Retire** | Company data, company apps, company email profile, and Intune management | **The user's personal data, photos, apps and accounts are untouched** | **A BYOD phone** when someone leaves, or stops using it for work. The employee keeps their phone and their life on it; the company gets its data off. |
> | **Wipe** | **Everything — full factory reset** | Nothing | **A lost or stolen device**, or a **company-owned** device being reassigned |
> | **Delete** | The **device record in Intune**. Management stops at next check-in. | Whatever is on the device right now | Tidying up stale records for devices that no longer exist |
>
> The real distinction is **Retire = company data only** versus **Wipe = everything**. That's the answer to *"what's the difference between retire and wipe?"*, which is asked constantly.
>
> **Retire is the one to reach for on a personal phone.** Wiping an employee's own phone when they resign destroys their family photos and is the kind of mistake that ends up with HR and lawyers.

### What the delete warning actually says

The instructor read it out, and it's worth reading to a student verbatim:

> *"If you delete these devices, you will no longer be able to view or manage them from the Intune portal. The device will no longer be allowed to access your corporate resources. **Company data may be wiped from the device if the device tries to check in later.**"*

He then paraphrased it as *"if it is deleted, data will automatically wipe"* — note the real wording is **may** be wiped, **company** data, and **only when the device next checks in**. A device that never checks in again keeps whatever it has.

### Custom notifications

**Devices → Send custom notification.** You give a title and a message, pick all devices or specific ones, and it arrives as a push notification.

He sent: *"Welcome to our class, please do not use many applications."*

It arrived in the Company Portal app and in the phone's notification tray.

> 📘 **Note:** Not a toy. Real uses: *"Your device needs updating by Friday or you'll lose email access"*, *"Planned maintenance tonight"*, *"Please restart to finish installing updates"*. It reaches a managed phone without needing the user's personal number or email, which matters for frontline and shift staff who don't sit at a desk.

### The other bulk actions

**Devices → Bulk device actions** — pick the platform and the action:

- **Sync**
- **Restart**
- **Rename**
- **Retire** / **Wipe** / **Delete**
- **Update cellular plan** (for eSIM)

> *"If it's one device, do it one. If it's bulk, you can do it in bulk."*

---

## Part 16 — Licence and role housekeeping, mid-class (1:29:57 – 1:31:50)

A short detour, but a useful revision of class 2 in a real context.

A student (Ram) couldn't do the exercises. The instructor checked and found he had **no licence**. The tenant trial had 25 licences and they were all allocated.

What he did:
1. Looked for licences that weren't being used — students in other classes, duplicate accounts.
2. Found a **duplicate account he had created himself** and **deleted it**, freeing a licence.
3. Assigned the licence to Ram.
4. Gave him the **Global Administrator** role.
5. **Removed the previous role first** — *"sometimes there's a conflict between the two roles."*

> 📘 **Note:** Three class-2 lessons show up here, and it's worth pointing them out because they land better in a real situation than in a list:
>
> 1. **Licences are finite and they cost money.** Someone has to track who has one. This is a genuine daily IT support task.
> 2. **No licence means no service.** Ram wasn't blocked by a permission problem — he had nothing to use. Always check the licence before troubleshooting anything else.
> 3. **Stacking roles causes trouble.** Remove the old role when you grant a new one. The instructor's instinct here was right.

---

## Part 17 — The per-device review, and an iOS update policy (1:31:50 – 1:38:50)

### The device page tabs, one by one

The instructor walked his own phone's page as a summary:

| Tab | What it shows |
|---|---|
| **Overview** | Compliance state, last check-in, primary user, ownership |
| **Properties** | Device name, **ownership** (personal/corporate), **device category** |
| **Hardware** | The full inventory from Part 7 |
| **Discovered apps** | Every app Intune can see installed |
| **Device compliance** | Each compliance policy and whether this device passes. His showed the **minimum iOS 17** policy — compliant. |
| **Device configuration** | Each configuration profile and its result. His showed **three profiles**: camera block **succeeded**, the others **not applicable**. |
| **App configuration** | App-specific settings |
| **Group membership** | Which groups this device is in |

> 📘 **Note:** **"Not applicable"** is not a failure, and the difference is worth explaining. **Succeeded** means applied. **Error** means it tried and failed. **Pending** means the device hasn't checked in. **Not applicable** means the setting doesn't exist on this device or OS version — an iPad-only setting on an iPhone, or a setting Apple removed. Beginners chase "not applicable" as a bug. It usually just means the policy is broader than the device.

### Writing an iOS update policy

He wanted to push an iOS update to one device. First he looked for an **Update policies for iOS/iPadOS** option and hit a duplication error, so he used the **settings catalogue** instead:

**Devices → iOS/iPadOS → Configuration → Create → New policy → Settings catalogue**, then under the setting picker:

**Declarative Device Management → Software Update**

Fields to fill in:

| Field | Value |
|---|---|
| **Target OS version** | 26.5 |
| **Target date** | today's date |
| **Target time** | 8:20 PM |

The class spent several minutes on the **time format** — it wanted a specific pattern and kept rejecting entries, and the instructor worked through AM/PM, seconds and separators until it took.

He assigned it to a **security group** containing just the one device.

> 📘 **Note:** **Declarative Device Management (DDM)** is Apple's newer management model, and the name is worth knowing because it's increasingly where Apple settings live. The old way: the server sends a command and waits to be asked. The DDM way: the server **declares the desired state** — "be on 26.5 by 8:20 Pm tonight" — and the **device takes responsibility** for getting there and reporting back. It's more reliable and faster, and Apple is moving software updates, passcode policy and more into it. If a student sees "declarative" in the settings catalogue, that's what it means.

### The time zone detour

Checking the deadline raised the question of **which time zone** Intune uses. The instructor went to **Settings (gear icon) → Language + region** and found the portal set to a different region.

He then showed where a **user's** country is set: **Users → [user] → Edit properties → Country or region**, and changed a student's from Nepal to Australia.

> 📘 **Note:** Keep two things apart here, because the video blurs them:
> - **Your portal's display region** only affects how dates and times are shown **to you**.
> - **A user's country** affects licence availability, data residency and some service behaviour.
>
> And for policies, the one that actually matters is neither: **Intune schedules are evaluated against the device's own local time zone**, not the admin's. If you set a deadline of 8 PM and your devices are in three countries, that's three different moments. For a global rollout, say so explicitly rather than assuming.

---

## Part 18 — App protection policies (MAM) ⭐ (1:38:50 – 1:40:40)

This is the **MAM** half of Intune, and it's the part most people have never heard of. The instructor moved quickly, so this section is worth slowing down on when you teach it.

**Where:** **Apps → App protection policies → Create policy.**

### What it protects

Not the device — **the company data inside the app**.

| Setting the instructor showed | What it does |
|---|---|
| **Block organisation data to iCloud / backup** | Company data can't be backed up to a personal cloud |
| **Allow user to save or copy data** | Controls copy-and-paste and Save As out of managed apps |
| **Block third-party keyboards** | Stops keyboards that send keystrokes to someone else's servers |
| **Require encryption of organisation data** | Company data is encrypted inside the app |
| **Require PIN to access** | A separate PIN just to open the work app |
| **Target: all Microsoft apps / all apps / selected apps** | Which apps the policy covers |
| **Selective wipe** | **Remove only the company data** from the app, leaving everything personal. Can be aimed at one specific user. |

He also noted **app categories** — tagging an app as a business app or a management app so it's grouped sensibly in the Company Portal.

> *"Whatever you want to do in order to protect the data — it has everything."*

### Why this matters more than it sounds ⭐

> 📘 **Note:** App protection is the answer to the hardest real question in device management: **"I'm a contractor. I'll read my work email on my own phone, but you're not managing my phone."**
>
> With **MDM** you'd have to enrol their phone, and they'd (reasonably) refuse.
>
> With **MAM / app protection** you don't need the device at all. The policy attaches to **Outlook and Teams on that phone**:
> - Work email needs a PIN to open
> - Company data can't be copied into WhatsApp or saved to personal iCloud
> - On their last day, a **selective wipe** removes the company data from those apps and **touches nothing else**
>
> This is called **MAM without enrollment** or **app protection without device enrollment**, and it's how most organisations handle contractors, consultants and staff who won't enrol a personal phone.
>
> **The one-line version for an interview:** *"MDM manages the device. MAM manages the company data inside the apps, and works even on a device you don't manage."* That answer alone puts a candidate ahead of most.

---

## Part 19 — Zero touch, proved (1:40:40 – 1:42:40)

The instructor closed the loop on the concept from Part 1 by asking the class a question:

> *"Now we've done all this. If you onboard a new iPhone, do you need to do anything?"*

**No.**

- The camera will **already be blocked**
- GlobalProtect, Firefox and AnyDesk will **install by themselves**
- The compliance policy will **already apply**
- The user **types their username and password, and nothing else**

> *"No need to do anything. That's why it's called ZTP. Whatever devices come here from today onward, every device will get the same settings. They are not even touching it — they just need to log in."*

### The one condition

> *"As long as you leave this policy here. **If you delete it, it doesn't work.**"*

This is why he deleted the **devices** at the end of class but kept the **policies**: so the class could re-enrol and watch everything arrive by itself.

### Why companies work this way

> *"That's why the company writes all the policies **first**, and then onboards the devices, and then everything comes automatically."*

> 📘 **Note:** This order is the whole point and it's easy to miss: **policy first, devices second.** Get it backwards — enrol 300 laptops and then start writing policies — and you spend weeks chasing devices that have already been handed to users with the wrong configuration. Do it in the right order and a new starter's laptop configures itself out of the box.
>
> This is also the honest answer to *"what does an endpoint engineer actually do all day?"* They are not installing software on individual machines. **They are writing the policies that install software on every machine.**

---

## Part 20 — Removing the test devices (1:42:40 – 1:44:50)

As promised, the instructor cleaned up.

**Two ways to unenrol:**

| From | How |
|---|---|
| **The admin side** | **Devices → All devices → select → Bulk device actions → Delete** |
| **The user side** | **Company Portal app → Devices → your device → Sign out / Remove** |

He read the warning aloud (quoted in Part 15), deleted all the iPhones, and the phones showed **"Device removed"** notifications. The pushed apps went with them.

> *"But I'm not deleting the policies, because we can practise. Maybe we can kick the devices out, re-enrol, and check that everything comes automatically."*

He kept **Ram's** device, who had only just been given a licence and hadn't had a turn.

> 📘 **Note:** He mentions *"we need to write the rollback policy"* in passing, and it's worth explaining, because it's a genuine Intune gotcha. **Removing a configuration profile does not always undo what it did.** Some settings revert when the profile is removed; others stay as they were last set. The camera, for instance, is restored when management is removed — but you cannot rely on that being true for every setting.
>
> So when you need to **reverse** a policy, the reliable method is to **set the value back explicitly** (set "Allow camera" to **Allowed**, push it, confirm) rather than deleting the profile and hoping. The industry term for this is **lack of tattoo-free removal** — settings that "tattoo" the device and persist.

---

## Part 21 — Windows enrollment settings (1:44:50 – 1:51:00)

> *"This is all about iPhone, and the same process for Android, Mac and iPad. A little bit different for Windows."*

**Where:** **Devices → Windows → Enrollment.**

### Automatic enrollment

He turned on **automatic enrollment**, so a Windows device that joins Entra ID enrols in Intune by itself. No certificate, no approval from anyone — *"it's not getting approval from Apple, because this is a Windows device."*

### CNAME validation

Under **CNAME validation** you type the company domain (`jobforit.online`) and Intune tests whether the DNS record is in place.

> 📘 **Note:** This is a **convenience** feature, not a requirement, and the video doesn't say so. The CNAME record (`enterpriseregistration` pointing at Microsoft) means a user can type just their email address during setup and Windows finds the right tenant. Without it, enrollment still works — the user just has to enter the full server address. Worth knowing so a student doesn't treat a failed CNAME check as a blocker.

### Device enrollment limit

**Devices → Enrollment → Device limit restrictions.**

- **Default: 5 devices per user**
- *"Most companies will give you one or two, because they give you a laptop and you can only log into that device."*
- He set it to **3**

> *"If they give you one laptop and they write this, if you try to log into another device, you cannot."*

### Co-management

The tab for running **Intune and Configuration Manager (SCCM) together**, deciding which product owns which workload. This is the real-world halfway state mentioned back in Part 1.

### Device platform restrictions ⭐

**Devices → Enrollment → Device platform restrictions.** For each platform you set:

- **MDM: allow or block**
- **Minimum and maximum OS version**
- **Personally-owned devices: allow or block**

The instructor's take on the last one:

> *"Most companies are not allowing personally-owned devices. They only use business devices. If they give you a laptop, what is the purpose of using a personal device? But if somebody says 'we're not giving a laptop, use your own device', then you need to allow this. Nowadays I think every company gives you a laptop — those who get the job will get a brand-new laptop."*

> 📘 **Note:** True for office-based staff, less true elsewhere. **BYOD is still very common** for phones, for contractors, for frontline and retail staff, and across much of healthcare and education. That's exactly the case **app protection policies** (Part 18) exist for. The clean split in practice is: **company-owned laptops get full MDM; personal phones get MAM.**

### Windows Hello for Business

**Devices → Enrollment → Windows Hello for Business.** The instructor went through it:

| Setting | What he said |
|---|---|
| **PIN** | Minimum length, uppercase/lowercase/numbers required, expiry |
| **Biometrics** | Allow fingerprint and facial recognition — *"most organisations use biometrics"* |
| **TPM** | Required — the hardware security chip |
| **Security key** | Allow a physical USB key |
| **Phone sign-in** | Allow signing in with a phone |

His view on PINs:

> *"PIN is very risky, but if you want to make it strong: PIN length 8, uppercase required, lowercase required, numbers required, expire after 4 months — then it's OK. Otherwise risky. Only four or six numbers is very risky, but put the lockout option."*

> ⚠️ **Correction / clarification:** A Windows Hello PIN is **not** as weak as it sounds, and the reason is worth teaching because it's a good interview answer.
>
> A password travels to a server and can be stolen, phished or replayed from anywhere in the world. A **Windows Hello PIN never leaves the device** — it unlocks a private key held in the **TPM**, the hardware security chip. A stolen PIN is useless without the physical machine, and the TPM locks out after a few wrong attempts in hardware.
>
> So **a 6-digit Hello PIN with TPM is stronger in practice than an 8-character password**, because the attack that matters — remote credential theft — doesn't work against it. This is the whole basis of Microsoft's passwordless strategy.
>
> The instructor's advice to add complexity and lockout isn't wrong, it's just solving a smaller problem than he thinks. The important setting on that page is **require TPM**.

### Backup and restore

Available, but *"not required in Windows — we can create a backup, but you need to pay extra and the storage will go up."*

---

## Part 22 — Windows Autopilot ⭐ (1:51:00 – 1:59:00)

### The problem, set up properly

> *"Let's suppose my university, CQ University, buys 600 Windows laptops. Do you think we need to go and manually add all these devices to Intune? It's possible, but it's too time-consuming."*

Then he proved it by timing the manual process, which is the best teaching move in the class.

### The manual enrollment, done live

He opened a **Windows VM** (taking a snapshot first — good practice) and enrolled it by hand:

**Settings → Accounts → Access work or school → Connect → sign in with the work account.**

**First attempt failed.** The machine was already joined to another tenant from a previous class.

> *"This device is already in another domain. You need to kick it out from that company — disconnect. **You cannot take one device to two companies.**"*

He disconnected, reconnected to the right tenant, signed in, and the device joined **Entra ID** and enrolled in **Intune**. Then signed out and back in. A few minutes later the device appeared in **Devices → Windows**, which had been zero.

> *"This is the process to onboard **one** device. And if you have 600,000 devices, it's time-consuming."*

### The Entra vs Intune discovery

This is the clearest moment in the class and the instructor spotted it himself.

He opened **portal.azure.com → Entra ID → Devices** and found **16 devices** from previous classes. But **Intune showed almost none**.

The reason: **MDM = None** on all 16.

> *"We onboarded these devices, but they're not managed, because at that time we didn't have the licence. We cannot install software, we cannot restart, we cannot update. **You cannot do anything if you don't have this licence.** Now we have a licence."*

> 📘 **Note:** This deserves to be a whole teaching point, because it's the most commonly confused pair in the whole subject:
>
> | | **Entra ID join** | **Intune enrollment** |
> |---|---|---|
> | Gives you | **Identity** — the device has a company account, SSO works | **Management** — policy, apps, compliance, remote actions |
> | Needs an Intune licence | ❌ No | ✅ **Yes** |
> | Where you see it | Entra portal → Devices | Intune → Devices |
> | Shows **MDM = None**? | Yes, if not also enrolled | No |
>
> **"The device is joined but I can't manage it"** is a real ticket, and **MDM = None** in the Entra device list is where you confirm the diagnosis. Usually the cause is a missing licence or automatic enrollment being switched off.

### What Autopilot actually does

**Devices → Enrollment → Windows Autopilot → Devices → Import.**

1. You buy devices from a vendor — Dell, HP, Lenovo.
2. The vendor supplies a **CSV** of **serial numbers**, with hardware hash, manufacturer and model. (Or they register the devices for you directly.)
3. You **import that CSV** into Intune.
4. The devices are now **known to the company before they're even unboxed**.
5. The user switches a new laptop on, connects to Wi-Fi, signs in — and it configures itself.

> *"Then when the device comes to your hand, it automatically gets all the settings. Instead of manually onboarding, you get a list of devices — Dell will give you all the serial numbers in a CSV with manufacturer and model number — and you just insert those."*

> ⚠️ **Reminder:** From here to the end of the class the instructor says **"Copilot"** several times when he means **"Autopilot"** — *"if you have hundreds of devices you need to go with the Copilot"*. See the correction in Part 1. **Autopilot** is device provisioning. **Copilot** is AI. They have nothing to do with each other.

---

## Part 23 — Deployment profiles and OOBE (1:59:00 – 2:02:00)

**Devices → Enrollment → Windows Autopilot → Deployment profiles → Create profile.**

### What OOBE is

The instructor asked the class and most didn't know, though he'd covered it in the Windows Server course.

**OOBE — Out-of-Box Experience** — is the setup wizard the first time a new Windows machine starts:

- Which **language**?
- Which **country / region**?
- Add another **keyboard**?
- Connect to **Wi-Fi**?
- Accept the **licence terms**
- Create or sign in to an **account**

An Autopilot deployment profile decides **how much of that the user sees**.

### The two deployment modes ⭐

| Mode | What happens | Used for |
|---|---|---|
| **User-driven** (the default) | The user still picks language, region, keyboard and Wi-Fi, then signs in with their work account. Everything after that is automatic. | **Normal staff laptops** |
| **Self-deploying** | **The user picks nothing.** You pre-set the region and language in the profile, and the device configures itself with **no user interaction at all**. | **Kiosks, shared devices, digital signage, meeting-room PCs** |

The instructor configured a self-deploying profile:

| Setting | Value |
|---|---|
| **Region** | Australia (AU) |
| **Language** | English (Australia) |
| **Automatically configure keyboard** | Yes |
| **Device name template** | A pattern that names each device automatically |

> *"For all devices, they don't even need to touch — not the region, not the language. How easy is this?"*

### Device name template

Rather than naming 600 laptops by hand, you give a pattern — something like `CQU-%SERIAL%` — and each device names itself from its own serial number.

### Enrollment Status Page

> *"You can check the status page, whether the device is enrolled or not."*

> 📘 **Note:** The **Enrollment Status Page (ESP)** is more useful than that one line suggests, and it's a good thing for a student to know about. It's the screen the user sees **during** Autopilot — *"Setting up your device… installing apps… 3 of 7"* — and it can be configured to **block the user from reaching the desktop until the required apps and policies have finished installing**.
>
> Without it, the user reaches a desktop that looks ready but is still installing things in the background, calls the helpdesk because Word is missing, and the helpdesk tells them to wait. With it, they see honest progress and don't call at all. It turns a support ticket into a progress bar.

---

## Part 24 — Windows device actions (2:02:00 – 2:05:35)

The Windows VM appeared in Intune as **BPC**. The instructor demonstrated remote management on it.

### Renaming a device remotely

**Devices → Windows → [device] → Properties → rename** to `BinodITPC`, then **Restart**.

A few minutes later, without him touching the machine, it restarted and came back with the new name.

> *"Who pushed this restart button? Not from here — from Intune."*
> *"I didn't touch the device. Did I touch the device? No. I did everything from here."*

### The available actions on Windows

| Action | Notes |
|---|---|
| **Sync** | Force a check-in |
| **Restart** | Reboot remotely |
| **Rename** | As demonstrated |
| **Remote lock** | Lock the screen |
| **Reset / Wipe** | Factory reset |
| **Autopilot reset** | Reset **but keep the device enrolled** — the next user gets a clean machine that's still managed |
| **Quick scan / Full scan** | Run Microsoft Defender antivirus remotely |
| **Fresh start** | Reinstall Windows, removing manufacturer pre-installed software |
| **Remote assistance** | See the screen (needs Remote Help) |
| **Collect diagnostics** | Pull logs from the device |

> 📘 **Note:** **Autopilot reset** is the one worth remembering, because it answers a real question: *"someone left, their laptop is going to a new starter, what do I do?"* A full wipe means the device has to be enrolled from scratch. **Autopilot reset** removes the user's data, apps and settings, **keeps the device registered and managed**, and the next person signs in to a freshly configured machine. It's the device equivalent of the offboarding procedure from class 2.

### The Company Portal on Windows

> *"For your easiest one, always use the Company Portal. If you use the Company Portal, you can see all the activity."*

The Windows Company Portal shows managed devices, available and installed apps, support contact details, and a **Sync** button — the same as on iOS.

> *"Whatever I did for the Apple, the same for Windows. 100% the same process. But over here it's flexible — you're not losing anything."*

---

## Part 25 — Windows configuration: blocking downloads in Edge (2:05:35 – 2:10:25)

A clean before-and-after demonstration.

### Creating the policy

**Devices → Windows → Configuration → Create → New policy → Windows 10 and later → Settings catalogue.**

Search for **Edge**, find the Microsoft Edge section, and set **Allow download restrictions** → block.

Assigned to the device, and also available **per user**:

> *"Even if you want to block per user, not only the device — then anywhere they're logged in, on another device, they're blocked."*

### The test

**Before the sync:** he opened Edge and downloaded Notepad++. It worked. *"You can do it now, because I haven't synced."*

**Then he synced** — from the Company Portal, and also from **Devices → Windows → [device] → Sync**.

**After the sync:** he tried the same download again.

> *"See — **blocked.**"*

> 📘 **Note:** This before-and-after structure is the best way to teach any policy, and worth copying when the student practises. **Test it first, apply the policy, sync, test again.** Without the "before", a student can't tell the difference between a policy that worked and a thing that was never possible. It's also exactly how you'd verify a change in a real job, and how you'd prove it to an auditor.

---

## Part 26 — Blocking websites in Edge, and what's next (2:10:25 – 2:13:03)

### URL blocking

Same place: **Configuration → Windows 10 and later → Settings catalogue →** search **Edge →** find **URL blocklist** (and **URL allowlist**).

He added:

- `facebook.com`
- `tiktok.com`
- `youtube.com`
- `instagram.com`

And again noted you can target **user** or **device**:

> *"You can implement it on the device, but if you implement it for the user, it works in both places."*

### The sync wait, one more time

The policy didn't apply immediately. He synced from the Company Portal, synced from the console, and mentioned `gpupdate /force` as the on-premises Group Policy equivalent.

> *"It takes a little bit of time… it's coming… but after a certain time it will work. Maybe if you come tomorrow it will work."*

> 📘 **Note:** Two honest caveats about URL blocking that the class ran out of time for:
>
> 1. **This only blocks Microsoft Edge.** A user who installs Chrome or Firefox walks straight around it. Real web filtering is done at the **network or DNS level**, or with a cloud security product — not in one browser's settings. Edge URL blocking is a useful layer, not a wall. (Note the irony: the class deployed **Firefox** to every iPhone an hour earlier.)
> 2. **Blocking social media is a policy decision, not a technical one.** Whether to do it belongs to HR and management, with a written acceptable-use policy behind it. IT implements that decision; IT doesn't make it. A student who says that in an interview sounds considerably more senior than one who just knows which checkbox to tick.

### What's next

> *"Tomorrow we'll wrap up this one, and then we'll discuss a little bit about SharePoint and Teams."*

---

## Quick reference: where each setting lives

**Intune admin center — intune.microsoft.com**

### Devices

| Task | Path |
|---|---|
| See every managed device | Devices → All devices |
| Count by platform | Devices → Overview |
| **Apple MDM Push Certificate** | Devices → iOS/iPadOS → Enrollment → Apple MDM Push Certificate |
| Android enrollment (Google connection) | Devices → Android → Enrollment |
| **Windows automatic enrollment** | Devices → Windows → Enrollment |
| **Device enrollment limit** (default 5) | Devices → Enrollment → Device limit restrictions |
| **Allow or block personal devices** | Devices → Enrollment → Device platform restrictions |
| **Windows Hello for Business** | Devices → Enrollment → Windows Hello for Business |
| **Co-management** (with SCCM) | Devices → Windows → Enrollment → Co-management settings |
| **Compliance policy** | Devices → [platform] → Compliance policies → Create policy |
| **Configuration profile** | Devices → [platform] → Configuration → Create → New policy |
| **Windows Autopilot** — import serial numbers | Devices → Enrollment → Windows Autopilot → Devices → Import |
| **Autopilot deployment profile** | Devices → Enrollment → Windows Autopilot → Deployment profiles |
| **Enrollment Status Page** | Devices → Enrollment → Windows Autopilot → Enrollment Status Page |
| **Bulk actions** (sync, restart, retire, wipe, delete) | Devices → All devices → select → Bulk device actions |
| **Custom notification** | Devices → Send custom notification |

### A single device

| Task | Path |
|---|---|
| Personal vs **corporate** ownership | [device] → Properties → Device ownership |
| **IMEI**, storage, battery, carrier | [device] → Hardware |
| Every installed app | [device] → Discovered apps |
| Which compliance policies it passes | [device] → Device compliance |
| Which profiles applied, and the result | [device] → Device configuration |
| **Rename / Sync / Restart / Remote lock / Remove passcode / Retire / Wipe / Delete** | Buttons across the top of [device] → Overview |
| **Autopilot reset** (Windows) | [device] → Overview → Autopilot reset |

### Apps

| Task | Path |
|---|---|
| **Deploy an app** | Apps → [platform] → Add → choose app type |
| **App protection policy** (MAM) | Apps → App protection policies → Create policy |
| App configuration | Apps → App configuration policies |

### Elsewhere

| Task | Path |
|---|---|
| **Create a security group** for targeting | Microsoft 365 admin center or Entra ID → Groups → New group → **Security** |
| Check whether a device is **Entra-joined but not managed** | portal.azure.com → Entra ID → Devices → look at the **MDM** column |
| A user's licence | Microsoft 365 admin center → Users → Active users → [user] → Licenses and apps |
| A user's role | Microsoft 365 admin center → Users → Active users → [user] → Account → Roles |
| A user's country | Users → [user] → Edit properties → Country or region |
| Portal display region | Intune → gear icon → Language + region |

### On the device

| Task | Where |
|---|---|
| **Enrol** iOS / Android / macOS | **Intune Company Portal** app → sign in → complete the steps |
| **Force a sync** | Company Portal → Devices → [device] → **Check status** |
| **Unenrol** | Company Portal → Devices → [device] → Sign out / Remove |
| Enrol **Windows** | Settings → Accounts → Access work or school → Connect |
| Leave a tenant (Windows) | Settings → Accounts → Access work or school → Disconnect |

---

## Glossary

| Term | Meaning |
|---|---|
| **Apple MDM Push Certificate** | The certificate that lets Intune manage Apple devices. **One per tenant, one Apple ID, renewed yearly.** |
| **App protection policy** | A **MAM** policy that protects company data **inside an app** — PIN, encryption, no copy-out, selective wipe |
| **Autopilot (Windows Autopilot)** | Provisioning new Windows devices automatically from their serial numbers. **Not** OS updates. |
| **Autopilot reset** | Wipe a Windows device's user data **but keep it enrolled and managed** |
| **Bundle ID** | An iOS app's permanent unique identifier, e.g. `com.facebook.Facebook` |
| **BYOD** | Bring Your Own Device — an employee's personal device used for work |
| **Check-in** | When a device contacts Intune for new policy. Roughly every 8 hours; faster just after enrollment. |
| **Co-management** | Running Intune and Configuration Manager (SCCM) together on the same devices |
| **Compliance policy** | The conditions a device must meet to be considered healthy — e.g. minimum OS, no jailbreak |
| **Conditional Access** | The Entra ID feature that **enforces** compliance by blocking access from unhealthy devices |
| **Configuration profile** | A set of settings pushed to devices — block the camera, set a passcode rule, configure Wi-Fi |
| **Copilot** | Microsoft's **AI** assistant. Nothing to do with device management. |
| **DDM (Declarative Device Management)** | Apple's newer model where the server declares a desired state and the device achieves it |
| **Delete** (device action) | Remove the device's **record from Intune**. Company data may be wiped at next check-in. |
| **Device limit restriction** | How many devices one user may enrol. **Default 5.** |
| **Discovered apps** | The list of applications Intune can see installed on a device |
| **Endpoint** | Any device that connects to the company — laptop, desktop, phone, tablet |
| **Enrollment** | Bringing a device under Intune management |
| **Enrollment Status Page (ESP)** | The progress screen during Autopilot, which can hold the user back until setup finishes |
| **Entra ID join** | Giving a device a company identity. **Different from Intune enrollment** — it alone gives you no management. |
| **IMEI** | A phone's permanent hardware serial number. Used to blacklist a stolen handset. |
| **Intune Company Portal** | The app users install to enrol a device, see company apps, and force a sync |
| **Line-of-business (LOB) app** | A company's own in-house application, uploaded to Intune as an installer |
| **MAM** | **Mobile Application Management** — managing the app and the company data inside it |
| **MDM** | **Mobile Device Management** — managing the whole device |
| **MDM = None** | Seen in the Entra device list. The device has an identity but **is not managed**. Usually a missing licence. |
| **Microsoft Endpoint Manager** | The old umbrella name for Intune plus Configuration Manager. Still appears in the UI and in older documentation. |
| **Not applicable** | A policy result meaning the setting doesn't exist on that device or OS. **Not a failure.** |
| **OOBE** | **Out-of-Box Experience** — the first-run setup wizard on a new Windows device |
| **Personal vs Corporate** | A device's recorded ownership. Affects what inventory Intune shows and which actions are available. |
| **Retire** | Remove **company** data and management, **leaving personal data intact**. The right action for a BYOD phone. |
| **SCCM / Configuration Manager** | The **on-premises** predecessor to Intune. Same job, your own server. |
| **Selective wipe** | Remove **only** company data from an app, leaving everything personal |
| **Self-deploying mode** | An Autopilot profile where the user chooses nothing at all. For kiosks and shared devices. |
| **Settings catalogue** | A searchable list of every available setting, with no structure |
| **Sync** | Force a device to check in now |
| **Template** (configuration) | A pre-built group of related settings, e.g. "Device restrictions" |
| **TPM** | The hardware security chip that holds the keys behind a Windows Hello PIN |
| **Update rings / Windows Update for Business** | The feature that **actually** deploys OS updates and patches from Intune |
| **User-driven mode** | The default Autopilot profile. The user picks region, language and Wi-Fi, then signs in. |
| **Wipe** | **Full factory reset.** For a lost, stolen or reassigned company device. |
| **Windows Hello for Business** | Passwordless sign-in with a PIN, fingerprint, face or security key, backed by the TPM |
| **ZTP (Zero Touch Provisioning)** | Writing the policies first so a new device configures itself when the user signs in |

---

## Practice tasks for the student

Use a **virtual machine** or a **spare device**. Do **not** practise on your own phone.

1. Open **intune.microsoft.com**. Find **Devices** and **Apps** and say out loud which is MDM and which is MAM.
2. Look at **Devices → Overview** and write down the count for each platform.
3. Check whether your tenant has an **Apple MDM Push Certificate**, and note its **expiry date**. Set yourself a calendar reminder 30 days before.
4. Install the **Intune Company Portal** on a phone and enrol it. Write down the four steps, and note which one needs you to leave the app and go into Settings.
5. In the Company Portal, find **Check status**. Use it.
6. Write a **compliance policy** with a minimum OS version **above** your test device's version. Confirm the device shows **Not compliant**. Then lower it and confirm it goes back to compliant.
7. Open your test device's **Hardware** tab. Find the **IMEI**, the free storage, and the battery level.
8. Switch the device from **Personal** to **Corporate** and compare the **Discovered apps** list before and after.
9. Write a **configuration profile** to block the **camera**. Push it. Confirm the camera app disappears. Then **set it back to Allowed**, push again, and confirm it returns. (Don't just delete the profile — see Part 20.)
10. Find the same camera setting **twice**: once through a **template** and once through the **settings catalogue**.
11. Set a **lock screen message** and confirm it appears.
12. Find the **bundle ID** of an app on your phone, then write a policy to **hide** it.
13. **Deploy a free store app** to all devices. Watch the notification arrive.
14. Create an app but **don't assign it**. Look at its status and read what it says. Then assign it.
15. Create a **security group** with **device** members. Target an app at that group only, and confirm other devices don't get it.
16. Send a **custom notification** to your test device.
17. **Rename** the device remotely, then **restart** it, then **sync** it.
18. Write an **app protection policy** that requires a **PIN** to open Outlook. Test it on a device that is **not enrolled**, and explain to yourself why that works.
19. Enrol a **second device** and confirm it picks up every policy and app **without you doing anything**. This is ZTP — prove it to yourself.
20. **Retire** one device and **delete** another. Write down the difference in what happened.
21. Turn on **Windows automatic enrollment**, then set the **device enrollment limit** to 2.
22. Set **device platform restrictions** to **block personally-owned** Windows devices.
23. Configure **Windows Hello for Business** with a PIN policy and **require TPM**.
24. Enrol a **Windows VM**: Settings → Accounts → Access work or school → Connect. Time how long it takes. Then work out how long 600 would take.
25. Open **portal.azure.com → Entra ID → Devices** and look at the **MDM** column. Find any device that is joined but not managed.
26. Create an **Autopilot deployment profile** in **user-driven** mode, then another in **self-deploying** mode. Write down the difference a user would see.
27. Write a Windows configuration policy to **block downloads in Edge**. Test the download **before**, sync, and test **after**.
28. Add `facebook.com` to the Edge **URL blocklist**. Confirm it's blocked in Edge — then open the same site in **Chrome** and explain why it still works.

---

## Review / interview questions (with answers)

1. **What is Microsoft Intune?**
   A cloud-based endpoint management service for managing devices and applications remotely, across Windows, macOS, iOS, iPadOS and Android.

2. **What does MDM stand for, and MAM? What's the difference?**
   Mobile Device Management and Mobile Application Management. MDM manages the whole device; MAM manages the application and the company data inside it. MDM manages the box, MAM manages the data in the box.

3. **What's the difference between SCCM and Intune?**
   Both are endpoint management tools. **SCCM is on-premises** and needs your own server and SQL database; **Intune is cloud-based** with nothing to install. Running both together is called co-management.

4. **You're asked in an interview whether you know SCCM, and you don't. What do you say?**
   "I know it theoretically but I've worked practically in Intune. They do the same job, so I'd pick it up quickly."

5. **What can't Intune do?**
   Anything to do with hardware — RAM, cables, batteries. It also needs the device powered on and connected to the internet, and it can't help a machine that won't boot.

6. **What is Zero Touch Provisioning?**
   Writing all the policies and app assignments before devices are issued, so a new starter just signs in and everything arrives automatically.

7. **What's the difference between Autopilot and Copilot?** ⭐
   **Autopilot** provisions new Windows devices automatically from their serial numbers. **Copilot** is Microsoft's AI assistant. They're unrelated. And neither deploys monthly OS updates — that's Update rings / Windows Update for Business.

8. **Why do you need an Apple MDM Push Certificate, and what are the rules?**
   Apple controls Apple devices, so the company has to be granted authority to manage them. One certificate per tenant, created and renewed with the **same Apple ID**, renewed **every year**.

9. **What happens if the Apple certificate expires?**
   Every enrolled Apple device stops being manageable and has to be re-enrolled by hand. Use a shared company Apple ID and set a reminder before expiry.

10. **How does a user enrol an iPhone?**
    Install the **Intune Company Portal** from the App Store, sign in with the work account, and complete the four steps — including installing the management profile from the iPhone's **Settings**.

11. **What is a compliance policy?**
    The conditions a device must meet to be trusted — minimum OS version, not jailbroken, passcode required, encryption on.

12. **A device is marked non-compliant. What actually happens?** ⭐
    On its own, nothing — it's just a report. Compliance is enforced by pairing it with **Conditional Access** in Entra ID, which blocks non-compliant devices from reaching company data.

13. **What's the difference between Retire, Wipe and Delete?** ⭐
    **Retire** removes company data and management and leaves personal data alone. **Wipe** is a full factory reset. **Delete** removes the record from Intune, and company data may be wiped at the device's next check-in.

14. **An employee resigns and their work email is on their personal phone. What do you do?**
    **Retire** the device, or do a **selective wipe** if it's managed by app protection only. Never wipe a personal phone.

15. **A phone is stolen. What do you do?**
    **Wipe** it immediately. The device is worth a few hundred dollars; the data is worth far more. Also note the IMEI from the Hardware tab for the carrier and the police.

16. **You push a policy and nothing happens. What are the first two things you check?**
    Whether the policy is **assigned**, and whether the device has **checked in**. Devices check in roughly every 8 hours; force it with Sync, or Check status in the Company Portal.

17. **A policy shows "Not applicable" on a device. Has it failed?**
    No. It means the setting doesn't exist on that device or OS version.

18. **Which group type do you use to target Intune policies at devices?**
    A **security group**. Not a Microsoft 365 group, not a mail-enabled security group, not a distribution list.

19. **When would you put devices in a group rather than users?**
    Device groups for device configuration, compliance and required apps — the policy follows the hardware. User groups for app protection and available apps — the policy follows the person.

20. **What are the app types in Intune?**
    Store app, web link, line-of-business (the company's own software), and Microsoft 365 apps.

21. **How do you deploy the company's own in-house Windows application?**
    As a **line-of-business app**. Package it with the Win32 Content Prep Tool into a `.intunewin` file, then supply the install command, uninstall command and a detection rule.

22. **What is a contractor's situation, and how do you handle their personal phone?** ⭐
    They'll read work email on their own device but won't let you manage it. Use an **app protection policy** (MAM without enrollment): a PIN on the work app, no copy-out of company data, and a selective wipe of company data at the end of the contract. Their phone is never managed.

23. **What's the difference between Entra ID join and Intune enrollment?** ⭐
    Entra ID join gives the device an **identity** and SSO. Intune enrollment gives you **management** and needs an Intune licence. A device showing **MDM = None** in Entra is joined but unmanaged.

24. **How many devices can a user enrol by default?**
    Five. Most companies reduce it to one or two.

25. **How would you onboard 600 new laptops?**
    **Windows Autopilot.** Import the serial numbers from the vendor's CSV, create a deployment profile, and the devices configure themselves when first switched on.

26. **What is OOBE, and what's the difference between user-driven and self-deploying?**
    The Out-of-Box Experience is the first-run setup wizard. **User-driven**: the user picks region, language and Wi-Fi, then signs in. **Self-deploying**: the user chooses nothing — used for kiosks and shared devices.

27. **What does the Enrollment Status Page do?**
    Shows setup progress during Autopilot and can block the user from the desktop until required apps and policies have installed.

28. **A laptop needs to go to a new starter. Full wipe or Autopilot reset?**
    **Autopilot reset** — it removes the previous user's data but keeps the device enrolled and managed, so the next person signs in to a configured machine.

29. **Why is a 6-digit Windows Hello PIN not as weak as it looks?**
    It never leaves the device. It unlocks a private key in the **TPM**, so it's useless to a remote attacker, and the TPM locks out after repeated failures.

30. **You block facebook.com in Edge. Is the company protected?**
    Not really. It only covers Edge — Chrome or Firefox would bypass it. Real web filtering happens at the network or DNS level. And whether to block social media at all is an HR and management decision, not an IT one.

31. **Can one device be joined to two companies?**
    No. You must disconnect it from the first tenant before joining the second.

32. **What's the correct order: write policies or enrol devices?**
    **Policies first.** Then devices inherit everything automatically when they enrol. That's the whole point of zero touch.

---

*End of class 3 notes. Next class: finishing Windows in Intune, then SharePoint and Teams.*
