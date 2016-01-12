---
layout: post
title: "All about MQTT protocol"
date: 2016-01-12 21:52:00
tags: mqtt
---
# Summary
MQTT is a publish-subscribe messaging protocol, designed for devices with low resources and small bandwidth available.
It's widely used in "Machine to Machine" and "Internet of Things" communication.
Each client is connected to a central server, called broker. The broker manages the dispatch of messages. Messages are published by clients on different
hierarchical topics, and received only by clients who subcribed to the particular topic. Examples of topics are "/device/sensor", "das-sade321/asds da/".

Topics cannot contain the characters `+` `#` and `/` since they have special meanings. The forward slash `/` is used as level separator.
The `+` is a wildcard used in subscriptions and it means "one level".
The `#` is a wildcard used in  subscriptions and it means "any number of levels".

The protocol itself [does not specify a payload format](http://modelbasedtesting.co.uk/?p=243). One interesting feature is that the broker can notify when
a client disconnects using a mechanism called [Last Will and Testament](http://stackoverflow.com/questions/17270863/mqtt-what-is-the-purpose-or-usage-of-last-will-testament).
Protocol [specifications (v3.1.1)](http://docs.oasis-open.org/mqtt/mqtt/v3.1.1/mqtt-v3.1.1.html) are freely available online. 

# MQTT Essentials
If you wish to read more I suggest proceeding with "MQTT Essentials" by HiveMQ team.

1. [Introducing MQTT](http://www.hivemq.com/blog/mqtt-essentials-part-1-introducing-mqtt)
2. [Publish & Subscribe](http://www.hivemq.com/blog/mqtt-essentials-part2-publish-subscribe)
3. [Client, Broker and Connection Establishment](http://www.hivemq.com/blog/mqtt-essentials-part-3-client-broker-connection-establishment)
4. [MQTT Publish, Subscribe & Unsubscribe](http://www.hivemq.com/blog/mqtt-essentials-part-4-mqtt-publish-subscribe-unsubscribe)
5. [MQTT Topics & Best Practices](http://www.hivemq.com/blog/mqtt-essentials-part-5-mqtt-topics-best-practices)
6. [Quality of Service 0, 1 & 2](http://www.hivemq.com/blog/mqtt-essentials-part-6-mqtt-quality-of-service-levels)
7. [Persistent Session and Queuing Messages](http://www.hivemq.com/blog/mqtt-essentials-part-7-persistent-session-queuing-messages)
8. [Retained Messages](http://www.hivemq.com/blog/mqtt-essentials-part-8-retained-messages)
9. [Last Will and Testament](http://www.hivemq.com/blog/mqtt-essentials-part-9-last-will-and-testament)
10. [Keep Alive and Client Take-Over](http://www.hivemq.com/blog/mqtt-essentials-part-10-alive-client-take-over)
11. [MQTT over WebSockets](http://www.hivemq.com/blog/mqtt-essentials-special-mqtt-over-websockets)
12. [Wrap-Up](http://www.hivemq.com/blog/mqtt-essentials-wrap-up)

# Public brokers
There are some brokers that are public. They can be used by anyone for testing and development purposes. Be careful not to publish sensitive data!  
Here it is a list of publicly available MQTT brokers. (checked on 2016-01-09)

 Address | Port | Description
 --- | --- | ---
broker.mqttdashboard.com | 1883 | MQTT, not encrypted
iot.eclipse.org | 1883 | MQTT, not encrypted
iot.eclipse.org | 8883 | MQTT, encrypted [TLS v1.2, v1.1 or v1.0 with x509 certificates](http://iot.eclipse.org/iot.eclipse.org.crt)
mq.thingmq.com | 80 | MQTT / Websockets, not encrypted
mq.thingmq.com | 1883 | MQTT, not encrypted 
mq.thingmq.com | 8883 | MQTT, encrypted SSL
mqtt.kgbvax.net | 1883 | MQTT, not encrypted, max message size 64 [KiB](https://en.wikipedia.org/wiki/Kibibyte)
mqtt.kgbvax.net | 8083 | MQTT / Websockets, not encrypted, max message size 64kiB
test.mosquitto.org | 1883 | MQTT, not encrypted
test.mosquitto.org | 8883 | MQTT, encrypted [TLS v1.2, v1.1 or v1.0 with x509 certificates](http://test.mosquitto.org/ssl/mosquitto.org.crt)
test.mosquitto.org | 8080 | MQTT / Websockets, not encrypted
test.mosquitto.org | 8081 | MQTT / Websockets, encrypted [TLS v1.2, v1.1 or v1.0 with x509 certificates](http://test.mosquitto.org/ssl/mosquitto.org.crt)
