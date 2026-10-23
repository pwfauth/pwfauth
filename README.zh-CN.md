<div align="center">

# 🔐 PWF Auth

**为桌面应用提供免费的许可证密钥和用户认证**
绑定 HWID 的密钥 · 用户账号 · 远程停用 · OTA 更新，全部通过一个简单的 REST API 完成

[![Website](https://img.shields.io/badge/Website-pwfauth.com-3CCF91?style=for-the-badge)](https://pwfauth.com)
[![NuGet](https://img.shields.io/nuget/v/PWFAuth?style=for-the-badge&logo=nuget&label=NuGet&color=3CCF91)](https://www.nuget.org/packages/PWFAuth)
[![Discord](https://img.shields.io/badge/Discord-Join-30363D?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/hX3ZV2ZtMp)
[![Telegram](https://img.shields.io/badge/Telegram-@pwfauthnews-229ED9?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/pwfauthnews)
[![YouTube](https://img.shields.io/badge/YouTube-@pwfauth-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@pwfauth)

<p><a href="https://github.com/pwfauth">English</a> · <b>简体中文</b> · <a href="https://github.com/pwfauth/pwfauth/blob/main/README.tr.md">Türkçe</a> · <a href="https://github.com/pwfauth/pwfauth/blob/main/README.ar.md">العربية</a></p>

</div>

---

## PWF Auth 是什么？

PWF Auth 是一个托管后端，用来销售和保护你的软件。你在后台创建许可证密钥，应用通过 API 或 SDK 校验这些密钥。软件卖出去之后，控制权依然在你手里

- 🔑 **许可证密钥：** HWID 绑定、到期时间和设备数量限制。可以在后台随时暂停、封禁或延长任意密钥
- 👤 **用户账号：** 客户可以注册和登录，有没有许可证密钥都可以，还能兑换密钥来增加使用时长
- 🛡️ **远程停用（Kill switch）：** 当你封禁、暂停或重置密钥时，加密的心跳会话会在几秒内结束
- 💻 **自助更换设备：** 客户可以自己把许可证转移到新电脑，冷却时间由你设定
- 🎁 **免费试用**，以及 🚀 支持版本、发布渠道和下载链接的 **OTA 更新**
- 🤝 **销售：**
  - 代理商（reseller）
  - 商店对接：SellAuth、Stripe 和 Shoppex
  - 面向买家的 Discord 和 Telegram 机器人
- 📊 **后台面板**，用于管理密钥、客户、数据分析和提醒

## ⚡ 快速开始（.NET）

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

后台的 **SDK 生成器** 可以为 **C#、VB.NET、Python、JavaScript、Java、Kotlin、PHP、Dart、C++ 和 Delphi** 生成开箱即用的客户端

## 📦 开源仓库

| 仓库 | 简介 |
| --- | --- |
| [**pwfauth-dotnet**](https://github.com/pwfauth/pwfauth-dotnet) | 官方 .NET 客户端：[`PWFAuth`](https://www.nuget.org/packages/PWFAuth) NuGet 包（netstandard2.0 + net8.0） |
| [**pwfauth-vbnet-examples**](https://github.com/pwfauth/pwfauth-vbnet-examples) | VB.NET 控制台程序和 WinForms **API Explorer**，以及运行在 .NET Framework 4.8.1 上的 C# 示例，均基于 NuGet 包 |
| [**pwfauth-csharp-client**](https://github.com/pwfauth/pwfauth-csharp-client) | C# Windows Forms 桌面示例（.NET Framework 4.8.1） |
| [**pwfauth-cpp-client**](https://github.com/pwfauth/pwfauth-cpp-client) | 原生 C++17 桌面示例 |
| [**pwfauth-python-client**](https://github.com/pwfauth/pwfauth-python-client) | 覆盖全部接口的 Python 客户端 |
| [**pwfauth-python-desktop-sample**](https://github.com/pwfauth/pwfauth-python-desktop-sample) | 带实时心跳会话的 Tkinter 桌面示例 |
| [**pwfauth-android**](https://github.com/pwfauth/pwfauth-android) | 用 Kotlin + Jetpack Compose 编写的 Android 演示应用：在手机上演示许可证密钥、客户账号和远程停用 |
| [**python-cli-license-starter**](https://github.com/pwfauth/python-cli-license-starter) | 用于销售 Python 命令行工具的模板：密钥激活、免费试用、运行中远程停用，以及打包成单个 exe（Typer + Rich） |

## 🔗 链接

- 🌐 官网：**[pwfauth.com](https://pwfauth.com)**
- 📖 [文档](https://pwfauth.com/docs) · [API 参考](https://pwfauth.com/api-reference) · [SDK](https://pwfauth.com/sdks)
- 📰 [更新日志](https://pwfauth.com/changelog) · [系统状态](https://pwfauth.com/status)
- 💬 Discord：**[加入服务器](https://discord.gg/hX3ZV2ZtMp)**
- ✈️ Telegram：新闻 **[@pwfauthnews](https://t.me/pwfauthnews)** · 支持 **[@pwfauth](https://t.me/pwfauth)**
- ▶️ YouTube：**[@pwfauth](https://www.youtube.com/@pwfauth)**（教程）

<div align="center">
<sub>几分钟内为你的应用加上授权功能</sub>
</div>
