<div align="center">

# 🔐 PWF Auth

**Free license keys and user authentication for your desktop apps.**
HWID-locked keys · user accounts · remote kill switch · OTA updates. All behind one simple REST API.

[![Website](https://img.shields.io/badge/Website-pwfauth.com-3CCF91?style=for-the-badge)](https://pwfauth.com)
[![NuGet](https://img.shields.io/nuget/v/PWFAuth?style=for-the-badge&logo=nuget&label=NuGet&color=3CCF91)](https://www.nuget.org/packages/PWFAuth)
[![Discord](https://img.shields.io/badge/Discord-Join-30363D?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/hX3ZV2ZtMp)
[![Telegram](https://img.shields.io/badge/Telegram-@pwfauthnews-229ED9?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/pwfauthnews)
[![YouTube](https://img.shields.io/badge/YouTube-@pwfauth-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@pwfauth)

</div>

---

## What is PWF Auth?

PWF Auth is a hosted backend for selling and protecting your software. You
create license keys in the dashboard, and your app checks them through the API
or an SDK. You stay in control after the sale.

- 🔑 **License keys:** HWID binding, expiry and device limits. Pause, ban or
  extend a key from the dashboard.
- 👤 **User accounts:** customers sign up and sign in, with or without a license
  key. They redeem keys to add time.
- 🛡️ **Kill switch:** encrypted heartbeat sessions end within seconds when you
  ban, pause or reset a key.
- 💻 **Self-service device moves:** customers move their license to a new PC
  themselves, with your cooldown.
- 🎁 **Free trials**, and 🚀 **OTA updates** with versions, channels and
  download links.
- 🤝 **Selling:**
  - resellers;
  - store connections: SellAuth, Stripe and Shoppex;
  - Discord and Telegram bots for your buyers.
- 📊 **A dashboard** for keys, customers, analytics and alerts.

## ⚡ Quick start (.NET)

```bash
dotnet add package PWFAuth
```

```csharp
var client = new PwfClient("your-64-char-app-secret");
client.SessionEnded += (s, e) => { MessageBox.Show(e.Message); Application.Exit(); };

var login = await client.LoginAsync(licenseKey);
if (!login.Success) { MessageBox.Show(login.Message); return; }
client.StartHeartbeat();   // obeys your kill switch from now on
```

The dashboard's **SDK Generator** writes a ready-to-use client for **C#, VB.NET,
Python, JavaScript, Java, Kotlin, PHP, Dart, C++ and Delphi**.

## 📦 Open-source repositories

| Repository | What it is |
| --- | --- |
| [**pwfauth-dotnet**](https://github.com/pwfauth/pwfauth-dotnet) | The official .NET client: the [`PWFAuth`](https://www.nuget.org/packages/PWFAuth) NuGet package (netstandard2.0 + net8.0) |
| [**pwfauth-vbnet-examples**](https://github.com/pwfauth/pwfauth-vbnet-examples) | VB.NET console and WinForms **API Explorer**, plus C# on .NET Framework 4.8.1. Built on the NuGet package |
| [**pwfauth-csharp-client**](https://github.com/pwfauth/pwfauth-csharp-client) | C# Windows Forms desktop sample (.NET Framework 4.8.1) |
| [**pwfauth-cpp-client**](https://github.com/pwfauth/pwfauth-cpp-client) | Native C++17 desktop sample |
| [**pwfauth-python-client**](https://github.com/pwfauth/pwfauth-python-client) | Python client for every endpoint |
| [**pwfauth-python-desktop-sample**](https://github.com/pwfauth/pwfauth-python-desktop-sample) | Tkinter desktop sample with live heartbeat sessions |

## 🔗 Links

- 🌐 Website: **[pwfauth.com](https://pwfauth.com)**
- 📖 [Docs](https://pwfauth.com/docs) · [API reference](https://pwfauth.com/api-reference) · [SDKs](https://pwfauth.com/sdks)
- 📰 [Changelog](https://pwfauth.com/changelog) · [System status](https://pwfauth.com/status)
- 💬 Discord: **[join the server](https://discord.gg/hX3ZV2ZtMp)**
- ✈️ Telegram: news **[@pwfauthnews](https://t.me/pwfauthnews)** · support **[@pwfauth](https://t.me/pwfauth)**
- ▶️ YouTube: **[@pwfauth](https://www.youtube.com/@pwfauth)** (tutorials)

<div align="center">
<sub>Build licensing into your app in minutes.</sub>
</div>
