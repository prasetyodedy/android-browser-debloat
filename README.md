# How remove Android Browser Bloatware?
Now can use tools for disable/remove bloatware (unwanted program) from your Android Browser use MDM (Mobile Device Management) / Policy Control Tools apps and set as `managed profile / work profile / profile owner / Device Owner`<br/> 

what is MDM / Policy Control Tools apps for set as `managed profile / work profile / profile owner / Device Owner`?<br/>
in below is Free and Open Source tools for MDM setup:<br/>
- [TestDPC](https://github.com/googlesamples/android-testdpc) (Official by Google)
- [Owndroid](https://github.com/BinTianqi/OwnDroid) (TestDPC fork, with better UI & UX, easy to use)

How implement specific policy?<br/>
MDM / Policy Control Apps >> Apps Management >> choose Apps (Brave/Edge) >> Managed Configuration.

**Note:**
- first setup MDM need logged out all account from your Android device
- Managed Configuration is not limited to browser applications such as Brave and Edge only, it can be implemented to all applications that support Group Policy, in here only focused for specific settings about debloating Brave and Edge.

<br/><br/>
# Remove Brave Android Browser Bloatware
- Brave AI Leo Chat
- Brave News
- Brave VPN
- Brave Rewards
- Brave Wallet
- and other Policy settings for increase Brave Privacy.

<img width="676" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Brave.png" />

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
|Enable automatic HTTPS upgrades|HttpsUpgradesEnabled|true|
|Enable reporting of usage and crash-related data|MetricsReportingEnabled|false|
|Enable network prediction|NetworkPredictionOptions|0|
|Enable Safe Browsing Extended Reporting|SafeBrowsingExtendedReportingEnabled|false|
|Enable content sharing with Google AI Mode and Lens integrations|SearchContentSharingSettings|1|<br/>

official source and credit from [Brave Group Policy](https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy).<br/>
**Note:** if missing some Policy Key Name in above or not found, that Key Name maybe already deprecated, or Brave change their Policy Key Name.

In addition to the Managed Configuration with Group Policy, which not invicible in normal settings. also recommended for Brave Browser user setup a configuration in below directly from Brave Browser settings:
- Settings >> Brave Shields & privacy >> Allow app links to open in apps outside of Brave (set to 'disable')
- Settings >> Privacy Report >> Privacy Report Notification "Sends a weekly privacy report" (set to 'disable')
- Settings >> Site settings >> Autoplay (set to 'Not allowed')

Also recommended for Brave user setup this flags:
|flags|description|
|-----|-----------|
|chrome://flags/#search-in-settings|for easy find exact settings|
|chrome://flags/#brave-origin|disable brave origin menu from settings|

In addition to the settings I mentioned above, Brave Browser already has default well-managed settings (such as disabling third-party cookies, good default ad-blocking filter rules + region-specific filter rules, and so on). now Brave ready for use, no need more change setup, for other settings user can customize by yourself.

<br/><br/>
# Disable Copilot Microsoft Edge Android and setup other settings
~~disable Copilot Microsoft Edge version 148 and above which currently cannot be completely turned off from settings.
Copilot AI can read any tab what user open, any word what user typing.~~<br/>
**Update:** now in Edge Browser v149.0.4022.67 Microsoft bring back feature for disable Copilot directly from Edge Settings

<img width="341" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Copilot.png" />

but if want disable Copilot entirely, use Policy Group with Managed Configuration.

<img width="240" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Copilot2.png" />

Microsoft Implemented different Policy (Data Protection and Privacy Rights / GDPR) to different region - language specific. some settings not available for different region or language specific and hidden intentionally by Microsoft (for example can't change directly from Edge settings for always use HTTPS and setup DNS resolver), with MDM user also can enforce settings and other setup via the Managed Configuration for increase privacy Edge Browser in Android.<br/>

**Microsoft Edge Android Browser Specific Policy Settings.**<br/>
key name list and values setup for Managed Configuration for Edge:
|Name|Key Name|Policy Values|
|----|--------|-------------|
|Enable the Copilot new tab page|CopilotNewTabPageEnabled|false|
|Default geolocation setting|DefaultGeolocationSetting|2|
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
|Prevent bypassing Edge Website Typo Protection prompts for sites|PreventTyposquattingPromptOverride|false|
|Enable Microsoft Defender SmartScreen DNS requests|SmartScreenDnsRequestsEnabled|false|
|Configure Microsoft Defender SmartScreen|SmartScreenEnabled|false|
|Configure Microsoft Defender SmartScreen to block potentially unwanted apps|SmartScreenPuaEnabled|false|

official source and credit from [Microsoft Group Policy](https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy).<br/>
**Note:** if missing some Policy Key Name in above or not found, that Key Name maybe already deprecated, or Microsoft change their Policy Key Name.

In addition to the Managed Configuration with Group Policy, which not invicible in normal settings. also recommended for Microsoft Edge user setup a configuration in below directly from Edge Browser settings:
- Settings >> Privacy and security >> Diagnostic data >> Optional diagnostic data (set to 'disable')
- Settings >> Microsoft services >> Improve quality of shortcuts on homepage (set to 'disable')
- Settings >> Search >> Show me search and site suggestions using my typed characters (set to 'disable')
- Settings >> Appearance and layout >> Theme and Wallpaper (optional. if like, keep it enable and customize)
- Settings >> New tab page >> Weather (optional. if like, keep it enable)
- Settings >> New tab page >> Continue browsing where I left off (enable)
- Settings >> Site settings >> Site permissions >> Third-party cookies (set to 'disable')
- Settings >> Site settings >> Block ads (optional. if like, enable in-built Block ads and disable 'Acceptable Ads') but recommended use [uBlock Origin](https://microsoftedge.microsoft.com/addons/detail/ublock-origin/odfafepnkmbhccpbejgmiehpchacaeak) extension for better ads blocking.

Home Page settings, tap hamburger menu on top right
- Show sponsored shortcuts (set to 'disable')
- Cards >> Edge tips (set to 'disable')
- Show feed (optional. if like read news, keep it enable)
<img width="456" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Edge.png" />

In addition to the settings I mentioned above, Edge Browser ready for use, no need more change setup, for other settings user can customize by yourself.


**Change Language Edge Browser Android.**<br/>
basic feature for change language isn't available in Edge settings, Edge browser uses the language autodetection applied to the Android System. for change Edge browser language, can enforce with ADB Shell or with apps [Language Selector](https://github.com/VegaBobo/Language-Selector) (vegabobo.languageselector) + [Shizuku](https://github.com/rikkaapps/shizuku).

ADB Shell command for change language:<br/>
`adb shell cmd locale set-app-locales com.example.app --user current --locales "<language_code>-<country_code>"`

for example change Microsoft Edge to english - United States<br/>
`adb shell cmd locale set-app-locales com.microsoft.emmx --user current --locales "en-US"`
