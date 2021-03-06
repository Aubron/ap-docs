# Messages
The Messages resource lets you send SMS/MMS messages and view messages that were previously sent or received.

<aside class="alert general small">
<p>
Read More about Messaging in the <a href="https://dev.bandwidth.com/faq/#messaging">FAQ</a>
</p>
</aside>



### Base URL

`https://api.catapult.inetwork.com/v1/users/{userId}/messages`

### Capabilities

| Verb                           | Path                                                                 | about                           |
|:-------------------------------|:---------------------------------------------------------------------|:--------------------------------|
| <code class="get">GET</code>   | [`/v1/users/{userId}/messages`](getMessages.md)                      | Get a list of previous messages |
| <code class="post">POST</code> | [`/v1/users/{userId}/messages`](postMessages.md)                     | Send message                    |
| <code class="get">GET</code>   | [`/v1/users/{userId}/messages/{messageId}`](getMessagesMessageId.md) | Get information about a message |
| <code class="patch">PATCH</code> | [`/v1/users/{userId}/messages/{messageId}`](redactMessageText.md)    | Redact text on a message        |

### Receive Incoming Messages
To receive [callbacks](../../apiCallbacks/messagingEvents.md) for incoming text messages (both SMS and MMS). You need to have:

* A [Bandwidth Application](../applications/applications.md) configured to send callbacks to your server.
* Assign the [phone number](../phoneNumbers/postPhoneNumbersNumberId.md) to that application.
* Use [SMIL](https://en.wikipedia.org/wiki/Synchronized_Multimedia_Integration_Language)  as an xml media attachment to control message presentation. 
