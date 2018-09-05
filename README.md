# Get Started

Before you can make your first API Request, you will need to [Sign up](https://catapult.inetwork.com/beta/signup) for a free Voice & Messaging API account.

## v1 Base API URL

`https://api.catapult.inetwork.com/v1`

## v1 REST API Reference Index

| Resource                                                                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [`v1/account`](methods/account/account.md)                                      | Account API allows you to retrieve your current balance, transaction list, account type and all elements related to your platform account.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [`v1/applications`](methods/applications/applications.md)                       | The Applications resource lets you define call and message handling applications. You write an application on your own servers and have Bandwidth API send events to it by configuring a callback URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [`v1/availableNumbers`](methods/availableNumbers/availableNumbers.md)           | The Available Numbers resource lets you search for numbers that are available for use with your application.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| [`v1/bridges`](methods/bridges/bridges.md)                                      | The Bridges resource allows you to bridge two calls together allowing for two way audio between them. A common example is bridging an incoming phone call together with a outgoing phone call.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| [`v1/calls`](methods/calls/calls.md)                                            | The Calls resource lets you make phone calls and view information about previous inbound and outbound calls.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| [`v1/conferences`](methods/conferences/conferences.md)                          | The Conference resource allows you create conferences, add members to it, play audio, speak text, mute/unmute members, hold/unhold members and other things related to conferencing. Once a conference is created there is no timeout associated with it, i.e., the conference will stay in created state until it is explicitly terminated. After the last member of a conference is removed from it, the conference will be set automatically as completed.                                                                                                                                                                                                                                                                                                                                                                                      |
| [`v1/domains`](methods/domains/domains.md)                                      | A domain is a way to logically group endpoints. There is a 100 domain max. per account limit. Most use cases require using a single domain for all endpoints. The name of the domain will be part of a public DNS record. For that reason, we let the customer choose their domain names. Once a domain has been created, endpoints can be created and managed within the context of the domain. Because endpoints can only exist within the context of a domain, creating a domain is the first step in creating endpoints.                                                                                                                                                                                                                                                                                                                       |
| [`v1/endpoints`](methods/endpoints/endpoints.md)                                | An endpoint represents is an entity that can register with the Application Platform SIP Registrar and place and receive calls. This can be a device like a phone or a pad, or it can be a softphone on a computer.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| [`v1/errors`](methods/errors/errors.md)                                         | The Errors resource lets you see information about errors that happened in your API calls and during applications callbacks. This error information can be very helpful when you're debugging an application. Because error information can be large, and errors in the distant past are less useful than new ones, Bandwidth API limits the number of user errors it keeps.                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| [`v1/media`](methods/media/media.md)                                            | The Media resource lets you upload your media files to Bandwidth API servers so they can be used in applications without requiring a separate hosting provider. You can upload files up to 65MB and file storage is free for an unlimited number of files. Files you upload can only be accessed by you when you supply your API access token and secret. They are not available to anonymous users. Bandwidth API supports the Cache-Control header when you upload files.                                                                                                                                                                                                                                                                                                                                                                        |
| [`v1/messages`](methods/messages/messages.md)                                   | The Messages resource lets you send SMS/MMS messages and view messages that were previously sent or received.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| [`v1/numberInfo`](methods/numberInfo/numberInfo.md)                             | This resource provides a CNAM number info. CNAM is an acronym which stands for Caller ID Name. CNAM can be used to display the calling party's name alongside the phone number, to help users easily identify a caller. CNAM API allows the user to get the CNAM information of a particular number.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| [`v1/phoneNumbers`](methods/phoneNumbers/phoneNumbers.md)                       | The Phone Numbers resource lets you get phone numbers for use with your programs and manage numbers you already have.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [`v1/recordings`](methods/recordings/recordings.md)                             | Retrieve information about call recordings. The recording information retrieved by GET method contains only textual data related to call recording as described on Properties section. To properly work with recorded media content such as download and removal of media file, please access /media documentation. To learn about how to transcribe recordings, read the /recordings/{id}/transcriptions documentation.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| [`v1/recordings/{id}/transcriptions`](methods/transcriptions/transcriptions.md) | The Transcription resource lets you transcribe a voicemail recording. This resource can be either created automatically when the call property transcriptionEnabled is set to true, when call is created, or during the call by posting an event. The transcription is based on a call audio recording. By enabling/disabling call property recordingEnabled, a call can have more than one recording, so it's possible to have one or more transcriptions for each one of those recordings. When transcriptionEnabled is set to true all the recordings generated within that call are going to be transcribed, i.e, if you start to record a call, at any given time when the call is active, and then terminate the recording, the transcription resource will be automatically started for this recording; this process can happen many times. |

## v1 REST API Callback Reference Index

## v1 Messaging Events

| Event                            | Description                                                                       |
|:---------------------------------|:----------------------------------------------------------------------------------|
| [v1 SMS Event](apiCallbacks/sms.md) | Bandwidth API sends this event to the application when an SMS is sent or received |
| [v1 MMS Event](apiCallbacks/mms.md) | Events sent to your server for inbound and outbound MMS messages.                 |

## Voice Events

| Event                                                             | Description                                                                                                                                                                                               |
|:------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Answer Event](apiCallbacks/answer.md)                            | Bandwidth API sends this message to the application when the call is answered.                                                                                                                            |
| [Audio File Playback Events](apiCallbacks/audio.md)               | Bandwidth API sends this message to the application when audio file playback is started or done playing.                                                                                                  |
| [CallTimeout Event](apiCallbacks/timeout.md)                      | Bandwidth API sends this message to the application when the call is not answered until the specified timeout.                                                                                            |
| [Conference Event](apiCallbacks/conf.md)                          | Bandwidth API sends this event to the application when a conference is created or completed.                                                                                                              |
| [Conference Audio File Playback Event](apiCallbacks/confAudio.md) | Bandwidth API sends this message to the application when audio playback has started or is done (stopped) in a conference. Note: For playback event in conference member, use the call playback event.     |
| [Conference Member Event](apiCallbacks/confMember.md)             | Bandwidth API sends this message to the application when a conference member has joined / left the conference or when it as muted or put on hold.                                                         |
| [Conference Speak Event](apiCallbacks/confSpeak.md)               | Bandwidth API sends this message to the application when text-to-speech speaking has started or is done (stopped) in a conference. Note:— For speak event in conference member, use the call speak event. |
| [DTMF Event](apiCallbacks/dtmf.md)                                | Bandwidth API sends this message to the application when it receives number pad tone signals during a call.                                                                                               |
| [Gather Event](apiCallbacks/gather.md)                            | Bandwidth API generates a gather event when the gather command completes in a call.                                                                                                                       |
| [Incoming Call Event](apiCallbacks/incomingCall.md)               | Bandwidth API sends this message to the application when an incoming call arrives. For incoming call the callback set is the one related to the Application associated with the called number.            |
| [Hangup Event](apiCallbacks/hangup.md)                            | Bandwidth API sends this message to the application when the call ends.                                                                                                                                   |
| [Recording Event](apiCallbacks/recording.md)                      | Bandwidth API sends this event to the application when an the recording media file is saved or an error occurs while saving it.                                                                           |
| [Reject Event](apiCallbacks/reject.md)                            | Bandwidth API sends this message to the application when the call is rejected.                                                                                                                            |
| [Speak Event](apiCallbacks/speak.md)                              | Bandwidth API sends this message to the application when text-to-speech starts or stops.                                                                                                                  |
| [Transcription Event – BETA](apiCallbacks/transcription.md)       | Bandwidth API sends this event to the application when a transcription is terminated or an error occurs while processing it.                                                                              |

### BXMLVerbs

| Verb                                        | Description                                                                                                                                                                         |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [`<Gather>`](verbs/gather.md)               | The Gather verb is used to collect digits for some period of time.                                                                                                                  |
| [`<Hangup>`](verbs/hangup.md)               | The Hangup verb is used to hangup current call.                                                                                                                                     |
| [`<PlayAudio>`](verbs/playAudio.md)         | The PlayAudio verb is used to play an audio file in the call.                                                                                                                       |
| [`<Pause>`](verbs/pause.md)                 | The Pause verb is used to pause the execution of an ongoing BXML document.                                                                                                          |
| [`<Record>`](verbs/record.md)               | The Record verb allows call recording. At the end of the call, a call recording event containing the media with recorded audio URL is generated                                     |
| [`<Redirect>`](verbs/redirect.md)           | The Redirect verb is used to redirect the current XML execution to another URL.                                                                                                     |
| [`<SendDtmf>`](verbs/sendDtmf.md)           | The SendDtmf verb is used to is used to send digits on a live call.                                                                                                                 |
| [`<SpeakSentence>`](verbs/speakSentence.md) | The SpeakSentence verb is used to convert any text into speak for the caller.                                                                                                       |
| [`<Transfer>`](verbs/transfer.md)           | The Transfer verb is used to transfer the call to another number.                                                                                                                   |

### BXML Callbacks

BXML events are HTTP messages that are sent to your application server to notify you of activity related to your Bandwidth resources during a BXML usage.

| Event                                             | Description                                                                                                                     |
|:--------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------|
| [Answer Event](callBacks/answer.md)               | Bandwidth API sends this message to the application when the call is answered.                                                  |
| [Gather event](callBacks/gather.md)               | Bandwidth API generates a gather event when the gather command completes in a call.                                             |
| [Hangup Event](callBacks/hangup.md)               | Bandwidth API sends this message to the application when the call ends.                                                         |
| [Recording event](callBacks/recording.md)         | Bandwidth API sends this event to the application when an the recording media file is saved or an error occurs while saving it. |
| [Transcription event](callBacks/transcription.md) | Bandwidth API sends this event to the application when the recording media file is transcribed if requested.                    |
| [Redirect event](callBacks/redirect.md)           | Bandwidth API sends this event to the application when a `<Redirect>` is requested                                              |
| [Transfer Complete Event](callBacks/transfer.md)  | Bandwidth API sends this event to the application when the `<Transfer>`is complete                                              |

## Error Codes
| Type                         | Description                                                                |
|:-----------------------------|:---------------------------------------------------------------------------|
| [Rate Limits](rateLimits.md) | Every endpoint is rate limited, Calls and Messages are handled differently |
| [HTTP Errors](errors.md)     | Learn about the different errors that you may encounter using the API      |

---
