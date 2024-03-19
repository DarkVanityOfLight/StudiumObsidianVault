
Der ExecutorService erweitert den [Executor](Executor.md) und ist die Schnittstelle zwischen [Callable](Callable.md) und Future.

- `submit` hat ein `Callable<V>` (oder `Runnable`) Objekt als Input und liefert ein `Future<V>` Objekt zurück
- `invokeAll` hat eine Collection an `Callable<V>` Objekten (+wahlweise timeout) als Input und liefert eine Liste an `Future<V>` Objekten zurück, die Ergebnisse alle `call()` Methoden
- `invokeAny` hat eine Collection an `Callable<V>` Objekten (+wahlweise timeout) als Input und ein `V` Objekt zurück, d.h., sobald ein Auftrag ausgeführt ist, werden die anderen gestoppt
