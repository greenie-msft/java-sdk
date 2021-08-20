---
type: docs
title: "Dapr Java SDK"
linkTitle: "Actors"
weight: 2000
description: Java SDK packages for developing Dapr applications
---

### Actors
An actor is an isolated, independent unit of compute and state with single-threaded execution. Dapr provides an actor implementation based on the [Virtual Actor pattern](https://www.microsoft.com/en-us/research/project/orleans-virtual-actors/), which provides a single-threaded programming model and where actors are garbage collected when not in use. With Dapr's implementaiton, you write your Dapr actors according to the Actor model, and Dapr leverages the scalability and reliability that the underlying platform provides. 

```java
import io.dapr.actors.ActorMethod;
import io.dapr.actors.ActorType;
import reactor.core.publisher.Mono;

@ActorType(name = "DemoActor")
public interface DemoActor {

  void registerReminder();

  @ActorMethod(name = "echo_message")
  String say(String something);

  void clock(String message);

  @ActorMethod(returns = Integer.class)
  Mono<Integer> incrementAndGet(int delta);
}
```

- For a full guide on actors visit [How-To: Use virtual actors in Dapr]({{< ref howto-actors.md >}}).
- Visit [Java SDK examples](https://github.com/dapr/java-sdk/tree/master/examples/src/main/java/io/dapr/examples/actors) for code samples and instructions to try actors

## Related links
- [Java SDK examples](https://github.com/dapr/java-sdk/tree/master/examples/src/main/java/io/dapr/examples)
