# Bandwidth Building Blocks

Here are some common tasks used to build up your full-featured Voice & Messaging application.

### Account Setup

| Building Block                                              | Description                                                                               | Difficulty |
|:------------------------------------------------------------|:------------------------------------------------------------------------------------------|:-----------|
| [Receive Messages and Calls](./incomingCallandMessaging.md) | Learn how to setup your account so you can receive incoming phone calls and text messages | Moderate   |

### Phone Numbers Building Blocks

| Building Block                                   | Description                                                                                   | Difficulty |
|:-------------------------------------------------|:----------------------------------------------------------------------------------------------|:-----------|
| [Get a Number](./buytn.md)                       | Learn how to order a phone number                                                              | Beginner   |
| [Import Dashboard Numbers](./importDashboard.md) | Learn how to import your Bandwidth Dashboard Phone Numbers to use with Voice & Messaging APIs | Advanced   |

### Voice Building Blocks

| Building Block                                           | Description                                                                                                                                                                                                                                                                                        | Difficulty |
|:---------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------|
| [Create outbound call](./outboundCall.md)                | Learn how to create outbound calls and what [callbacks](https://dev.bandwidth.com/ap-docs/apiCallbacks/voiceEvents.html) to expect                                                                                                                                                                  | Beginner   |
| [Play Audio](./playAudio.md)                             | Learn how to play an audio file in a [call](https://dev.bandwidth.com/ap-docs/methods/calls/calls.html), [conference](https://dev.bandwidth.com/ap-docs/methods/conferences/conferences.html), & [bridge](https://dev.bandwidth.com/ap-docs/methods/bridges/bridges.html)                             | Moderate   |
| [Speak Sentence](./speakSentence.md)                     | Learn how to use 'text-to-speech' (TTS) to speak a sentence in a [call](https://dev.bandwidth.com/ap-docs/methods/calls/calls.html), [conference](https://dev.bandwidth.com/ap-docs/methods/conferences/conferences.html), & [bridge](https://dev.bandwidth.com/ap-docs/methods/bridges/bridges.html) | Moderate   |
| [Record a Call](./recordCall.md)                         | Learn how to manage recordings                                                                                                                                                                                                                                                                     | Moderate   |
| [Create Gather (collect digits/dtmf)](./createGather.md) | Learn how to collect button presses on a phone call                                                                                                                                                                                                                                                | Moderate   |
| [Forward a call](./forwardACall.md)                      | Learn how to forward an incoming call to another phone number                                                                                                                                                                                                                                      | Moderate   |
| [Screen a call before forwarding](callScreen.md#top)         | Learn how to screen a call by prompting the caller to speak their name before forwarding                                                                                                                                                                                                           | Moderate   |
| [Conference Call](./conferenceCall.md)                   | Learn how to create and manage a [conference call](https://dev.bandwidth.com/ap-docs/methods/conferences/conferences.html)                                                                                                                                                                          | Moderate   |
| [Voicemail - NodeJS](./voicemail.md)                     | Learn how to setup a simple voicemail system with NodeJS                                                                                                                                                                                                                                           | Moderate   |
| [Configure SIP & Softphone](./sip.md)                    | Learn how to configure Bandwidth to handle SIP calls                                                                                                                                                                                                                                               | Moderate   |
| [WebRTC](./webrtc.md)                                    | Learn how to use Bandwidth SIP and WebRTC ⚠️ Currently unsupported ⚠️                                                                                                                                                                                                                              | Moderate   |
| [For Mobile Apps](./acrobits.md)                         | Learn how to configure Bandwidth for Mobile Applications                                                                                                                                                                                                                                           | Advanced   |
| [Setup Dashboard for Network Bridge](./networkBridge.md) | Learn how to link other API providers and Bandwidth's Phone Number Dashboard                                                                                                                                                                                                                       | Advanced   |

### Messaging Building Blocks

| Building Block                                           | Description                                                                                                                                                                              | Difficulty |
|:---------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------|
| [Send SMS/MMS](./sendSMSMMS.md)                          | Learn how to send both a SMS and MMS (multimedia) [message](https://dev.bandwidth.com/ap-docs/methods/messages/postMessages.html)                                                         | Beginner   |
| [Send SMS with Delivery Receipt](./smsDLR.md)            | Learn how to send a [text message](https://dev.bandwidth.com/ap-docs/methods/messages/postMessages.html) with delivery and error notifications                                            | Moderate    |
| [Hosted Messaging Getting Started](./hostedMessaging.md) | Learn how to enable messaging on non-bandwidth phone numbers ⚠️ Requires a Bandwidth Phone Number Dashboard Account, [contact sales](mailto:letstalk@bandwidth.com) for more information | Advanced   |
