# 如何解决国内手机注册telegram收不到验证码问题

登录 Telegram 帐户时，该应用程序会请求一次性代码，该代码由五位或六位数字组成。在本文中，我们将介绍用户在收到此类代码时可能遇到的问题。

# 1\. 如何获取授权码？

Telegram 平台可以通过不同的方式将此代码发送给用户：

- 如果该帐户已经有一个活动会话（即该帐户已经在某个应用程序中的某个设备上登录），则授权代码将从[Telegram 服务帐户](https://t.me/+42777 "电报服务帐户")到达此会话。在这种情况下，应用程序会显示“未获取代码？”按钮，用户有时可以使用该按钮请求 SIM 卡上的代码。
- 如果没有处于活动会话的设备，代码将通过电话或短信发送到 SIM 卡。
- 如果 Telegram 之前已将用户切换为通过电子邮件授权，则代码将发送到指定为登录电子邮件的电子邮件地址。顺便说一句，即使帐户有活动会话，代码也会到达此地址：在这种情况下，代码会同时发送到会话和电子邮件。

# 2\. 发送代码到另一个会话

如果当您登录帐户时，应用程序显示消息“我们通过 Telegram 向另一台设备发送了一个代码，其中……已获得授权”，那么可能只有两个问题：

### 2.1.该代码未到达另一个会话

有时，用户发现自己处于这样的境地：

1. 他们拥有已登录帐户的设备。
2. 他们尝试在新设备或新应用程序上登录自己的帐户。
3. 步骤 2 中的应用程序显示代码已发送到另一台设备，但代码未到达。

我们不确定为什么会发生这种情况。我们建议尝试以下方法：

1. [尝试在其他应用程序（来自 Google Play 的 Telegram](https://play.google.com/store/apps/details?id=org.telegram.messenger "来自 Google Play 的 Telegram")、[来自官方网站的 Telegram](https://telegram.org/android "来自官方网站的 Telegram")或[Telegram X](https://play.google.com/store/apps/details?id=org.thunderdog.challegram "电报X") ）和/或从其他设备登录您的帐户。如果 Telegram 服务器由于某种原因不信任您尝试登录帐户的设备或应用程序，这会有所帮助。在这种情况下，重新安装应用程序也会有所帮助。
2. 等待几个小时，然后重试。如果代码由于某些内部平台故障等原因而无法提供，这会有所帮助。

### 2.2.没有其他会议

有时，用户确实知道没有其他会话（例如，他只是手动终止了它们），但应用程序仍然报告代码已发送到另一个会话。在这种情况下，等待几十分钟或几个小时通常会有所帮助。

# 3\. 应用程序显示代码已通过电话或短信发送，但代码未到达

用户输入电话号码，应用程序指示代码已发送，但随后什么也没有发生：既没有收到电话也没有收到短信。

我们将在三个部分中概述可能影响一次性代码交付的所有条件和措施。

## 3.1.所需条件

如果不满足这些要求中的任何一个，则可能无法接收（有时甚至请求）代码。

1. 使用运行 Android 或 iOS 的移动设备。[无法](https://t.me/tginfoen/1169 "不可能")通过 PC 请求代码。
2. 使用官方移动应用程序：在 Android 上 – [Telegram](https://play.google.com/store/apps/details?id=org.telegram.messenger "电报")或[Telegram X](https://play.google.com/store/apps/details?id=org.thunderdog.challegram "电报")，在 iOS 上 – [Telegram](https://apps.apple.com/app/telegram-messenger/id686449807 "非官方客户")。无法通过其他应用程序（例如网络版本（WebA 和 WebK）或第三方开发人员创建的[非官方客户端](https://t.me/tginfoen/1611 "非官方客户")）请求代码。一些非官方应用程序仍然提供请求代码的选项，但这违反了 Telegram 的使用条款，而该信使积极执行该条款。
3. 如果您使用的是 Android 设备，请确保它具有 Google 服务。无法在没有 Google 服务的设备上接收代码。如果您有华为智能手机，请从[AppGallery](https://appgallery.cloud.huawei.com/ag/n/app/C101184875)安装 Telegram 。
4. 使用带有可接收来自身份验证服务的来电和短信的电话号码的 SIM 卡。确保 SIM 卡正常运行，并且其余额允许接收来电和消息，包括来自身份验证服务的来电和消息。有时，尤其是在漫游时，运营商会定期向 SIM 卡发送消息，但不会从大量发送此类 SMS 的服务发送消息。要检查您的 SIM 卡是否可以接收此类短信，您可以通过短信请求恢复您的 Google 帐户密码：用于输入 Telegram 帐户的代码是由同一发件人发送的。

## 3.2.建议采取的行动

有时，即使不满足以下要求，代码也会到达。但是，如果代码未到达，我们建议您采取以下建议：

1. 使用最新版本的移动应用程序。如果它有几个版本过时（例如，10.1 而不是 10.3），可能并不重要，但使用半年到一年前发布的版本可以显着降低接收代码的机会。
2. 将 SIM 卡插入您要请求代码的设备。这对于 Firebase 身份验证系统非常重要，该系统自 2023 年初以来一直在 Telegram Android 应用中[使用。](https://t.me/tginfoen/1598 "应用")
3. 使用具有官方固件且没有 root 访问权限的设备。为了使 Firebase 身份验证发挥作用，设备必须成功通过 SafetyNet/Play 完整性 API 检查。
4. 如果 VPN 已启用，请将其关闭。对于 Telegram 的服务器来说，连接区域与您的手机号码国家/地区代码关联的区域相匹配可能很重要。同样，如果您处于漫游状态，请尝试通过位于您 SIM 卡所在区域或至少位于为您的电话号码发放的国家/地区的 VPN 进行连接。

## 3.3.如果代码仍然没有到达怎么办？

如果您已满足上述所有要求，但代码仍未到达，请尝试以下操作：

1. 如果您有 Android 设备，请尝试通过其他应用程序登录。有两个官方应用程序：Telegram 和[Telegram X](https://play.google.com/store/apps/details?id=org.thunderdog.challegram "电报X")，Telegram 有两个选项：[Google Play 版本](https://play.google.com/store/apps/details?id=org.telegram.messenger "谷歌播放版本")和[直接版本](https://telegram.org/android "直接版")。尝试所有三个应用程序。
2. 尝试在其他设备上登录您的帐户。如果您使用的是其他人的设备，请记住在登录屏幕上禁用联系人同步：否则，其他人电话簿中的所有联系人都将保存在您的帐户中，并且将来您会经常看到与你不认识的人。
3. 如果您的 Android 设备没有收到代码，请尝试 iOS 设备。
4. 尝试切换到不同类型的互联网连接：如果您连接到 Wi-Fi，请切换到移动数据，反之亦然。
5. 如果您的 Android 设备具有反垃圾邮件过滤器，请检查系统是否将来自 Telegram 的电话或短信视为垃圾邮件。
6. 尝试阻止 Telegram 应用程序访问短信和通话：有时，当应用程序尝试自行拦截授权代码时，它会失败。

# 4\. 该应用程序不提供通过电话或短信发送代码的功能

如果在另一个会话中发送授权代码，Telegram 移动应用程序会显示“未获取代码？”代码输入屏幕上的按钮。通常，当您单击它时，应用程序会通知您代码已通过电话或短信发送。但是，有时服务器拒绝将代码发送到具有指定电话号码的 SIM 卡，并且应用程序会建议指定其他电话号码或联系 Telegram 支持团队。

![](https://tginfo.me/wp-content/uploads/2023/11/596f9fdc5dd1b8f68da9717-498x1024.png)

@tginfo 的编辑团队没有关于在这种情况下向 Telegram 发送信件效果如何的数据。我们建议您仍然通过单击“帮助”按钮来发送信件，但不要等到以电话或短信形式发送代码开始在此应用程序中工作，而是尝试自己解决问题：使用另一个应用程序（一定是[官方的](https://telegram.org/apps "官方的")！）或其他设备。

# 5\. 关于授权问题，还可以如何联系 Telegram？

Telegram 官方常见问题解答提到了两种就授权相关问题联系 Telegram 管理部门的方法。

在“ [Telegram 支持](https://telegram.org/faq#telegram-support "电报支持")”部分，有一个指向[https://telegram.org/support](https://telegram.org/support)表格的链接，并注明“如果您无法登录您的帐户，请使用此表格。”

## 如何在没有电话号码的情况下获取旧 Telegram 账户
您可以使用以下任一方法来恢复旧的 Telegram 帐户，无需电话号码或短信验证码。

### 方法一：扫描二维码

如果您已经在智能手机上登录 Telegram，那么将新设备添加到 Telegram 中是一件轻而易举的事情。您可以扫描新设备上显示的二维码来登录您的 Telegram 帐户。

以下是需要遵循的步骤：

**步骤 1：**在已登录的手机上打开**Telegram应用程序。**

**第 2 步：**点击左上角的**三条水平线，然后选择****“设置”**。

[

![电报应用程序设置](https://www.gizmochina.com/wp-content/uploads/2024/03/Telegram-app-settings-945x1024.png)

](https://www.gizmochina.com/wp-content/uploads/2024/03/Telegram-app-settings-945x1024.png)

**步骤3：**选择**设备**并点击**链接桌面设备**。

[

![在 Telegram 中链接新设备](https://www.gizmochina.com/wp-content/uploads/2024/03/Linking-a-new-device-in-Telegram-945x1024.png)

](https://www.gizmochina.com/wp-content/uploads/2024/03/Linking-a-new-device-in-Telegram-945x1024.png)

**步骤 4：**在您想要登录 Telegram 帐户的设备上访问[web.telegram.org 。](https://web.telegram.org/)

**第 5 步：**使用您的智能手机扫描二维码。

等待几秒钟让 Telegram 加载您的聊天和消息。

### 方法 2：使用 Telegram 上收到的验证码

如果您在设备上有一个活动的 Telegram 会话，那么即使您没有电话号码，也不必担心登录到其他设备。

如果您已经登录Telegram账户，平台会在Telegram上发送验证码，您可以使用它在不同的设备上登录您的账户。

**步骤 1：**在您想要登录帐户的设备上打开 Telegram 应用程序或[Telegram Web 。](https://web.telegram.org/)

**第 2 步：**输入您的电话号码。

**步骤 3：**检查您的 Telegram 帐户（您已登录的帐户）以获取验证码。

**第四步：**输入验证码。

您应该已经在新设备上登录了您的 Telegram 帐户。  

### 方法 3：联系 Telegram 支持

如果您无法使用旧电话号码，并且任何设备或浏览器上都没有登录 Telegram 会话，请联系[Telegram 支持](https://telegram.org/support)寻求帮助。

联系 Telegram 支持人员进行帐户恢复更像是一种希望，而不是一种经过验证的方法。不要忘记提及可以验证您帐户真实性的详细信息；只有这样您才有机会恢复。

## 避免将来丢失 Telegram 帐户的技巧

**提示1：定期登录**

如果您在特定时间内未登录 Telegram，Telegram 将自动删除您的帐户。默认情况下，此自毁计时器为 6 个月。但您最多可以将其设置为 1 年。因此，请定期使用您的 Telegram 帐户以避免自毁。

如果您的 Telegram 帐户被自动删除，下次您尝试登录时将拥有一个新的 Telegram 帐户。您将丢失所有消息、照片、视频、群组和频道。

**提示#2：保护您的电话号码**

保护好您的电话号码至关重要。您可能会失去对许多应用和服务的访问权限，而不仅仅是 Telegram。 

**提示#3：卸载前先在其他地方登录**

如果您没有电话号码，最好在卸载 Telegram 应用程序或将设备恢复出厂设置之前在其他设备上登录您的 Telegram 帐户（使用[方法 1](https://www.gizmochina.com/how-to/get-old-telegram-account-without-phone-number/#Method_1_Scan_the_QR_Code)或[方法 2 ）。](https://www.gizmochina.com/how-to/get-old-telegram-account-without-phone-number/#Method_2_Use_the_Verification_Code_Received_on_Telegram)

希望本指南能帮助您恢复旧 Telegram 帐户。您找回旧 Telegram 帐户了吗？请在下方评论中分享您的想法或任何问题（如果有）。

## **常见问题解答：**

**1\. 没有电话号码的情况下我怎样才能找回我的 Telegram？**

您可以扫描二维码，在没有电话号码的其他设备上登录您的 Telegram 帐户。

**2\. 如何访问我的旧电报账户？**

您可以通过短信验证或扫描二维码轻松访问您的旧 Telegram 帐户。您可以使用活动会话在 Telegram 上获取验证码。



