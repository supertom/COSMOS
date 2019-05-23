---
layout: news_item
title: 'Protocols'
date: 2019-05-23 08:00:00 -0700
author: jmthomas
categories: [post]
---
## Protocols
Protocols were introduced into COSMOS in version 4.0.0. Protocols consist of the code that make sense of the incoming byte stream before it is turned into packets. They work hand in hand with the COSMOS interface that connects to the target, whether it is TCP/IP, UDP, or serial. The new COSMOS protocol system makes it possible to add and layer protocols into a COSMOS interface.

### Built-in Protocols
COSMOS comes with a number of built-in protocols that are used directly with the COSMOS provided interfaces. In fact, when you declare your interface you're required to specify a protocol. For example, the following code declares a TCP/IP client with a LENGTH protocol.

```
INTERFACE INTERFACE_NAME tcpip_client_interface.rb localhost 8080 8081 10.0 nil LENGTH 0 16 0 1 BIG_ENDIAN 4 0xBA5EBA11
```

The built-in protocols are described fully on the [Protocols](/docs/protocols) page and also mentioned on the [Interfaces](/docs/interfaces/#protocols) page.

### Custom Protocols
The built-in protocols are enough to support almost all of the data streams that you'll probably encounter from a target. However, sometimes you need to massage the data a little by stripping off data or adding headers. This is when you should create a custom protocol.

#### Removing Data



If you have a question which would benefit the community you can ask on [StackOverflow](https://stackoverflow.com/questions/ask?tags=cosmos;ruby) or if you find a bug or want a feature please use our [Github Issues](https://github.com/BallAerospace/COSMOS/issues). If you would like more information about a COSMOS training or support contract please contact us at <cosmos@ball.com>.
