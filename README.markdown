# java-mpns [![Build Status](https://travis-ci.org/aerogear/java-mpns.png)](https://travis-ci.org/aerogear/java-mpns)

_Note:_ This is a maintained fork of [https://github.com/notnoop/java-mpns](https://github.com/notnoop/java-mpns)

|                 | Project Info  |
| --------------- | ------------- |
| License:        | Apache License, Version 2.0  |
| Build:          | Maven  |
| Documentation:  | https://aerogear.org/push/  |
| Issue tracker:  | https://issues.jboss.org/browse/AGPUSH  |
| Mailing lists:  | [aerogear-users](http://aerogear-users.1116366.n5.nabble.com/) ([subscribe](https://lists.jboss.org/mailman/listinfo/aerogear-users))  |
|                 | [aerogear-dev](http://aerogear-dev.1069024.n5.nabble.com/) ([subscribe](https://lists.jboss.org/mailman/listinfo/aerogear-dev))  |


java-mpns is a Java client for [Microsoft Push Notification service (MPNs)](http://msdn.microsoft.com/en-us/library/windows/apps/ff402558.aspx).
The library aims to provide a highly scalable interface to the Microsoft Push
server, while still being simple and modular.

The interface aims to require very minimal code to achieve the most common
cases, but have it be reconfigurable so you can even use your own networking
connections or XML library if necessary.

Features:
--------------
  *  Easy to use, high performance MPNS Service API
  *  Easy to extend and reuse
  *  Easy to integrate with dependency injection frameworks
  *  Easy to setup custom notification payloads
  *  Supports connection pooling
  *  Supports message delegates and callbacks


Sample Code
----------------

To send a notification, you can do it in two steps:

1. Declare Maven dependency

        <dependency>
            <groupId>org.jboss.aerogear.windows</groupId>
            <artifactId>java-mpns</artifactId>
            <version>0.1.0</version>
        </dependency>

2. Setup the connection

        MpnsService service =
            MPNS.newService()
            .build();

3. Create and send the message

        MpnsMessage notification = MPNS.newMessage()
            .tile().count(2).title("Tile message")
            .build();
        String subscriptionUri = "https://..../"
        service.push(subscriptionUri, notification);

That's it!

## Documentation

For more details about the current release, please consult [our documentation](https://aerogear.org/docs/unifiedpush/).

## Development

If you would like to help develop AeroGear you can join our [developer's mailing list](https://lists.jboss.org/mailman/listinfo/aerogear-dev), join #aerogear on Freenode, or shout at us on Twitter @aerogears.

Also takes some time and skim the [contributor guide](http://aerogear.org/docs/guides/Contributing/)

## Questions?

Join our [user mailing list](https://lists.jboss.org/mailman/listinfo/aerogear-users) for any questions or help! We really hope you enjoy app development with AeroGear!

## Found a bug?

If you found a bug please create a ticket for us on [Jira](https://issues.jboss.org/browse/AGPUSH) with some steps to reproduce it.

