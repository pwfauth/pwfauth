<div align="center">

# 🔐 PWF Auth

**Masaüstü uygulamalarınız için ücretsiz lisans anahtarları ve kullanıcı kimlik doğrulaması**
HWID'ye bağlı anahtarlar · kullanıcı hesapları · uzaktan durdurma · OTA güncellemeleri. Hepsi tek ve basit bir REST API ile

[![Website](https://img.shields.io/badge/Website-pwfauth.com-3CCF91?style=for-the-badge)](https://pwfauth.com)
[![NuGet](https://img.shields.io/nuget/v/PWFAuth?style=for-the-badge&logo=nuget&label=NuGet&color=3CCF91)](https://www.nuget.org/packages/PWFAuth)
[![Discord](https://img.shields.io/badge/Discord-Join-30363D?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/hX3ZV2ZtMp)
[![Telegram](https://img.shields.io/badge/Telegram-@pwfauthnews-229ED9?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/pwfauthnews)
[![YouTube](https://img.shields.io/badge/YouTube-@pwfauth-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@pwfauth)

<p><a href="https://github.com/pwfauth">English</a> · <a href="https://github.com/pwfauth/pwfauth/blob/main/README.zh-CN.md">简体中文</a> · <b>Türkçe</b> · <a href="https://github.com/pwfauth/pwfauth/blob/main/README.ar.md">العربية</a></p>

</div>

---

## PWF Auth nedir?

PWF Auth, yazılımınızı satmanız ve korumanız için barındırılan bir arka uç hizmetidir. Lisans anahtarlarını panelde oluşturursunuz, uygulamanız da bunları API ya da bir SDK üzerinden doğrular. Satıştan sonra da kontrol sizde kalır

- 🔑 **Lisans anahtarları:** HWID bağlama, bitiş tarihi ve cihaz sınırı. Herhangi bir anahtarı panelden duraklatabilir, yasaklayabilir ya da süresini uzatabilirsiniz
- 👤 **Kullanıcı hesapları:** müşteriler lisans anahtarıyla ya da anahtarsız kayıt olup giriş yapar. Süre eklemek için anahtar kullanabilirler
- 🛡️ **Uzaktan durdurma (kill switch):** bir anahtarı yasakladığınızda, duraklattığınızda ya da sıfırladığınızda şifreli heartbeat oturumları saniyeler içinde sona erer
- 💻 **Kendi kendine cihaz değişikliği:** müşteriler lisanslarını yeni bir bilgisayara kendileri taşır, sizin belirlediğiniz bekleme süresiyle
- 🎁 **Ücretsiz deneme** ve 🚀 sürümler, kanallar ve indirme bağlantılarıyla **OTA güncellemeleri**
- 🤝 **Satış:**
  - bayiler (reseller)
  - mağaza bağlantıları: SellAuth, Stripe ve Shoppex
  - alıcılarınız için Discord ve Telegram botları
- 📊 Anahtarlar, müşteriler, analizler ve uyarılar için **bir yönetim paneli**

## ⚡ Hızlı başlangıç (.NET)

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

Paneldeki **SDK Generator**, **C#, VB.NET, Python, JavaScript, Java, Kotlin, PHP, Dart, C++ ve Delphi** için kullanıma hazır bir istemci üretir

## 📦 Açık kaynak depolar

| Depo | Açıklama |
| --- | --- |
| [**pwfauth-dotnet**](https://github.com/pwfauth/pwfauth-dotnet) | Resmi .NET istemcisi: [`PWFAuth`](https://www.nuget.org/packages/PWFAuth) NuGet paketi (netstandard2.0 + net8.0) |
| [**pwfauth-vbnet-examples**](https://github.com/pwfauth/pwfauth-vbnet-examples) | VB.NET konsol ve WinForms **API Explorer** örnekleri, ayrıca .NET Framework 4.8.1 üzerinde C#. Hepsi NuGet paketiyle hazırlandı |
| [**pwfauth-csharp-client**](https://github.com/pwfauth/pwfauth-csharp-client) | C# Windows Forms masaüstü örneği (.NET Framework 4.8.1) |
| [**pwfauth-cpp-client**](https://github.com/pwfauth/pwfauth-cpp-client) | Yerel C++17 masaüstü örneği |
| [**pwfauth-python-client**](https://github.com/pwfauth/pwfauth-python-client) | Tüm uç noktaları kapsayan Python istemcisi |
| [**pwfauth-python-desktop-sample**](https://github.com/pwfauth/pwfauth-python-desktop-sample) | Canlı heartbeat oturumlarıyla Tkinter masaüstü örneği |
| [**pwfauth-android**](https://github.com/pwfauth/pwfauth-android) | Kotlin + Jetpack Compose ile Android demo uygulaması: telefonda lisans anahtarları, müşteri hesapları ve uzaktan durdurma |
| [**python-cli-license-starter**](https://github.com/pwfauth/python-cli-license-starter) | Python komut satırı aracı satmak için şablon: anahtar etkinleştirme, ücretsiz deneme, çalışırken uzaktan durdurma ve tek exe derlemesi (Typer + Rich) |

## 🔗 Bağlantılar

- 🌐 Web sitesi: **[pwfauth.com](https://pwfauth.com)**
- 📖 [Belgeler](https://pwfauth.com/docs) · [API referansı](https://pwfauth.com/api-reference) · [SDK'lar](https://pwfauth.com/sdks)
- 📰 [Değişiklik günlüğü](https://pwfauth.com/changelog) · [Sistem durumu](https://pwfauth.com/status)
- 💬 Discord: **[sunucuya katılın](https://discord.gg/hX3ZV2ZtMp)**
- ✈️ Telegram: haberler **[@pwfauthnews](https://t.me/pwfauthnews)** · destek **[@pwfauth](https://t.me/pwfauth)**
- ▶️ YouTube: **[@pwfauth](https://www.youtube.com/@pwfauth)** (eğitim videoları)

<div align="center">
<sub>Uygulamanıza dakikalar içinde lisanslama ekleyin</sub>
</div>
