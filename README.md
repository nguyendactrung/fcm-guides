# iOS Firebase Cloud Messaging

Deliver and receive messages and notifications on iOS.

<!-- TOC -->

- [Introduction](#introduction)
- [Key capabilities](#key-capabilities)
- [About FCM Messages](#about-fcm-messages)
  - [Message types](#message-types)
- [How it works?](#how-it-works)
- [Understanding Firebase Cloud Messaging on iOS](#understanding-firebase-cloud-messaging-on-ios)
- [FCM Server](#fcm-server)

<!-- /TOC -->

## Introduction

Using FCM, you can notify an iOS client app that new email or other data is available to sync. You can send notification messages to drive user re-engagement and retention.

## Key capabilities

| Capability    |     Explains  |
| ------------- |---------------|
| Send notification messages or data messages    | Send notification messages that are displayed to your user. Or send data messages and determine completely what happens in your application code. See Message types. |
| Versatile message targeting    | Distribute messages to your client app in any of 3 ways—to single devices, to groups of devices, or to devices subscribed to topics.      |
| Send messages from client apps | Send acknowledgments, chats, and other messages from devices back to your server over FCM’s reliable and battery-efficient connection channel. |

## About FCM Messages

Firebase Cloud Messaging (FCM) offers a broad range of messaging options and capabilities

### Message types

* Notification messages, sometimes thought of as "display messages." These are handled by the FCM SDK automatically.

```json
{
"message":{
    "token":"bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
    "notification":{
    "title":"Portugal vs. Denmark",
    "body":"great match!"
    }
}
}
```

> Notification messages have a predefined set of user-visible keys and an optional data payload of custom key-value pairs.

* Data messages, which are handled by the client app.

```json
{
  "message":{
    "token":"bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
    "data":{
      "Nick" : "Mario",
      "body" : "great match!",
      "Room" : "PortugalVSDenmark"
    }
  }
}
```

> Data messages have only custom key-value pairs. A message can transfer a payload of up to 4KB to a client app.

## How it works?

An FCM implementation includes two main components for sending and receiving:

* A trusted environment such as Cloud Functions for Firebase or an app server on which to build, target, and send messages and an iOS client app that receives messages.

* You can send messages via the Admin SDK or the HTTP and XMPP APIs. For testing or for sending marketing or engagement messages with powerful built-in targeting and analytics, you can also use the Notifications composer.

![](https://firebase.google.com/docs/cloud-messaging/images/messaging-overview.png)

## Understanding Firebase Cloud Messaging on iOS

## FCM Server