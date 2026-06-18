# How to remove Android Browser Bloatware?
Users can utilize Mobile Device Management (MDM) or Policy Control Tools to disable and remove bloatware (unwanted features and programs) from Android browsers by provisioning the device as a `managed profile, work profile, profile owner, or device owner`.<br/> 

1. **What MDM / Policy Control Tools can be used to set up these profiles?**<br/>
Below are free and open-source tools for MDM setup:<br/>
   - [TestDPC](https://github.com/googlesamples/android-testdpc) (Official by Google)
   - [OwnDroid](https://github.com/BinTianqi/OwnDroid) (TestDPC fork, with better UI & UX, easy to use)

2. **How to implement a specific policy?**<br/>
MDM / Policy Control Apps >> Apps Management >> choose Apps (Brave/Edge) >> Managed Configuration.

3. **Why setting up group policy with managed configuration?**<br/>
Because there are some settings that are not visible in the normal settings, even making changes and some settings with `chrome://flags` has no effect and does not mean anything to Brave Browser / Edge Browser.<br/>
That's why as users, we can take advantage of the highest privileges of group policy set from managed configuration to apply some settings that users cannot change in the normal settings.

4. **Where to check known all available group policy key names for managed configuration?**<br/>
   - `chrome://policy`
   - in the Applications menu section within Managed Configuration of MDM Tools.
   - official documentation from developer/publisher, for example:
        - Brave Group Policy https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy
        - Microsoft Group Policy https://learn.microsoft.com/en-us/deployedge/microsoft-edge-policies

**Note:**
- Before setting up an MDM profile, users must log out of all active accounts from the Android device.
- And before starting MDM setup, the device does not have a second user (guest mode), not set up as a managed profile, and has not set up a private space.
- In here not explain how to provision the device as a `managed profile, work profile, profile owner, or device owner`. All documentation about setting up MDM is already on the [TestDPC](https://github.com/googlesamples/android-testdpc) and [OwnDroid](https://github.com/BinTianqi/OwnDroid) repo, if encounter any difficulties or issues when setting up MDM, please visit  https://deepwiki.com/BinTianqi/OwnDroid
- Managed Configuration is not limited to browser applications such as Brave and Edge only; it can be implemented for all applications that support Group Policy, but the focus here is on specific settings about Brave Browser and Edge Browser for Android.

<br/><br/>
# Remove Brave Android Browser Bloatware
How to remove:
- Brave AI Leo Chat
- Brave News
- Brave Firewall + VPN
- Brave Rewards
- Brave Wallet

And add other policy configurations to increase Brave Browser privacy.<br/>

<img width="1362" height="480" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Brave.png" />

**Brave Specific Policy Settings**<br/>
Key name list and values for Managed Configuration in Brave Browser:
|Name|Key Name|Policy Values|
|----|--------|-------------|
|Settings for Google's AI Mode integrations in the address bar and New Tab page search box.|AIModeSettings|1|
|Enable AI Chat|BraveAIChatEnabled|false|
|Configure Global Privacy Control|BraveGlobalPrivacyControlEnabled|true|
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
|Enable Touch to Search|ContextualSearchEnabled|false|
|Default Brave fingerprinting protection setting|DefaultBraveFingerprintingV2Setting|3|
|Control HTTPS upgrade behavior|DefaultBraveHttpsUpgradeSetting|3|
|Default idle detection setting|DefaultIdleDetectionSetting|2|
|Control use of JavaScript JIT|DefaultJavaScriptJitSetting|2|
|Allow reporting of domain reliability related data|DomainReliabilityAllowed|false|
|Specifies whether in-product Brave surveys are shown to users.|FeedbackSurveysEnabled|false|
|Settings for Chrome Finds|FindsSettings|2|
|Enforce Google SafeSearch|ForceGoogleSafeSearch|false|
|Settings for Gemini integration|GeminiSettings|1|
|Settings for GenAI local foundational model|GenAILocalFoundationalModelSettings|1|
|Allow HTTPS-Only Mode to be enabled|HttpsOnlyMode|force_enabled|
|Enable automatic HTTPS upgrades|HttpsUpgradesEnabled|true|
|Enable reporting of usage and crash-related data|MetricsReportingEnabled|false|
|Enable network prediction|NetworkPredictionOptions|0|
|Enable Safe Browsing Extended Reporting|SafeBrowsingExtendedReportingEnabled|false|
|Enable content sharing with Google AI Mode and Lens integrations|SearchContentSharingSettings|1|<br/>

official source and credit from the [Brave Group Policy](https://support.brave.app/hc/en-us/articles/360039248271-Group-Policy).<br/>
**Note:** If some Policy Key Names above are missing or can't be found, that Key Name may be already deprecated, or Brave has changed their Policy Key Name.

Besides setting up Managed Configurations via Group Policy, it is also recommended for users to configure the options below directly in the Brave Browser settings:
- Settings >> Brave Shields & privacy >> Allow app links to open in apps outside of Brave (set to 'disable')
- Settings >> Privacy Report >> Privacy Report Notification "Sends a weekly privacy report" (set to 'disable')
- Settings >> Site settings >> Autoplay (set to 'Not allowed')

Also recommended for Brave users to set up these flags:
|Flags|Value|Description|
|-----|-----|-----------|
|chrome://flags/#search-in-settings|enable|adds a search bar for easily finding specific internal settings|
|chrome://flags/#brave-origin|disable|disable the Brave Origin menu in settings|

In addition to the settings I mentioned above, Brave Browser has well-managed default settings, such as already disabling third-party cookies, enabling anti-fingerprinting, enabling built-in ad-blocking including region-specific filter rules, etc. Now Brave Browser is ready to use. No further setup changes are needed. Users can customize other settings themselves.

<br/><br/>
# Disable Copilot Microsoft Edge Android and setup other settings
~~Copilot AI in Microsoft Edge version 148 and above, currently cannot be completely disabling/turned off from settings, which Copilot AI always could read active tabs and text typed by the user in Edge Browser.~~<br/>
**Update:** now in Edge Browser v149.0.4022.67 Microsoft brings back the feature to disable Copilot directly from Edge Settings

<img width="682" height="480" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Copilot.png" />

However, to disable Copilot entirely, utilize Group Policies via Managed Configuration.

<img width="480" height="480" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Copilot2.png" />

Microsoft implements different policies (Data Protection and Privacy Rights / GDPR) for different regions and languages. Certain options are not available across different regional or language-specific locales, and are intentionally hidden by Microsoft (for example, users can't change settings directly from Edge Browser to enable HTTPS-only and set up a secure DNS resolver), by utilizing an MDM users can apply these and other settings through Managed Configurations to enhance Edge Browser privacy on Android devices.<br/>

**Microsoft Edge Android Browser Specific Policy Settings.**<br/>
key name list and values setup for Managed Configuration for Microsoft Edge Browser:
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
|EdgeDefaultHTTPS|EdgeDefaultHTTPS|true|
|Enforce Google SafeSearch|ForceGoogleSafeSearch|false|
|Force minimum YouTube Restricted Mode|ForceYouTubeRestrict|0|
|Settings for GenAI local foundational model|GenAILocalFoundationalModelSettings|1|
|Allow HTTPS-Only Mode to be enabled|HttpsOnlyMode|force_enabled|
|Enable automatic HTTPS upgrades|HttpsUpgradesEnabled|true|
|Enable network prediction|NetworkPredictionOptions|0|
|Prevent bypassing Microsoft Defender SmartScreen prompts for sites|PreventSmartScreenPromptOverride|false|
|Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads|PreventSmartScreenPromptOverrideForFiles|false|
|Prevent bypassing Edge Website Typo Protection prompts for sites|PreventTyposquattingPromptOverride|false|
|Enable Microsoft Defender SmartScreen DNS requests|SmartScreenDnsRequestsEnabled|false|
|Configure Microsoft Defender SmartScreen|SmartScreenEnabled|false|
|Configure Microsoft Defender SmartScreen to block potentially unwanted apps|SmartScreenPuaEnabled|false|

official source and credit from the [Microsoft Group Policy](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-policies).<br/>
**Note:** If some Policy Key Names above are missing or can't be found, that Key Name may be already deprecated, or Microsoft has changed their Policy Key Name.

Besides setting up Managed Configurations via Group Policy, it is also recommended for users to configure the options below directly in the Edge Browser settings:
- Settings >> Privacy and security >> Diagnostic data >> Optional diagnostic data (set to 'disable')
- Settings >> Microsoft services >> Improve quality of shortcuts on homepage (set to 'disable')
- Settings >> Search >> Show me search and site suggestions using my typed characters (set to 'disable')
- Settings >> Appearance and layout >> Theme and Wallpaper (optional. if liked, keep it enabled and customize)
- Settings >> New tab page >> Weather (optional. if liked, keep it enabled)
- Settings >> New tab page >> Continue browsing where I left off (select and activate this)
- Settings >> Site settings >> Site permissions >> Third-party cookies (set to 'disable')
- Settings >> Site settings >> Block ads (optional. if liked, enabled built-in Block ads and disable 'Acceptable Ads') but recommended to use [uBlock Origin](https://microsoftedge.microsoft.com/addons/detail/ublock-origin/odfafepnkmbhccpbejgmiehpchacaeak) extension for better ads blocking.

Home Page settings, tap hamburger menu on top right
- Show sponsored shortcuts (set to 'disable')
- Cards >> Edge tips (set to 'disable')
- Show feed (optional. if liked read news, keep it enabled)
<img width="912" height="480" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Edge.png" />

In addition to the settings I mentioned above, Edge Browser is ready to use. No further setup changes are needed. Users can customize other settings themselves.

**Change Language Edge Browser Android.**<br/>
The basic feature for changing language isn't available in Edge Browser settings. Edge Browser uses the language autodetection applied to the Android System. To change Edge Browser language, it can be enforced with ADB Shell or with apps [Language Selector](https://github.com/VegaBobo/Language-Selector) (vegabobo.languageselector) + [Shizuku](https://github.com/rikkaapps/shizuku).

ADB Shell Command for changing application language<br/>
`adb shell cmd locale set-app-locales com.example.app --user current --locales "<language_code>-<country_code>"`

Where provide info about language code and country code?
- [ISO 639-1 Code](https://www.loc.gov/standards/iso639-2/php/code_list.php) about Language code
- [ISO 3166 Alpha-2 code](https://www.iso.org/obp/ui/#search) about Country codes

for example changing Microsoft Edge languages to english - United States<br/>
`adb shell cmd locale set-app-locales com.microsoft.emmx --user current --locales "en-US"`
