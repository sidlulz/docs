---
layout: default
title: Twitch
menu: Integrations
num: 2
permalink: /integrations/twitch
type: fullpage
---

SAMMI can connect to your Twitch account, remotely control it and listen to events in your stream.

#### Link a single Twitch account
We need to authorize SAMMI to interact with your Twitch account.

1. In SAMMI click on **Twitch Connections** button.
2. Click on **Link Streamer Account** which should open a new browser window and redirect you to Twitch to authorize SAMMI.
3. Press **Authorize** and wait to be redirected again to see `All good, you can go back to SAMMI now` message in your browser.
4. Back in SAMMI you should now see your Twitch account in the list!


   {% include video.html w="75" src="link-twitch.mp4" alt="Linking a Twitch account" %}

{% include alert.html text="You must relink your Twitch account every 60 days as that's when your token expires. SAMMI will automatically remind you to do so." type="warning" %}

**Linked Twitch account's settings:**

{% include image.html w="75" src="account-settings.png" alt="Active Twitch Connection" %}

- `Join chat under this name` - all your Twitch chat messages and whispers from SAMMI will be sent under this Twitch account's name
- `Join channel` - whether you want to join this Twitch account's chat and listen for chat messages
- `Listen for` - check all events you wish to listen for and received triggers for. Some events will be greyed out if you're not affiliate.
- `Revoke Token` - disconnect your Twitch account from SAMMI
- (only if affiliate) `Edit Channel Points` - allows you to create, modify and delete all your current channel points

**Twitch Connections General Settings**

{% include image.html w="75" src="account-settings2.png" alt="Active Twitch Connection" %}

- `Connect/Disconnect Twitch` - connect to Twitch to be able to receive and send chat messages, and listen to events
- `Auto connect to Twitch` - check this if you want SAMMI to automatically connect to Twitch once launched, otherwise you will have to press Connect Twitch button every time.
- `Copy Streamer URL` - if you would rather copy the URL instead of opening it in your default browser to link your account, you can use this option instead
- `Done` - click Done to save the settings


#### Link multiple Twitch accounts
You can link multiple Twitch accounts to SAMMI by following the same steps in [Link a single Twitch account](#linkasingletwitchaccount) section, but you will need to click 'Link Bot Account' instead of 'Link Streamer Account'.

This is useful if you want to use a different Twitch account to send Twitch chat messages from. It makes it easier for your viewers to tell the difference between you personally interacting with them and any automated messages you have set up in SAMMI.

{% include alert.html text="All Twitch chat messages will be sent from your Twitch account that is marked as <strong>Join chat under this name</strong> in the <code>Twitch Connections</code> menu. You can freely switch to a different account your messages will be sent from." type="danger" %}

**Listen to Twitch events from your alternate account(s)**\
SAMMI will automatically listen to all selected events and chat (if Join Channel is checked) from all your Twitch accounts.

{% include alert.html text="SAMMI doesn't have a way to tell where your Twitch triggers come from, be it your main or one of your alternate accounts." type="warning" %}

**Differences between Streamer Account and Bot Account options**\
The main differences between a Streamer Account and a Bot Account is the scopes that are automatically enabled for the respective accounts. Streamer accounts will have all scopes enabled by default, excluding 'Get Stream Key'. Bot accounts will have the follwing scopes:
- channel:moderate
- chat:edit
- chat:read
- whispers:edit
- whispers:read

Enabling **custom scopes** for your Streamer account is possible while you're in Dev Mode. In Dev Mode, click 'Advanced Scopes' and tick the scopes that you want to enable for the account. Note that this list in Advanced Scopes does NOT reflect what scopes you already have enabled. 

All changes to scopes require you to revoke your token, relinking and reauthorising your Twitch account. 

**Remember to specify channel name when using Twitch: Chat message command**\
If you've linked more than more Twitch account to SAMMI, you must specify the channel name in your [Twitch: Send Message]({{ "commands/twitch#sendchatmessage" | relative_url }}) command. Otherwise the message will be sent to your primary SAMMI account's channel (the one with `Join chat under this name` selected). NOTE: The channel name must be in all lowercase. Otherwise the message will not appear in chat until user refreshes their chat.

#### Listen to Twitch Events

Once you link your account(s), SAMMI automatically connects to Twitch PubSub and Twitch Chat (if you pressed Connect Twitch button) to listen to all selected Twitch events and Twitch chat.\
Learn more about all Twitch event triggers in our [Triggers-Twitch]({{ "triggers/twitch" | relative_url }}) section.


#### Send Twitch chat messages

SAMMI can natively send Twitch chat messages, whispers and moderation commands (if the linked account has the permissions) to any Twitch chat channel by using [Twitch: Send Message]({{ "commands/twitch#sendchatmessage" | relative_url }}) command.

See a list of all possible [Twitch chat mod commands](https://help.twitch.tv/s/article/chat-commands?language=en_US#AllMods).

#### Other Twitch Commands
Navigate to our [Commands-Twitch]({{ "commands/twitch" | relative_url }}) section to see all possible Twitch commands.
