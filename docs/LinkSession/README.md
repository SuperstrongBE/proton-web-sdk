# LinkSession Class

The LinkSession is an abstract class that represents a session with the Proton blockchain. It provides the base functionality for different types of sessions (Channel and Fallback).

## Abstract Methods

### serialize()
Serializes the session data for storage.

```typescript
abstract serialize(): SerializedLinkSession
```

## Static Methods

### restore(link: Link, data: SerializedLinkSession)
Restores a session from serialized data.

```typescript
static restore(link: Link, data: SerializedLinkSession): LinkSession
```

## Implementations

### LinkChannelSession
A session implementation that uses a communication channel.

```typescript
class LinkChannelSession extends LinkSession implements LinkTransport
```

### LinkFallbackSession
A fallback session implementation.

```typescript
class LinkFallbackSession extends LinkSession implements LinkTransport
```

## Interfaces

### SerializedLinkSession
Interface describing the structure of serialized session data.

```typescript
interface SerializedLinkSession {
    chain: string;
    actor: string;
    permission: string;
    publicKey: string;
    type: 'channel' | 'fallback';
}
```