<div align="center">

# 🔐 PWF Auth

**مفاتيح ترخيص ونظام حسابات مجاني لتطبيقات سطح المكتب**
مفاتيح مرتبطة بمعرّف الجهاز (HWID) · حسابات للمستخدمين · الإيقاف عن بُعد · تحديثات تلقائية (OTA). وكل ذلك من خلال واجهة REST API واحدة وبسيطة

[![Website](https://img.shields.io/badge/Website-pwfauth.com-3CCF91?style=for-the-badge)](https://pwfauth.com)
[![NuGet](https://img.shields.io/nuget/v/PWFAuth?style=for-the-badge&logo=nuget&label=NuGet&color=3CCF91)](https://www.nuget.org/packages/PWFAuth)
[![Discord](https://img.shields.io/badge/Discord-Join-30363D?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/hX3ZV2ZtMp)
[![Telegram](https://img.shields.io/badge/Telegram-@pwfauthnews-229ED9?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/pwfauthnews)
[![YouTube](https://img.shields.io/badge/YouTube-@pwfauth-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@pwfauth)

<p><a href="https://github.com/pwfauth">English</a> · <a href="https://github.com/pwfauth/pwfauth/blob/main/README.zh-CN.md">简体中文</a> · <a href="https://github.com/pwfauth/pwfauth/blob/main/README.tr.md">Türkçe</a> · <b>العربية</b></p>

</div>

---

## ما هي PWF Auth؟

PWF Auth خدمة سحابية لبيع برامجك وحمايتها. تُنشئ مفاتيح الترخيص من لوحة التحكم، ويتحقق تطبيقك منها عبر الواجهة البرمجية (API) أو إحدى حزم SDK، فتبقى صاحب القرار حتى بعد البيع

- 🔑 **مفاتيح الترخيص:** ربط بمعرّف الجهاز، وتاريخ انتهاء، وحدّ لعدد الأجهزة. يمكنك إيقاف أي مفتاح مؤقتاً أو حظره أو تمديده من لوحة التحكم
- 👤 **حسابات المستخدمين:** يُنشئ العملاء حساباتهم ويسجّلون الدخول إليها، بمفتاح ترخيص أو من دونه، ويستخدمون المفاتيح لإضافة مدة إلى حساباتهم
- 🛡️ **الإيقاف عن بُعد:** تنتهي الجلسات المشفّرة خلال ثوانٍ عندما تحظر المفتاح أو توقفه مؤقتاً أو تعيد تعيينه
- 💻 **نقل الترخيص ذاتياً:** ينقل العملاء ترخيصهم إلى جهاز جديد بأنفسهم، بعد مدة الانتظار التي تحددها
- 🎁 **نسخ تجريبية مجانية**، و🚀 **تحديثات تلقائية (OTA)** مع الإصدارات وقنوات النشر وروابط التنزيل
- 🤝 **البيع:**
  - الموزّعون (resellers)
  - الربط مع المتاجر: SellAuth وStripe وShoppex
  - بوتات Discord وTelegram لعملائك
- 📊 **لوحة تحكم** للمفاتيح والعملاء والإحصاءات والتنبيهات

## ⚡ البدء السريع (.NET)

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

يُنشئ **مولّد SDK** في لوحة التحكم عميلاً جاهزاً للاستخدام بلغات **C# وVB.NET وPython وJavaScript وJava وKotlin وPHP وDart وC++ وDelphi**

## 📦 المستودعات مفتوحة المصدر

| المستودع | الوصف |
| --- | --- |
| [**pwfauth-dotnet**](https://github.com/pwfauth/pwfauth-dotnet) | عميل .NET الرسمي: حزمة NuGet باسم [`PWFAuth`](https://www.nuget.org/packages/PWFAuth) (netstandard2.0 + net8.0) |
| [**pwfauth-vbnet-examples**](https://github.com/pwfauth/pwfauth-vbnet-examples) | أمثلة VB.NET لتطبيق Console وتطبيق WinForms باسم **API Explorer**، إضافةً إلى مثال C# على .NET Framework 4.8.1، وكلها مبنية على حزمة NuGet |
| [**pwfauth-csharp-client**](https://github.com/pwfauth/pwfauth-csharp-client) | مثال لتطبيق سطح مكتب بـ C# Windows Forms (.NET Framework 4.8.1) |
| [**pwfauth-cpp-client**](https://github.com/pwfauth/pwfauth-cpp-client) | مثال لتطبيق سطح مكتب أصلي بلغة C++17 |
| [**pwfauth-python-client**](https://github.com/pwfauth/pwfauth-python-client) | عميل Python يغطي كل نقاط الاتصال في الواجهة البرمجية |
| [**pwfauth-python-desktop-sample**](https://github.com/pwfauth/pwfauth-python-desktop-sample) | مثال لتطبيق سطح مكتب بـ Tkinter مع جلسات تحقق دوري مباشرة |
| [**pwfauth-android**](https://github.com/pwfauth/pwfauth-android) | تطبيق تجريبي لنظام Android بلغة Kotlin وJetpack Compose: مفاتيح الترخيص وحسابات العملاء والإيقاف عن بُعد على الهاتف |
| [**python-cli-license-starter**](https://github.com/pwfauth/python-cli-license-starter) | قالب لبيع أداة سطر أوامر بلغة Python: تفعيل المفتاح، ونسخة تجريبية مجانية، والإيقاف عن بُعد أثناء التشغيل، وإنشاء ملف تنفيذي واحد (Typer + Rich) |

## 🔗 روابط

- 🌐 الموقع: **[pwfauth.com](https://pwfauth.com)**
- 📖 [الوثائق](https://pwfauth.com/docs) · [مرجع الواجهة البرمجية](https://pwfauth.com/api-reference) · [حزم SDK](https://pwfauth.com/sdks)
- 📰 [سجل التغييرات](https://pwfauth.com/changelog) · [حالة النظام](https://pwfauth.com/status)
- 💬 Discord: **[انضم إلى الخادم](https://discord.gg/hX3ZV2ZtMp)**
- ✈️ Telegram: الأخبار **[@pwfauthnews](https://t.me/pwfauthnews)** · الدعم **[@pwfauth](https://t.me/pwfauth)**
- ▶️ YouTube: **[@pwfauth](https://www.youtube.com/@pwfauth)** (شروحات)

<div align="center">
<sub>أضف نظام الترخيص إلى تطبيقك خلال دقائق</sub>
</div>
