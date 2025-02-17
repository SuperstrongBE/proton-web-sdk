# WalletConnectRet Interface

**Note: This interface could not be found in the current codebase. The documentation below is a placeholder and needs to be updated once the correct interface is located.**

The WalletConnectRet interface likely represents the return value from a wallet connection operation. Please refer to the latest SDK documentation or source code for the current implementation details.

## Suggested Properties

These are typical properties that might be included in a wallet connection return value:

### connected
Indicates if the wallet connection was successful.
```typescript
connected: boolean
```

### session
The session information if connection was successful.
```typescript
session?: any
```

### error
Any error that occurred during the connection attempt.
```typescript
error?: string
```

## Usage Example

```typescript
// Example usage (actual implementation may differ)
const result: WalletConnectRet = await wallet.connect();

if (result.connected) {
    // Handle successful connection
    console.log(result.session);
} else {
    // Handle connection failure
    console.error(result.error);
}
```

Please consult the current SDK documentation for the actual implementation and usage details.