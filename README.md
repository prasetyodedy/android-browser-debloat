# How remove Android Browser Bloatware?
now can use tool for disable unwanted program from your Android Browser use MDM (managed profile / work profile / profile owner / Device Owner) >> Apps Management >> choose Apps (Brave/Edge) >> Managed Configuration.

what tools for setup MDM (managed profile / work profile / profile owner / Device Owner) in below is Free and Open Source tools for setup MDM:<br/>
- [TestDPC](https://github.com/googlesamples/android-testdpc) (Official by Google)
- [Owndroid](https://github.com/BinTianqi/OwnDroid) (TestDPC fork, but better UI & UX, easy to use)

**Note:** first setup MDM need logged out all account from your Android device

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
In addition to the MDM [TestDPC](https://github.com/googlesamples/android-testdpc) / [Owndroid](https://github.com/BinTianqi/OwnDroid), you can set these values via the Managed Configuration:
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
# Disable Copilot Microsoft Edge Android
disable Copilot Microsoft Edge version 148 and above which currently cannot be completely turned off from settings.

<img width="324" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Edge.png" />

Copilot AI can read any tab what user open, any word what user typing.
and Microsoft Implemented different DMCA & GDPR to different language/region.
for different language some settings not available, or hidden intentionally by Microsoft.

<img width="432" height="240" alt="Image" src="https://raw.githubusercontent.com/prasetyodedy/debloat-android-browser/refs/heads/main/screenshot/Edge_2.png" />
