# Microsoft 365 for IT Support
## Part 1 — Getting Started: The Suite, Licences, Domains, Users, Outlook and Admin Roles

---

## Preface

This book is written for someone starting a career in **IT support**. It assumes no earlier knowledge of Microsoft 365. It is based on the first class of a Microsoft 365 course and explains each topic in more depth, the way a textbook would.

Microsoft 365 is one of the most useful skills an IT support engineer can have. Almost every small and medium business, and many large ones, run their email, files, meetings, user accounts and devices on it. As the course instructor put it: *"If you know only this one, you can get a job."*

### How this book is organised

Each chapter contains:

- **What you will learn:** the goals of the chapter.
- **The explanation:** the main content, in plain language.
- 💡 **Explain it like this:** simple analogies you can use when teaching.
- 🛠️ **Hands-on:** step-by-step tasks to do in the Microsoft 365 admin center or Outlook.
- 🏢 **In the real world:** how the topic shows up in an actual IT job.
- 🎯 **Interview corner:** what employers ask and how to answer.
- ✅ **Check your understanding:** questions, with answers at the end of the chapter.

### A note on the examples

This book uses the fictional company **Contoso** with the domain **contoso.com**. Microsoft uses the same example company in its own documentation. In the class, the practice domain was **jobforit.online**, so a user there is `firstname@jobforit.online` instead of `firstname@contoso.com`.

Microsoft often renames products and moves menu items. Prices change too. The screens you see may look slightly different from the ones described here, but the ideas stay the same.

---

## Contents

1. [Introduction to Microsoft 365 and the Cloud](#chapter-1--introduction-to-microsoft-365-and-the-cloud)
2. [The Services Inside Microsoft 365](#chapter-2--the-services-inside-microsoft-365)
3. [Identity, Single Sign-On and Business vs Personal Accounts](#chapter-3--identity-single-sign-on-and-business-vs-personal-accounts)
4. [Microsoft 365 Licensing](#chapter-4--microsoft-365-licensing)
5. [Your Tenant: Trials and the Admin Center](#chapter-5--your-tenant-trials-and-the-admin-center)
6. [Domains and DNS](#chapter-6--domains-and-dns)
7. [Onboarding Users](#chapter-7--onboarding-users)
8. [Signing In and Multi-Factor Authentication](#chapter-8--signing-in-and-multi-factor-authentication)
9. [Supporting Users: Troubleshooting Sign-In Problems](#chapter-9--supporting-users-troubleshooting-sign-in-problems)
10. [Outlook Everywhere: Web, Desktop and Mobile](#chapter-10--outlook-everywhere-web-desktop-and-mobile)
11. [Everyday Outlook Tasks: Signatures, Automatic Replies and Rules](#chapter-11--everyday-outlook-tasks-signatures-automatic-replies-and-rules)
12. [Admin Roles and Least Privilege](#chapter-12--admin-roles-and-least-privilege)
13. [Your Career: Putting It All Together](#chapter-13--your-career-putting-it-all-together)

Appendices
- [A. Quick Reference: URLs and Menu Paths](#appendix-a--quick-reference-urls-and-menu-paths)
- [B. Glossary](#appendix-b--glossary)
- [C. Lab Workbook](#appendix-c--lab-workbook)

---

# Chapter 1 — Introduction to Microsoft 365 and the Cloud

### What you will learn
- What Microsoft 365 is and why businesses use it
- What "the cloud" and "SaaS" mean
- Why companies are moving away from owning their own servers

## 1.1 What is Microsoft 365?

**Microsoft 365** is a **complete, cloud-based business suite**. A *suite* is a collection of products sold together as one package. Microsoft 365 combines the tools a business needs to run its daily work:

- business email
- telephone calls, video meetings and chat
- user accounts and passwords
- management of laptops, phones and apps
- file storage and sharing
- security
- office applications like Word, Excel and PowerPoint

Before cloud services, a company had to buy a separate product for each of these, often from different vendors. It also had to run its own servers in a back room. With Microsoft 365, the company gets all of it from **one place**, with **one bill**, **one admin portal**, and **one username and password** for each staff member.

> 💡 **Explain it like this:** Microsoft 365 is like a **big shopping centre**. Instead of driving to ten different shops, you go to one place and find everything: clothes, groceries, electronics, even a food court. A business goes to Microsoft 365 and finds email, phones, storage, security and apps under one roof.

## 1.2 What is "the cloud"?

"The cloud" means **someone else's computers, which you use over the internet**. Microsoft owns huge data centres around the world, full of servers. When you use Microsoft 365, your email and files are stored on those servers, not in your office.

For a business, this has big advantages:

- **No hardware to buy.** No servers, no server room, no special network equipment for email.
- **Work from anywhere.** Staff sign in from a browser at home, in the office or on the road.
- **Use any device.** A company laptop, a personal computer or a phone.
- **No maintenance.** Microsoft handles power, cooling, hardware failures, updates and backups of the infrastructure.
- **Pay as you go.** Pay a monthly fee per user. Add users when you hire and remove them when people leave.

> 💡 **Explain it like this:** Think about how people live today. You don't need to buy a car to get to the airport, because you book an **Uber**. You don't buy a house for a holiday, you rent an **Airbnb**. You don't buy a Lamborghini, but you can **rent one for a day**. Renting instead of owning is the idea behind the cloud.
>
> Or: *"If you have the money, why cook at home? Go to a restaurant."* A restaurant must also follow **food-safety rules**, so it's often safer than your own kitchen. In the same way, Microsoft has more security engineers than any single company could hire.

## 1.3 SaaS: Software as a Service

Cloud services come in three main types:

| Model | What you rent | What you still manage | Example |
|---|---|---|---|
| **IaaS**: Infrastructure as a Service | Virtual servers, storage, networks | Operating system, apps, data | Azure Virtual Machines |
| **PaaS**: Platform as a Service | A ready platform to run your own code | Your application and data | Azure App Service |
| **SaaS**: Software as a Service | A **finished application** | Only your users, settings and data | **Microsoft 365**, Gmail |

Microsoft 365 is **SaaS**. You don't install servers or manage operating systems. You **rent the finished software** and use it. The IT administrator's job is to manage **users, licences, permissions, settings and data**.

## 1.4 Microsoft 365 or Office 365?

You will hear both names. **Office 365** is the **older name**. **Microsoft 365** is the **newer name**, and it added extra features such as more security and device management. For everyday work and in job interviews, **treat them as the same thing**. If an interviewer asks *"Do you have Office 365 experience?"*, the answer is yes.

> 🎯 **Interview corner:** *"What is Microsoft 365?"*
> **Good answer:** "Microsoft 365 is Microsoft's cloud-based business suite, a SaaS product. It gives an organisation business email through Exchange Online, calls and meetings through Teams, identity through Entra ID, device management through Intune, storage in OneDrive and SharePoint, security, and the Office apps, all managed from the Microsoft 365 admin center."

### ✅ Check your understanding
1. In one sentence, what is Microsoft 365?
2. What does SaaS stand for? Give an example other than Microsoft 365.
3. Name three advantages of the cloud for a business.
4. Is Office 365 different from Microsoft 365?

**Answers:** (1) A complete cloud-based business suite that gives an organisation email, communication, identity, device management, storage, security and apps from one place. (2) Software as a Service, e.g. Gmail or Salesforce. (3) Any three of: no hardware to buy, work from anywhere, any device, no maintenance, pay per user. (4) No, it's the old name for the same product.

---

# Chapter 2 — The Services Inside Microsoft 365

### What you will learn
- The main services in Microsoft 365 and what each one does
- Which business need each service meets
- The one thing Microsoft 365 can't provide

## 2.1 Starting from business needs

A good way to learn Microsoft 365 is to ask: **"What does every organisation need?"** Then find the Microsoft 365 service for each need.

| Every business needs… | Microsoft 365 service |
|---|---|
| Business email | **Exchange Online** (read with **Outlook**) |
| A telephone system, meetings, chat, remote support | **Microsoft Teams** |
| Usernames and passwords, security for sign-in | **Microsoft Entra ID** |
| Management of laptops, phones and apps | **Microsoft Intune** |
| Somewhere to store files | **OneDrive** and **SharePoint** |
| Protection against attacks | **Microsoft Defender** and other security tools |
| Word processing, spreadsheets, presentations | **Microsoft 365 apps** (Word, Excel, PowerPoint…) |

The sections below explain each one.

## 2.2 Exchange Online: business email

**Exchange Online** is Microsoft's **cloud email server**. It stores each user's **mailbox** (inbox, sent items, calendar and contacts) and handles sending and receiving email.

**Outlook** is the **program people use to read their email**. It comes as a website (outlook.office.com), a desktop app and a mobile app.

> 💡 **Explain it like this:** Exchange Online is the **post office**. It receives, stores and sends the mail. Outlook is the **letterbox and reading glasses**, the tool you use to see your mail.

**Minimum requirement:** if you ask what the *minimum* thing is that every organisation needs, the answer is **business email**. It is usually the first service a company sets up.

## 2.3 Microsoft Teams: communication and remote support

**Teams** is Microsoft's hub for communication. The business version includes:

- **Chat** with colleagues, one-to-one or in groups
- **Audio and video calls** and **online meetings** (with recording)
- **Screen sharing** and **file sharing**
- **Remote control**, so IT can take control of a user's screen to help them
- **Telephone system (VoIP)**: a business can have real phone numbers that ring in Teams. Someone can call from another country and the call rings on your computer or phone.

**VoIP** stands for **Voice over Internet Protocol**, which means phone calls carried over the internet instead of traditional phone lines.

With Teams, a business doesn't need a separate meeting tool like Zoom or a separate phone system.

## 2.4 Microsoft Entra ID: identity management

Every company needs **usernames and passwords**. Staff use them to sign in to their computers, their email and every other system.

In traditional offices this was handled by **Active Directory**, a Microsoft server installed on-site. The **cloud version** is **Microsoft Entra ID** (formerly called *Azure Active Directory* or *Azure AD*).

In Entra ID an administrator can:

- **create users** with usernames and passwords
- set up **multi-factor authentication (MFA)**
- create **groups** of users
- grant **roles and permissions**

Entra ID is the **foundation** of Microsoft 365. Every other service asks Entra ID *"Who is this person, and are they allowed in?"*

## 2.5 Microsoft Intune: device and app management

**Intune** lets IT **manage devices and applications from the cloud**:

- **MDM (Mobile Device Management):** managing the **whole device**, such as a company laptop or phone.
- **MAM (Mobile Application Management):** managing only the **company apps and data** on a device, which is useful when staff use their own phones.

With Intune, an IT person can **onboard** iPhones, Android phones and Windows laptops. From **one dashboard, anywhere in the world**, they can **install and uninstall software**, **restart** computers, **push updates** and **apply policies**. The device only needs power and an internet connection. You don't need to be physically there.

## 2.6 OneDrive and SharePoint: storage

| | **OneDrive** | **SharePoint** |
|---|---|---|
| Purpose | **Personal** storage for each user | **Business / team** storage |
| Think of it as | "**My** files" | "**Our** files" |
| Example | Your own drafts and documents | The Finance department's shared folder, the company intranet |

Many people already use OneDrive personally. In a company, **SharePoint** is where shared business documents live.

## 2.7 Security

Microsoft 365 includes security tools, mainly **Microsoft Defender** plus identity protections in Entra ID. These can **block suspicious sign-ins**, **stop users signing in from other countries**, **protect against phishing and malware**, and much more.

Detailed security configuration is usually the job of **cybersecurity engineers**, not IT support. This book doesn't cover it. Still, the right licence **gives the organisation these protections automatically**, and cybersecurity is a natural next step once you master Microsoft 365.

## 2.8 Microsoft 365 apps

The familiar Office applications: **Word, Excel, PowerPoint, Outlook, OneNote**, and more. Depending on the licence there are **30+ apps**, including Access, Publisher and Whiteboard. They may be available **in the browser only** or as **downloadable desktop apps**. That depends on the licence (see Chapter 4).

## 2.9 The one thing it can't give you

What does Microsoft 365 **not** provide? **A printer.** You can rent almost anything from the cloud, but you can't rent a printer online. The hardware has to be physically with you. That's why offices and homes still buy printers.

> 🏢 **In the real world:** Because Microsoft 365 covers so much, **one IT support person who knows it well can manage most of a small or medium organisation's IT**. That's why the skill is so valuable.

### ✅ Check your understanding
1. Which service provides business email? Which app do users read it in?
2. What is VoIP, and which Microsoft 365 service provides it?
3. What was Entra ID called before, and what is its on-premises equivalent?
4. What is the difference between MDM and MAM?
5. When would you use OneDrive, and when SharePoint?
6. What can't Microsoft 365 provide?

**Answers:** (1) Exchange Online, read in Outlook. (2) Voice over Internet Protocol, i.e. phone calls over the internet. It's provided by Microsoft Teams. (3) Azure Active Directory (Azure AD). The on-premises equivalent is Active Directory. (4) MDM manages the whole device. MAM manages only company apps and data. (5) OneDrive for personal work files, SharePoint for shared team or department files. (6) A printer.

---

# Chapter 3 — Identity, Single Sign-On and Business vs Personal Accounts

### What you will learn
- What single sign-on means
- How Microsoft 365 relates to Azure
- The difference between business and personal Microsoft accounts

## 3.1 Single sign-on (SSO)

**Single sign-on** means **one username and password gives access to many systems**. In the Microsoft world, one account signs in to Outlook, Teams, OneDrive, SharePoint, the Azure portal and more.

This works because all Microsoft business services use the **same identity system, Entra ID**. If you've created users in **Azure**, the same users exist in **Microsoft 365**. You **don't recreate them**, and policies such as MFA apply everywhere.

> 💡 **Explain it like this:** SSO is like a **hotel key card**. One card opens your room, the gym, the pool and the lift. You don't carry a separate key for each.

## 3.2 Business accounts vs personal accounts

Microsoft offers **free personal** services and **paid business** services. They can look similar, but they are very different.

| | **Personal** (free) | **Business** (Microsoft 365) |
|---|---|---|
| Email address | `name@outlook.com`, `name@hotmail.com` | `name@contoso.com`, **your company's domain** |
| Whose brand is in the address | Microsoft's | Your company's |
| Cost | Free | Paid, per user per month |
| Storage | Small (e.g. 5 GB OneDrive) | Large (e.g. 50 GB mailbox, 1 TB OneDrive) |
| Security features | Basic | Business-grade (MFA policies, Defender, etc.) |
| **Admin panel** | **No**, you can't create other users | **Yes**, IT manages all users centrally |
| Teams | Personal Teams (family and friends) | Business Teams (meetings, phone system, org chat) |

**Business email** is email that uses **your own company name** in the address. It looks professional, and customers trust it. The company owns and controls it, because when someone leaves, their mailbox stays with the company.

How many business accounts can a company create? As many as it needs, even thousands. **It just pays for each user's licence.**

> 🎯 **Interview corner:** *"What's the difference between Outlook.com and Exchange Online?"*
> **Good answer:** "Outlook.com is Microsoft's free personal email service using Microsoft's domain. Exchange Online is the business email server in Microsoft 365. It uses the company's own domain, is centrally managed by IT through the admin center, and has business-grade security and storage."

### ✅ Check your understanding
1. What is SSO? Why does it work across Azure and Microsoft 365?
2. Give two differences between a personal @outlook.com account and a business account.
3. Can a company with 5,000 staff use Microsoft 365 business email?

**Answers:** (1) One username and password for many systems. It works because both use the same Entra ID. (2) Any two: domain name, cost, storage, security, admin panel. (3) Yes. It pays for 5,000 licences on an Enterprise plan (Business plans stop at 300 users).

---

# Chapter 4 — Microsoft 365 Licensing

### What you will learn
- Why licences matter
- The main licence families: Personal, Business, Enterprise, Government, Education, Frontline
- The differences between Business Basic, Standard and Premium
- How to talk about licences in a job interview

## 4.1 Why licences matter

Microsoft 365 is a cloud service, which means **you rent it**. Each user needs a **licence**, a paid subscription that switches services on for them.

**No licence means no services.** A user without a licence exists in Entra ID but has **no mailbox, no Teams, no OneDrive and no Office apps**. When a new staff member can't get email, a missing licence is one of the first things to check.

Choosing the right licence is also a business decision. Too basic, and staff lack tools or security. Too expensive, and the company wastes money.

> Prices below are approximate figures from the class, in Australian dollars. Microsoft changes prices and plan contents regularly, so always check the current offer on Microsoft's website.

## 4.2 Personal and Family: not for business

- **Microsoft 365 Personal:** one person, desktop Office apps, **1 TB** of OneDrive, signed in on up to 5 devices at once. About AUD 159 per year.
- **Microsoft 365 Family:** the same for up to six people. About AUD 179 per year.

These are for **home use only**. They have **no business features**: no company domain, no admin center, no Intune. If a friend asks *"How do I get Word and Excel at home?"*, recommend these.

## 4.3 Business plans: up to 300 users

For organisations with **up to 300 staff**, Microsoft sells three main Business plans.

### Business Basic
- Business **email** (Exchange Online)
- **Storage** (OneDrive, SharePoint)
- **Teams**
- **Web and mobile versions** of Word, Excel and PowerPoint. You use them in a browser, but **you can't download and install them**.
- ❌ No desktop apps, ❌ no Intune, ❌ no advanced security
- About **AUD 9 per user per month**, the cheapest option

### Business Standard
- Everything in Basic
- ➕ **Downloadable desktop apps**: install Word, Excel, PowerPoint and Outlook on the computer
- ❌ Still no Intune, ❌ no advanced security
- About **double** the price of Basic, because the desktop apps are included

### Business Premium ⭐
- Everything in Standard
- ➕ **Microsoft Intune**: device and app management
- ➕ **Advanced security**: Defender for Business, Conditional Access (Entra ID P1), information protection
- The most expensive Business plan, and **the best one**

**Business Premium is what most small and medium companies choose.** Today companies manage their computers from the cloud and need at least basic security, and only Premium includes both. It's the plan used for practice in this course.

| | Basic | Standard | **Premium** |
|---|---|---|---|
| Business email | ✅ | ✅ | ✅ |
| Storage (OneDrive/SharePoint) | ✅ | ✅ | ✅ |
| Teams | ✅ | ✅ | ✅ |
| Web & mobile Office apps | ✅ | ✅ | ✅ |
| **Desktop** Office apps | ❌ | ✅ | ✅ |
| **Intune** (device management) | ❌ | ❌ | ✅ |
| **Advanced security** | ❌ | ❌ | ✅ |
| Max users | 300 | 300 | 300 |

> 💡 **Explain it like this:** Basic is renting a **furnished room**: bed, desk and internet. Standard is the same room **with a TV you can take home**. Premium is the room **with a TV, a security guard and a caretaker** who looks after all your devices.

## 4.4 Enterprise plans: more than 300 users

Organisations with **more than 300 staff** must use **Enterprise** plans:

- **E3**: full apps, email, Intune, identity and compliance features
- **E5**: everything in E3 plus Microsoft's top security, compliance and analytics tools
- The class also mentioned **E7**, the newest and most expensive tier, which includes everything Microsoft offers

These plans are expensive. The class quoted roughly **AUD 85 per user per month for E5** and **AUD 148 for E7**. For a company of 1,000 people, that's over AUD 100,000 **per month** in licences alone. Only large enterprises such as big tech companies, banks and major corporations use them.

## 4.5 Other licence families

| Family | For whom | Examples |
|---|---|---|
| **Government (G)** | Government agencies only. You can't buy them unless you are one. | G3, G5 |
| **Education (A)** | Schools, colleges, universities | A1, A3, A5 |
| **Frontline (F)** | Frontline workers such as hospital staff, police, army, retail and factory workers, who often share devices | F1, F3 |

You don't need to memorise every plan. Microsoft publishes detailed licensing maps, which you can look up when you actually need to buy something.

## 4.6 Licences in the job interview

> 🎯 **Interview corner:** *"Which Microsoft 365 licence did your company use?"*
>
> If you're applying to a **small or regional company**, **don't say "Enterprise E5"**. A small company rarely pays for Enterprise licences, so the interviewer may not believe you.
>
> **Good answer:** "We used **Microsoft 365 Business Premium**. It gave us Exchange Online, Teams, SharePoint and OneDrive, desktop apps, and Intune, which we used to manage all our devices."
>
> Everything in this course is covered by Business Premium, so this answer matches your skills. If you're applying in education, government or a large enterprise, you can mention knowing that those sectors use A, G or E licences.

### ✅ Check your understanding
1. What happens to a user who has no licence?
2. What's the maximum number of users on a Business plan?
3. What does Business Standard add to Business Basic?
4. What does Business Premium add to Business Standard?
5. A company has 800 staff. Which licence family must it use?
6. Which licence should you mention in an interview for a small company, and why?

**Answers:** (1) They have no mailbox, Teams, OneDrive or apps. (2) 300. (3) Downloadable desktop Office apps. (4) Intune and advanced security. (5) Enterprise (E3/E5/E7). (6) Business Premium. It's realistic for a small company and covers Intune and everything else you've learned.

---

# Chapter 5 — Your Tenant: Trials and the Admin Center

### What you will learn
- What a tenant is
- How to get a free Business Premium trial
- How to reach and navigate the Microsoft 365 admin center

## 5.1 The tenant

When an organisation signs up for Microsoft 365, Microsoft creates a **tenant**: the organisation's **own private space in Microsoft's cloud**. It holds all of the company's users, mailboxes, files, licences and settings, separate from every other company.

Every tenant starts with a free domain like **contoso.onmicrosoft.com**. The organisation normally adds its **own domain** (Chapter 6) so that email addresses look like `name@contoso.com`.

## 5.2 Getting a free trial

To practise, you can get a free **Microsoft 365 Business Premium trial**:

1. Search for **"Microsoft 365 Business Premium free trial"** and open Microsoft's page.
2. Click **Try free for one month**.
3. Enter your details, create the admin account and add a **payment card**.
4. When it's finished, you land in the **Microsoft 365 admin center**.

**What the trial gives you:**
- **25 licences** for **one month**, free
- Everything in Business Premium: Word, Excel, PowerPoint, Outlook, Access, Publisher, Teams, OneDrive, SharePoint, email, Intune and security
- The trial can often be **extended**. Look in **Billing → Your products**.

**Important rules:**
- **Each card gets one trial per product.** You can use the same card for an Azure trial and a Microsoft 365 trial, because they are different products.
- **Cancel before the trial ends**, or you'll be charged. **Put a reminder in your calendar a few days before the end date.**

A trial is also available from inside an existing tenant: **Marketplace → All products → Microsoft 365 Business Premium → Start free trial**.

> 🏢 **In the real world:** In a job, the company already has a tenant. IT gives you an account with an **admin role**, and you sign in to the admin center. **Only IT staff get admin access.** Normal users only see their own apps.

## 5.3 The Microsoft 365 admin center

The **admin center** is the main control panel for Microsoft 365. You will use it every day.

- **URL:** **admin.microsoft.com** (it now redirects to **admin.cloud.microsoft**)
- Or go to **office.com**, sign in, and click the **Admin** tile

### Main areas of the admin center

| Menu | What you do there |
|---|---|
| **Home** | Dashboard and shortcuts |
| **Users → Active users** | Create, edit, delete users. Reset passwords, assign licences and roles. |
| **Teams & groups** | Groups, distribution lists, shared mailboxes |
| **Roles** | Give admin permissions to IT staff |
| **Marketplace** | Buy or try licences and products |
| **Billing** | Licences, subscriptions, invoices |
| **Settings → Domains** | Add and verify the company's domain |
| **Health** | Check if Microsoft has a service problem |
| **Admin centers** | Links to specialist portals: Exchange, Entra, SharePoint, Teams, Intune, Security |

> 💡 **Explain it like this:** The **Marketplace** is the **food court** of the shopping centre. Whatever Microsoft sells, you can browse, try and buy it there.

### ✅ Check your understanding
1. What is a tenant?
2. How many licences does a Business Premium trial include, and for how long?
3. What's the URL of the admin center?
4. Where in the admin center do you create users? Where do you add a domain?

**Answers:** (1) An organisation's own private space in Microsoft's cloud. (2) 25 licences for one month. (3) admin.microsoft.com. (4) Users → Active users; Settings → Domains.

---

# Chapter 6 — Domains and DNS

### What you will learn
- What a domain is and where to buy one
- What DNS is and why it matters
- The four DNS records Microsoft 365 needs
- How to connect a domain to Microsoft 365, automatically and manually

## 6.1 Domains

A **domain name** is a company's name on the internet, such as **contoso.com**. For business email, users' addresses end with the company's domain: `anna@contoso.com`.

**Where do you buy one?** From a **domain registrar**, such as **GoDaddy**, **Crazy Domains** or **Namecheap**. Prices vary: some endings like `.online` cost a couple of dollars a year, while `.com` usually costs more.

**Microsoft doesn't sell domain names.** You buy the name somewhere else and then **connect it** to Microsoft 365.

> 💡 **Explain it like this:** Some restaurants don't sell drinks, but they let you **bring your own** and enjoy it there. Microsoft is like that. Buy the domain elsewhere and bring it to Microsoft 365.

## 6.2 What is DNS?

Computers talk to each other using **IP addresses**, numbers like `40.97.120.1`. Humans can't remember numbers like that, so we use names like `facebook.com`.

**DNS (Domain Name System)** is the internet's **translator**. It turns names into the IP addresses computers understand, and stores other information about a domain in **DNS records**.

> 💡 **Explain it like this:** Can you phone someone if you know their **number** but not their **name**? Yes. Can you phone them if you know their **name** but not their **number**? No. The name is only there to help humans. The phone system needs the number. DNS is the **phone book** that finds the number for the name. It's also like an **interpreter** between two presidents who speak different languages.

## 6.3 Why Microsoft asks for DNS records

When you add your domain to Microsoft 365, Microsoft needs **proof that you own it**, and it needs the internet to know that **your email is handled by Microsoft**. By default, Microsoft and your registrar (e.g. GoDaddy) **don't trust each other**. So Microsoft gives you some **DNS records to add at your registrar**. When Microsoft sees them there, it knows the domain is yours.

> 💡 **Explain it like this:** In some government offices you're told: *"Take this form to room 5, get it stamped, and bring it back."* Microsoft gives you a code, you "stamp" it into GoDaddy, and Microsoft checks the stamp.

## 6.4 The four key DNS records

| Record | Name | Purpose | Example value (illustrative) |
|---|---|---|---|
| **TXT** | Text record | **Verifies you own the domain** | `MS=ms12345678` |
| **MX** | Mail Exchange | **Sends and receives email.** Tells the world where to deliver mail for your domain. **Without it, email doesn't work.** | `contoso-com.mail.protection.outlook.com`, priority 0 |
| **CNAME** | Canonical name (an alias) | **Autodiscover**: Outlook automatically finds the right server settings when a user adds their account | `autodiscover` → `autodiscover.outlook.com` |
| **TXT (SPF)** | Sender Policy Framework | **Email protection**: lists which servers may send email for your domain, which stops spoofing | `v=spf1 include:spf.protection.outlook.com -all` |

> The exact values for your domain are shown in the admin center. Always copy them from there, not from a book.

Later you may also meet **DKIM** and **DMARC**, two more email-security records that work together with SPF.

## 6.5 Connecting the domain: step by step

🛠️ **Hands-on: add a domain**

1. Admin center → **Settings → Domains → Add domain**.
2. Type the domain name (e.g. `contoso.com`) and click **Use this domain**.
3. Microsoft detects where your DNS is hosted (e.g. GoDaddy). Choose how to add the records.

**Option A: automatic (recommended)**
4. Choose to let Microsoft add the records, **sign in to your GoDaddy account** when asked, and click **Connect**.
5. Microsoft adds all the records for you. You don't need to touch anything.

**Option B: manual**
4. Microsoft shows a table of records. For each one, note the **Type**, **Host name**, **Value**, **Priority** and **TTL**.
5. In GoDaddy, open your domain → **DNS** → **Add new record**. For example, the MX record:
   - **Type:** MX
   - **Name/Host:** `@` (means "the domain itself")
   - **Value:** copied from Microsoft
   - **Priority:** 0
   - **TTL:** 1 hour
6. **Save**, and repeat for the TXT, CNAME and SPF records.
7. Back in Microsoft 365, click **Continue / Verify**.

**Finishing up**
- Wait for the domain status to become **Healthy**. DNS changes can take anywhere from minutes to a few hours (occasionally up to 48 hours) to spread across the internet. Refresh the page. If it looks stuck, try a private browser window, since your browser may be showing an old cached page.
- **Set the domain as default.** Then new users get `@contoso.com` instead of `@contoso.onmicrosoft.com`.

> ⚠️ **If the domain isn't Healthy, email won't work properly.** Always check this status first when new mailboxes can't receive external email.

### ✅ Check your understanding
1. Does Microsoft sell domain names?
2. What does DNS do?
3. Which record is needed to receive email? Which one proves ownership?
4. What does the autodiscover CNAME do?
5. What does SPF protect against?
6. What are the two ways to add the records?

**Answers:** (1) No. (2) It translates names into IP addresses and stores information about a domain. (3) MX; TXT. (4) Lets Outlook find mailbox settings automatically. (5) Spoofing, i.e. others sending email pretending to be your domain. (6) Automatically, by signing in to the registrar from Microsoft's wizard, or manually, by copying each record.

---

# Chapter 7 — Onboarding Users

### What you will learn
- What onboarding is
- How to create a single user
- How to assign licences, one at a time and in bulk
- How to create many users at once with a CSV file
- How to reset passwords, one at a time and in bulk

## 7.1 What is onboarding?

When a company hires someone, IT must create their account, give them a licence and help them sign in. This is called **onboarding**. It's one of the **most common tasks** in IT support. (The opposite, when someone leaves, is **offboarding**.)

## 7.2 Creating a single user

🛠️ **Hands-on: add a user**

Admin center → **Users → Active users → Add a user**

1. **Basics**
   - **First name**, **last name**, **display name** (how the name appears in email)
   - **Username**, e.g. `anna` @ `contoso.com`. This becomes the sign-in name **and** the email address.
2. **Password settings**
   - **Automatically create a password**: the system makes a random one, or
   - **Let me create the password**: you type one.
   - ✅ **Require this user to change their password when they first sign in.** This makes it a **temporary password**, so only the user will know their real password. Without it, the password is permanent.
3. **Product licences**
   - **The most important step.** Select the country and tick **Microsoft 365 Business Premium**.
   - Without a licence, the user gets **no mailbox**.
4. **Optional settings**
   - **Roles:** leave as **User (no admin center access)** for a normal staff member.
   - **Profile info:** job title, department, office and phone.
5. **Finish**. The admin center shows the username and password. Share them **securely** with the new user.

Your job isn't done yet. **Guide the user** to sign in (Chapter 8) and set up Outlook, Teams and OneDrive.

> 🏢 **In the real world:** Many companies have an onboarding checklist: create the account, assign the licence, add the user to the right groups, prepare the laptop (often with Intune), and hand over the details on the first morning. Being organised and friendly on someone's first day leaves a great impression.

## 7.3 Assigning licences

**One user:** Users → Active users → click the user → **Licenses and apps** → tick the licence → **Save changes**.

**Many users at once:**
1. Users → Active users → **tick all the users**.
2. Click **… (More actions) → Manage product licences**.
3. Choose one:
   - **Assign more**: *adds* the new licence and **keeps** existing ones.
   - **Replace**: **removes** existing licences and gives only the new one.
4. Select **Microsoft 365 Business Premium** → **Save changes**.
5. Check the **Licences** column in the user list to confirm.

## 7.4 Creating many users with a CSV file

If a company hires 50 people, or a college enrols hundreds of students, creating accounts one by one is slow and mistakes are likely. Use **bulk creation with a CSV file**. (A CSV is a simple spreadsheet file with values separated by commas.)

🛠️ **Hands-on: add multiple users**

1. Admin center → **Users → Active users → Add multiple users**.
2. Choose to upload a CSV, then **download the blank CSV file with the required headers** (or the sample file). Always start from Microsoft's template, so the column names are exactly right.
3. Open it in **Excel**. It has columns such as:
   `User name, First name, Last name, Display name, Job title, Department, Office number, Office phone, Mobile phone, Fax, Alternate email address, Address, City, State or province, ZIP or postal code, Country or region`
   Fill in what you need, at least **User name**, **First name**, **Last name** and **Display name**. Delete the example rows.
4. **Build usernames with a formula** instead of typing every address. If the first name is in cell **B2**:
   ```
   =CONCATENATE(B2,"@contoso.com")
   ```
   This joins the first name with the domain, e.g. `anna@contoso.com`. Drag the formula down to fill every row. **Don't forget the "@"**. It's a common mistake.
5. Save the file in **CSV** format.
6. Back in the admin center: **Browse** → select the file → **Next**.
7. **Assign a licence** (e.g. Business Premium) to all of them → **Next** → **Add**.
8. Microsoft shows the results, including temporary passwords. Download or email them to yourself securely.

> Tip: the admin center accepts up to about 250 users per CSV file. For bigger jobs, split into several files or use PowerShell (a later topic).

## 7.5 Resetting passwords

**One user** (the most common helpdesk request, *"I forgot my password"*):
Users → Active users → select the user → **Reset password** → auto-generate or type a new temporary password → keep **"require change at next sign-in"** on → **Reset**.

**Many users at once:**
Users → Active users → **tick several users** → **Reset password** → set **one temporary password** for all → **Reset**. This is useful after a bulk import, or when a whole team needs new passwords.

### ✅ Check your understanding
1. What is onboarding?
2. What makes a password "temporary"?
3. What is the single most important step when creating a user? Why?
4. What's the difference between **Assign more** and **Replace** when managing licences?
5. Write the Excel formula that turns the first name in cell B2 into an email address at contoso.com.
6. How do you reset passwords for ten users at once?

**Answers:** (1) Creating and setting up accounts for new staff. (2) The option that forces the user to change it at first sign-in. (3) Assigning a licence. Without one, the user has no mailbox or apps. (4) Assign more adds a licence and keeps existing ones. Replace removes existing licences and gives the new one. (5) `=CONCATENATE(B2,"@contoso.com")`. (6) Select the ten users in Active users → Reset password.

---

# Chapter 8 — Signing In and Multi-Factor Authentication

### What you will learn
- How a new user signs in for the first time
- What MFA is and why it's required
- How to set up Microsoft Authenticator

## 8.1 The first sign-in

1. Open a browser and go to **outlook.office.com**.
2. Type the **username** (the full email address, e.g. `anna@contoso.com`).
3. Type the **temporary password** from IT.
4. Microsoft asks you to **update your password**:
   - **Current password** = the temporary password
   - **New password** = your own **strong** password
5. Microsoft then says **"More information required"** or **"Let's keep your account secure."** This is **MFA setup**.

## 8.2 What is MFA?

**Multi-Factor Authentication (MFA)** means proving who you are in **more than one way**:

1. Something you **know**: your password
2. Something you **have**: your phone with the Authenticator app
3. (Sometimes) something you **are**: your fingerprint or face

Why does it matter? Passwords are stolen all the time through phishing emails, data breaches and guessing. With MFA, **a stolen password alone is not enough**, because the attacker would also need your phone. Microsoft reports that MFA blocks the vast majority of account-takeover attacks.

Typing a username and password isn't really IT. Anyone can do that, like logging in to Facebook. What makes business sign-in different today is **security, and MFA is required**.

> 💡 **Explain it like this:** A password is your **house key**. MFA is a **guard at the door who calls your phone** to check it's really you. A thief who steals your key still can't get in.

## 8.3 Setting up Microsoft Authenticator

🛠️ **Hands-on: register MFA**

1. On your **phone**, install **Microsoft Authenticator** from the App Store or Google Play. Make sure it's the one **by Microsoft**. There are many other authenticator apps.
2. On the **computer**, click **Next** until a **QR code** is shown.
3. In the app, tap **+ (Add account)** → **Work or school account** → **Scan QR code**. (The other option, **Sign in**, adds the account by signing in on the phone.)
4. Point the **phone's camera** at the QR code on the computer screen. The computer itself doesn't need a camera.
5. Click **Next** on the computer. Microsoft sends a test sign-in, and you **approve it in the app**, usually by typing the number shown on the computer screen.
6. Done. From now on, signing in on a new device asks for approval in the app.

## 8.4 Testing email

Once signed in, **test that email works**:
- Send an email **from a personal Gmail account** to your new business address. If it arrives, **email from the internet reaches the mailbox**, which means the **MX record** is correct.
- **Reply** back to Gmail to check outgoing email.
- Email a **colleague** to check internal email.

### ✅ Check your understanding
1. What is the "current password" on first sign-in?
2. What are the factors in MFA?
3. Which app is used? What are the steps inside the app?
4. Does the computer need a camera to scan the QR code?
5. Why send a test email from Gmail?

**Answers:** (1) The temporary password IT gave you. (2) Something you know, something you have and something you are. (3) Microsoft Authenticator. Tap + → Work or school account → Scan QR code. (4) No, the phone's camera scans the code on the computer screen. (5) To confirm email from outside the organisation arrives, which proves the MX record works.

---

# Chapter 9 — Supporting Users: Troubleshooting Sign-In Problems

### What you will learn
- The most common first-day sign-in problems and how to fix them
- How to check whether a user has registered MFA
- How to make a user register MFA again

## 9.1 Why this chapter matters

When you work in IT, **users will call you when something goes wrong**. First-day sign-in problems are among the most frequent calls. In the class, it took about half an hour to get everyone signed in. Every problem in the table below actually happened.

## 9.2 Common problems and solutions

| Symptom | Likely cause | Fix |
|---|---|---|
| "We couldn't find an account with that username" | **Typo in the username or domain** (e.g. `.com` instead of `.online`) | Check the exact username in Active users and have them type it carefully |
| "Your account is temporarily locked" | **Too many wrong password attempts.** Microsoft locks the account to stop attackers guessing. | Wait a short time, or **reset the password** |
| New password is rejected | Doesn't meet the **password policy** | Use a longer password that mixes upper case, lower case, numbers and symbols |
| User doesn't know the "current password" | Confusion on first sign-in | It's the **temporary password** from IT |
| User signs in but Outlook says there's no mailbox | **No licence**, or the licence was given to the **wrong user** (e.g. two people with similar names) | Check **Licences** on the correct user. Mailbox creation can take a few minutes after licensing. |
| Page shows the wrong account or old errors | **Browser cache** or already signed in as someone else | Use an **Incognito / InPrivate / private window** |
| "Authenticator registration has timed out" | Took too long between steps | Click **Next / Try again**. Have the app open and ready before starting. |
| Phone can't scan the QR code | Camera or focus problem | Choose **"Can't scan image?"** and **type the code** into the app manually |
| Can't find the right app | Installed a different authenticator | Install **Microsoft Authenticator** |
| Locked out of the Authenticator app (forgot app PIN) | — | Delete and reinstall the app. The admin may need to reset the user's MFA (below). |
| User got a **new phone** | The old phone held the MFA registration | Admin resets the MFA method (below) |
| User keeps choosing "Not now" | MFA setup can be **postponed for up to 14 days** | After that it's required. Encourage setting it up straight away. |

## 9.3 Checking a user's MFA registration

🛠️ **Hands-on: view and reset authentication methods**

1. Admin center → **Admin centers → Microsoft Entra** (or go to **entra.microsoft.com** or **portal.azure.com**).
2. **Users** → search for the user → open them → **Authentication methods**.
3. If the user registered MFA, you'll see **Microsoft Authenticator** and the phone name (e.g. "iPhone 13"), and possibly a phone number.
4. **Nothing listed** means they haven't finished MFA setup.
5. **To make them register again** (new phone, broken setup): **delete** the existing method, or use **Require re-register multifactor authentication**. At the next sign-in they'll be asked to set it up again.

You can also view a user's **sign-in logs** in Entra ID. They show when and **from which location** the user signed in, and whether the sign-in succeeded. This helps with troubleshooting and with spotting suspicious activity.

## 9.4 How to guide a user well

- **Ask them to share their screen**, ideally from a computer rather than a phone, so you can see exactly what they see.
- Go **step by step** and let them do the clicking.
- **Stay calm and patient.** For many people this is their first time.
- **Confirm success**, e.g. ask them to send you an email from their new account.

> 🏢 **In the real world:** A helpdesk engineer handles these calls daily. Solving them quickly and kindly is what makes users trust IT.

### ✅ Check your understanding
1. A user sees "account temporarily locked". What happened, and what do you do?
2. A user signs in but has no mailbox. What do you check first?
3. Where do you see whether a user has registered MFA?
4. A user bought a new phone and can't approve sign-ins. How do you fix it?
5. What's a quick fix when a browser keeps showing the wrong account?

**Answers:** (1) Too many wrong passwords, so reset the password. (2) Their licence, and that it was assigned to the right user. (3) Entra ID → Users → user → Authentication methods. (4) Delete their old authentication method, or require re-registration, so they set up MFA again. (5) Use a private/Incognito window.

---

# Chapter 10 — Outlook Everywhere: Web, Desktop and Mobile

### What you will learn
- The three ways to use Outlook
- How to add a business account to Outlook desktop and mobile

## 10.1 Three ways to use Outlook

| Version | How to open | When to use |
|---|---|---|
| **Outlook on the web** | **outlook.office.com** in any browser | Any computer, no installation needed |
| **Outlook desktop app** | Installed on Windows or Mac (included with Business Standard/Premium) | Daily office work |
| **Outlook mobile app** | iPhone / Android app | Email on the go |

All three show **the same mailbox**. An email read on the phone shows as read on the computer too, because everything lives in Exchange Online.

## 10.2 Adding the account to Outlook desktop

🛠️ **Hands-on**

1. Open **Outlook** on the computer. If another account is already there, choose **Add account**.
2. Type the business email address → **Continue**.
3. Type the **password**.
4. Complete **MFA**: approve in Microsoft Authenticator, or type the code shown in the app.
5. If offered, tick the option not to ask again on this device for a while, so the user isn't prompted every time.
6. Outlook loads the mailbox. **Autodiscover** (the CNAME record from Chapter 6) finds the settings automatically, so **no manual server settings or DNS work is needed**.

## 10.3 Adding the account to Outlook mobile

1. Install **Microsoft Outlook** from the app store.
2. **Add account** → type the business email → password → MFA.
3. Done. Email, calendar and contacts appear on the phone.

> 🏢 **In the real world:** Part of your job is **helping staff connect Outlook on every device they use**. Companies with Business Premium often manage this through Intune, so company data on phones stays protected.

### ✅ Check your understanding
1. What's the web address for Outlook on the web?
2. Why don't you need to type server settings when adding the account to Outlook desktop?
3. If a user deletes an email on their phone, will it disappear on their computer? Why?

**Answers:** (1) outlook.office.com. (2) Autodiscover finds the settings automatically. (3) Yes. All versions show the same mailbox, which is stored in Exchange Online.

---

# Chapter 11 — Everyday Outlook Tasks: Signatures, Automatic Replies and Rules

### What you will learn
- How to set up an email signature that appears automatically
- How to set up automatic replies (out of office)
- How to create rules that sort email automatically

These are everyday support tasks. Users often ask IT to set them up, and interviewers may ask how.

## 11.1 Email signatures

A **signature** is the block of text at the bottom of an email: name, job title, company, contact details.

🛠️ **Hands-on (Outlook on the web / new Outlook)**

1. **Settings ⚙ → Account → Signatures**.
2. Click **+ New signature** and give it a **name**. This is only the name of the signature, e.g. "Work signature", not the person's name.
3. Type the signature, for example:
   ```
   Kind regards,
   Anna Smith
   IT Support Engineer | Contoso
   anna@contoso.com | www.contoso.com
   Mobile: 04xx xxx xxx
   ```
4. ⭐ **Choose the default signatures** (the step people forget):
   - **For new messages:** select this signature
   - **For replies/forwards:** select this signature
5. **Save**.
6. Test: create a **new email** and **reply** to one. The signature should appear **automatically** both times.

> ⚠️ If the defaults aren't set, the user has to insert the signature by hand every time. The fix is almost always those two dropdowns.

## 11.2 Automatic replies (out of office)

**Automatic replies** send a message to everyone who emails you while you're away, e.g. *"I'm on leave, please contact…"*.

🛠️ **Hands-on**

1. **Settings ⚙ → Account → Automatic replies**.
2. **Turn on** automatic replies.
3. Tick **Send replies only during a time period** and set the **start and end date and time**. It then turns on and off by itself.
4. Write the **message for people inside the organisation**, e.g.:
   > Hi, I'm on annual leave until Monday 2 June. For IT issues please contact Ben at ben@contoso.com. I'll reply when I return.
5. ⭐ Tick **Send replies outside your organisation** and write a message for **external** senders (customers, suppliers, Gmail and Yahoo users). You might keep this one shorter or more formal.
6. **Save**, then test by emailing the account from another address.

> ⚠️ If customers say they didn't get the out-of-office reply, check that **"Send replies outside your organisation"** is ticked.

## 11.3 Rules

A **rule** tells Outlook to **do something automatically** with incoming emails that match a condition. Busy inboxes get hundreds of emails, and rules make sure important ones aren't missed and junk is moved away.

Every rule has three parts:

| Part | Meaning | Example |
|---|---|---|
| **Condition** | Which emails? | From my manager / subject contains "invoice" |
| **Action** | What to do with them? | Move to a folder / mark as junk / delete / forward |
| **Exception** (optional) | Except when… | …it's marked as important |

🛠️ **Hands-on: Settings ⚙ → Mail → Rules → + Add new rule**

**Example 1: never miss the manager's emails**
1. **Name:** Manager email
2. **Condition:** **From** → *(your manager)*
3. **Action:** **Move to** → **New folder** → "My manager"
4. Tick **Run rule now** to move emails already in the inbox too.
5. **Save**. New emails from the manager now go straight to that folder.

**Example 2: a department folder**
- Condition: **From** → several people (e.g. everyone in IT).
- Action: move to a new folder, "IT Department".
- You can create **sub-folders** under the Inbox for each department: Sales, Marketing, IT…

**Example 3: marketing emails by keyword**
1. **Name:** Sales or marketing
2. **Condition:** **Subject or body includes** → `sales`, `marketing`, `offer`, `discount`
3. **Action:** **Mark as junk** (or move to a "Promotions" folder, or delete)
4. **Save**, then test by sending an email with "discount" in the subject.

**Tips**
- A rule only matches the **words you enter**. If senders use different spellings, add those variations too.
- Rules run **from top to bottom**. Use **Stop processing more rules** if you don't want later rules to act on the same email.
- There are many conditions and actions to explore: *has an attachment*, *sent only to me*, *importance*, *forward to*, and more.

### ✅ Check your understanding
1. A user's signature only appears when they insert it manually. What's wrong?
2. Where do you set up automatic replies?
3. Customers don't receive a user's out-of-office message. What do you check?
4. What are the three parts of a rule?
5. Describe a rule that moves all email from the CEO into a folder called "CEO".

**Answers:** (1) The default signature for new messages and replies/forwards isn't set. (2) Settings → Account → Automatic replies. (3) That "Send replies outside your organisation" is on. (4) Condition, action, exception. (5) Condition: From → CEO. Action: Move to → new folder "CEO". Optionally run the rule now.

---

# Chapter 12 — Admin Roles and Least Privilege

### What you will learn
- What admin roles are
- The main roles for IT support: Helpdesk Admin, User Admin, Global Admin
- The principle of least privilege
- How to assign a role

## 12.1 What are admin roles?

Not every IT person should be able to do everything. Microsoft 365 uses **admin roles**, sets of permissions you give to a user. Only people with an admin role can open the admin center. Normal users can't.

## 12.2 The key roles

| Role | What it can do | Typical holder |
|---|---|---|
| **Helpdesk Administrator** | **Reset passwords** for **non-admin** users, sign users out, open support requests. **That's about it.** | First-line helpdesk staff and new IT starters |
| **User Administrator** | **Create, edit and delete users**, reset passwords, **manage groups**, assign licences, manage support tickets, view service health | IT support engineers who handle onboarding and offboarding |
| **Global Administrator** | **Everything** in the tenant, including all other roles, billing and security settings | Senior IT, the IT manager, the business owner |

> 💡 **Explain it like this:** The **Global Administrator** is the **master key**. It opens every door in the building. A **User Administrator** has keys to the offices. A **Helpdesk Administrator** only has the key to the **password cupboard**. You don't give a new employee the master key on their first day.

**Other useful roles you'll see:**

| Role | Purpose |
|---|---|
| **Global Reader** | Can **see** everything but **change nothing**. Great for trainees and auditors. |
| **Billing Administrator** | Buy licences, manage subscriptions and invoices |
| **Exchange Administrator** | Manage mailboxes and email settings only |
| **SharePoint Administrator** | Manage SharePoint and OneDrive only |
| **Teams Administrator** | Manage Teams only |

## 12.3 Least privilege

The **principle of least privilege** means: **give each person only the permissions they need to do their job, and nothing more.**

Why?
- **Fewer mistakes.** Someone who can't change a setting can't break it by accident.
- **Less damage if hacked.** If an attacker steals a helpdesk account, they can only reset passwords, not take over the whole company.
- **Accountability.** It's clear who is allowed to do what.

Microsoft recommends having **fewer than five Global Administrators**, and at least two so the organisation is never locked out.

A common path for a new IT starter is **Helpdesk Admin → User Admin → Global Admin**, as trust and skill grow.

## 12.4 Assigning a role

🛠️ **Method 1: from the Roles page** (good for several users)
1. Admin center → **Roles → Role assignments**.
2. Click the role, e.g. **User Administrator**.
3. **Assigned → Add users** → search for and select the people → **Add**.

🛠️ **Method 2: from the user** (one user)
1. Admin center → **Users → Active users** → click the user.
2. **Account** tab → **Manage roles**.
3. Choose **Admin center access** → tick the role → **Save changes**.

After a role is assigned, **it can take a few minutes** to take effect. The user then goes to **admin.microsoft.com**. If the dashboard doesn't appear, they can wait a little, then sign out and back in.

### ✅ Check your understanding
1. What can a Helpdesk Administrator do?
2. Which role creates and deletes users?
3. Why is Global Administrator called the "master key"?
4. Explain least privilege in your own words.
5. How many Global Admins does Microsoft recommend?

**Answers:** (1) Reset passwords for non-admin users (and a few small support tasks). (2) User Administrator. (3) It can do everything in the tenant. (4) Give people only the access they need for their job. (5) Fewer than five, and at least two.

---

# Chapter 13 — Your Career: Putting It All Together

## 13.1 What you can now do

After this part, you can:

- ✅ Explain what Microsoft 365 is and what each service does
- ✅ Recommend the right licence
- ✅ Get a tenant and navigate the admin center
- ✅ Connect a company domain with DNS records
- ✅ Onboard users one at a time or in bulk, and manage licences and passwords
- ✅ Guide users through first sign-in and MFA, and troubleshoot problems
- ✅ Set up Outlook on web, desktop and mobile
- ✅ Configure signatures, automatic replies and rules
- ✅ Assign admin roles using least privilege

These are real, day-one tasks for an **IT Support / Helpdesk / Microsoft 365 Administrator** role.

## 13.2 A day in the life

> Monday, 9:00 AM. A new salesperson starts today. You **create their account**, assign a **Business Premium licence**, and give them a **temporary password**. When they sign in, you guide them through **Microsoft Authenticator**. You then add their mailbox to **Outlook on their phone**, set up their **signature**, and create a **rule** to file emails from their manager.
>
> 11:30 AM. A user is "locked out". You **reset their password**.
>
> 2:00 PM. A colleague bought a new phone and can't approve sign-ins. You **reset their MFA method** in Entra ID.
>
> 4:30 PM. Someone is going on holiday and asks you to set their **out-of-office**, including for external customers.

## 13.3 Interview preparation checklist

Be ready to answer, in your own words:

1. What is Microsoft 365, and what is SaaS?
2. Name the main services and what each one does.
3. Office 365 vs Microsoft 365?
4. Business Basic vs Standard vs Premium? Which did your company use? (**Business Premium**)
5. What DNS records does Microsoft 365 need, and what does each do?
6. Walk me through onboarding a new user.
7. How would you create 100 users at once?
8. A user can't sign in. How do you troubleshoot?
9. What is MFA, and how do you reset it for a user with a new phone?
10. What's the difference between Helpdesk Admin, User Admin and Global Admin?
11. What is the principle of least privilege?

## 13.4 Study advice

- **Practise hands-on.** This subject is learned by doing, not by reading. Repeat every lab until you can do it without notes.
- **Break things and fix them.** Lock a test user out, then unlock them. Remove a licence and see what happens.
- **Ask for help early.** Use your classmates, your trainer and the support team.
- **Start applying for jobs** as soon as you're comfortable with these tasks. Your skills grow faster once you're working.

**Coming next:** groups, shared mailboxes, deeper Exchange administration, and then **Microsoft Intune** for device management.

---

# Appendix A — Quick Reference: URLs and Menu Paths

### URLs

| URL | What |
|---|---|
| **admin.microsoft.com** | Microsoft 365 admin center |
| **office.com** | Microsoft 365 home (Admin tile for admins) |
| **outlook.office.com** | Outlook on the web |
| **entra.microsoft.com** | Microsoft Entra admin center (users, MFA, sign-in logs) |
| **portal.azure.com** | Azure portal (also reaches Entra ID) |
| **mysignins.microsoft.com/security-info** | A user's own MFA and security info page |

### Admin center paths

| Task | Path |
|---|---|
| Add a domain | Settings → Domains → Add domain |
| Get a trial / buy licences | Marketplace → All products → Business Premium |
| Add one user | Users → Active users → Add a user |
| Add many users | Users → Active users → Add multiple users (CSV) |
| Assign a licence (one user) | Users → Active users → user → Licenses and apps |
| Assign licences (bulk) | Users → Active users → select → Manage product licences |
| Reset password(s) | Users → Active users → select → Reset password |
| Assign an admin role | Roles → Role assignments → role → Add users |
| Check a user's MFA | Entra → Users → user → Authentication methods |

### Outlook paths

| Task | Path |
|---|---|
| Signature | Settings → Account → Signatures (set both defaults) |
| Automatic replies | Settings → Account → Automatic replies (tick "outside your organisation") |
| Rules | Settings → Mail → Rules → Add new rule |

---

# Appendix B — Glossary

| Term | Meaning |
|---|---|
| **Active Directory** | Microsoft's on-premises identity system (usernames and passwords) |
| **Admin center** | The Microsoft 365 web portal for administrators |
| **Autodiscover** | Lets Outlook find mailbox settings automatically (via a CNAME record) |
| **Business email** | Email using the company's own domain |
| **CNAME** | A DNS record that points one name to another (alias) |
| **CSV** | Comma-separated values, a simple spreadsheet file format used for bulk imports |
| **DNS** | Domain Name System. Translates names to IP addresses. |
| **Domain** | A company's internet name, e.g. contoso.com |
| **Entra ID** | Microsoft's cloud identity service (formerly Azure AD) |
| **Exchange Online** | Microsoft's cloud email server |
| **Global Administrator** | The admin role with full control, the "master key" |
| **Helpdesk Administrator** | Admin role that can reset non-admin passwords |
| **IaaS / PaaS / SaaS** | Infrastructure / Platform / Software as a Service |
| **Intune** | Microsoft's device and app management service |
| **Least privilege** | Give only the access needed, nothing more |
| **Licence** | A paid subscription that switches on services for a user |
| **MAM** | Mobile Application Management, which manages company apps and data only |
| **MDM** | Mobile Device Management, which manages the whole device |
| **MFA** | Multi-Factor Authentication, more than one proof of identity |
| **Microsoft Authenticator** | Phone app used for MFA |
| **MX record** | DNS record that tells the internet where to deliver email |
| **Offboarding** | Removing access and handling accounts when someone leaves |
| **OneDrive** | Personal cloud storage |
| **Onboarding** | Creating and setting up accounts for new staff |
| **Outlook** | The app used to read email (web, desktop, mobile) |
| **Registrar** | A company that sells domain names (e.g. GoDaddy) |
| **Role** | A set of admin permissions |
| **Rule (Outlook)** | Automatic action on incoming email that matches a condition |
| **SharePoint** | Business/team cloud storage and sites |
| **SPF** | DNS TXT record listing servers allowed to send email for a domain |
| **SSO** | Single sign-on, one account for many services |
| **Teams** | Chat, meetings, calls and phone system |
| **Temporary password** | A password the user must change at first sign-in |
| **Tenant** | An organisation's private space in Microsoft 365 |
| **TXT record** | DNS text record, used for domain verification and SPF |
| **User Administrator** | Admin role that manages users and groups |
| **VoIP** | Voice over Internet Protocol, phone calls over the internet |

---

# Appendix C — Lab Workbook

Do these in order in a practice tenant. Tick each one when you can do it **without looking at the book**.

| # | Lab | Chapter | ✔ |
|---|---|---|---|
| 1 | Sign in to **admin.microsoft.com** and find: Active users, Roles, Marketplace, Billing, Settings → Domains | 5 | ☐ |
| 2 | In **Settings → Domains**, open the domain and identify the **MX, TXT, CNAME and SPF** records | 6 | ☐ |
| 3 | Create **one user** with a temporary password and a Business Premium licence | 7 | ☐ |
| 4 | Sign in as that user in a **private window**, change the password and register **MFA** | 8 | ☐ |
| 5 | Send an email from **Gmail** to the new user, and reply | 8 | ☐ |
| 6 | Download the **CSV template**, create **5 users** using `CONCATENATE`, and import them with licences | 7 | ☐ |
| 7 | Remove the licence from one user, then use **Manage product licences → Assign more** to give it back to several users | 7 | ☐ |
| 8 | **Reset the password** for all 5 users at once | 7 | ☐ |
| 9 | In **Entra ID**, check a user's **Authentication methods**. Delete the method and have the user register again. | 9 | ☐ |
| 10 | Add the account to **Outlook desktop** and **Outlook mobile** | 10 | ☐ |
| 11 | Create a **signature** and set it as default for **new** and **reply** emails. Test both. | 11 | ☐ |
| 12 | Set **automatic replies** for tomorrow, inside **and** outside the organisation. Test from Gmail. | 11 | ☐ |
| 13 | Create three **rules**: manager → folder, department → folder, keywords → junk. Test each one. | 11 | ☐ |
| 14 | Assign **Helpdesk Administrator** to a test user. Sign in as them and see what they can and can't do. | 12 | ☐ |
| 15 | Change that user to **User Administrator** and compare | 12 | ☐ |

### Scenario challenges

1. **New starter:** "Priya starts tomorrow in Sales. She needs email on her laptop and phone, a signature, and her manager's emails in a separate folder." List every step.
2. **Locked out:** "Tom says 'account temporarily locked' and he has a new phone." What two things do you fix, and where?
3. **Bulk intake:** "A college is enrolling 120 students on Monday." How do you create and license them quickly?
4. **Missing email:** "A new user can sign in but has no mailbox." What do you check, and in what order?
5. **Holiday:** "The sales manager is away for two weeks and customers must be told who to contact." What do you configure, and which setting is easy to forget?

**Suggested answers:**
1. Create the user with a temporary password and a Business Premium licence → guide first sign-in and MFA → add the account to Outlook desktop and mobile → set the signature with both defaults → create a rule: From manager → move to a folder.
2. Reset his password (Users → Active users → Reset password). Reset his MFA (Entra → Users → Tom → Authentication methods → delete the old method) so he registers the new phone.
3. Add multiple users with a CSV template, build the usernames with `CONCATENATE`, and assign licences during the import. Then bulk reset passwords if needed.
4. Is a licence assigned, to the **right** user? Has enough time passed for the mailbox to be created? Is the domain status Healthy?
5. Automatic replies with a time period for two weeks. The easy-to-forget part is ticking **"Send replies outside your organisation"** so customers receive it.

---

*End of Part 1.*
