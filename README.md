# How remove Android Browser Bloatware?
now can use tools for disable/remove bloatware (unwanted program) from your Android Browser use MDM (managed profile / work profile / profile owner / Device Owner) >> Apps Management >> choose Apps (Brave/Edge) >> Managed Configuration.

what tools for setup MDM (managed profile / work profile / profile owner / Device Owner)?<br/>
in below is Free and Open Source tools for setup MDM:<br/>
- [TestDPC](https://github.com/googlesamples/android-testdpc) (Official by Google)
- [Owndroid](https://github.com/BinTianqi/OwnDroid) (TestDPC fork, but better UI & UX, easy to use)

**Note:**
- first setup MDM need logged out all account from your Android device
- Managed Configuration is not limited to browser applications such as Brave and Edge only, it can be implemented to all applications that support Group Policy, here it only contains specific settings for debloating Brave and Edge.

<br/><br/>
# Remove Brave Android Browser Bloatware
- Brave AI Leo Chat
- Brave News
- Brave VPN
- Brave Rewards
- Brave Wallet
- and other Policy settings for increase Brave Privacy.

<img width="676" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Brave2.png" />

**Brave Specific Policy Settings**<br/>
key name list and values setup for Managed Configuration for Brave:
|Name|Key Name|Policy Values|
|----|--------|-------------|
|Settings for Google's AI Mode integrations in the address bar and New Tab page search box.|AIModeSettings|1|
|Enable AI Chat|BraveAIChatEnabled|false|
|Disable Brave News|BraveNewsDisabled|true|
|Enable Privacy Preserving Product Analytics (P3A)|BraveP3AEnabled|false|
|Enable Brave Playlist|BravePlaylistEnabled|false|
|Disable Brave Rewards|BraveRewardsDisabled|true|
|Enable Stats Usage Ping|BraveStatsPingEnabled|false|
|Disable Brave Talk|BraveTalkDisabled|true|
|Disable Brave VPN|BraveVPNDisabled|true|
|Disable Brave Wallet|BraveWalletDisabled|true|
|Enable Web Discovery|BraveWebDiscoveryEnabled|false|
|Brave cloud policy overrides Platform policy.|CloudPolicyOverridesPlatformPolicy|false|
|Control HTTPS upgrade behavior|DefaultBraveHttpsUpgradeSetting|3|
|Default idle detection setting|DefaultIdleDetectionSetting|2|
|Control use of JavaScript JIT|DefaultJavaScriptJitSetting|2|
|Allow reporting of domain reliability related data|DomainReliabilityAllowed|false|
|Specifies whether in-product Brave surveys are shown to users.|FeedbackSurveysEnabled|false|
|Settings for Chrome Finds|FindsSettings|2|
|Settings for Gemini integration|GeminiSettings|1|
|Settings for GenAI local foundational model|GenAILocalFoundationalModelSettings|1|
|Enable reporting of usage and crash-related data|MetricsReportingEnabled|false|
|Enable network prediction|NetworkPredictionOptions|0|
|Enable content sharing with Google AI Mode and Lens integrations|SearchContentSharingSettings|1|<br/>

official source from [Brave Group Policy](https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy).<br/>

<br/><br/>
# Disable Copilot Microsoft Edge Android and setup other settings
disable Copilot Microsoft Edge version 148 and above which currently cannot be completely turned off from settings.

<img width="324" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Edge.png" />

Copilot AI can read any tab what user open, any word what user typing.
and Microsoft Implemented different DMCA & GDPR to different language/region.
for different language some settings not available, or hidden intentionally by Microsoft.

<img width="432" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Edge_2.png" />

since Edge Android Browser hidden their some settings (for example can't change directly from Edge settings for always HTTPS and setup DNS resolver), with MDM user also can setup that settings via the Managed Configuration to enforce specific settings and increase privacy Edge Browser in Android.


**Microsoft Edge Android Browser Specific Policy Settings**<br/>
key name list and values setup for Managed Configuration for Edge:
|Name|Key Name|Policy Values|
|----|--------|-------------|
|Enable the Copilot new tab page|CopilotNewTabPageEnabled|false|
|Default geolocation setting|DefaultGeolocationSetting|2|
|Default idle detection setting|DefaultIdleDetectionSetting|2|
|Control use of JavaScript JIT|DefaultJavaScriptJitSetting|2|
|Control the mode of DNS-over-HTTPS|DnsOverHttpsMode|secure|
|Specify URI template of desired DNS-over-HTTPS resolver|DnsOverHttpsTemplates|https://cloudflare-dns.com/dns-query<br/>/ other dns resolver|
|Allow download restrictions|DownloadRestrictions|0|
|Enable Copilot|EdgeCopilotEnabled|false|
|Enforce Google SafeSearch|ForceGoogleSafeSearch|false|
|Force minimum YouTube Restricted Mode|ForceYouTubeRestrict|0|
|Settings for GenAI local foundational model|GenAILocalFoundationalModelSettings|1|
|Allow HTTPS-Only Mode to be enabled|HttpsOnlyMode|force_enabled|
|Enable network prediction|NetworkPredictionOptions|0|
|Prevent bypassing Microsoft Defender SmartScreen prompts for sites|PreventSmartScreenPromptOverride|false|
|Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads|PreventSmartScreenPromptOverrideForFiles|false|
|Enable Microsoft Defender SmartScreen DNS requests|SmartScreenDnsRequestsEnabled|false|
|Configure Microsoft Defender SmartScreen|SmartScreenEnabled|false|
|Configure Microsoft Defender SmartScreen to block potentially unwanted apps|SmartScreenPuaEnabled|false|

official source from [Microsoft Group Policy](https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy).<br/>
