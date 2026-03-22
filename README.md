# dactor_test

Test utilities for the [Dactor](https://pub.dev/packages/dactor) actor system.

## Features

- **TestActorSystem** — A controlled actor system for deterministic testing with message tracing
- **TestProbe** — Probe actor for message expectation, verification, and timeout-based assertions

## Usage

```dart
import 'package:dactor_test/dactor_test.dart';

final system = TestActorSystem(ActorSystemConfig());
final probe = await system.createTestProbe('test-probe');

// Send a message and verify receipt
actorRef.tell('hello');
final msg = await probe.expectMessage(timeout: Duration(seconds: 2));
expect(msg, equals('hello'));

await system.shutdown();
```

## License

MIT
