# ProtonWebLink Class

The ProtonWebLink class is responsible for handling web-based authentication and transaction signing for the Proton blockchain. It manages the communication between your application and the WebAuth interface.

## Constructor

```typescript
constructor(options: LinkOptions & { testUrl?: string })
```

### Parameters
- `options`: Configuration object that extends LinkOptions with an optional testUrl
  - `scheme`: The scheme to use (e.g., 'proton')
  - `client`: JsonRpc client or endpoint URL
  - `storage`: Storage adapter for persisting data
  - `testUrl`: Optional URL for testing purposes
  - `transport`: Transport layer for communication
  - `chainId`: Chain ID for the blockchain

## Public Properties

- `childWindow`: Gets or sets the child window used for authentication
- `scheme`: The scheme being used
- `storage`: Storage adapter instance
- `client`: JsonRpc client instance
- `testUrl`: Optional test URL
- `transport`: Transport layer instance
- `chainId`: Chain ID string

## Public Methods

### login()
Initiates the login process through WebAuth.

```typescript
async login(): Promise<{ session: any }>
```

### createSession(auth: Authorization)
Creates a new session with the given authorization.

```typescript
createSession(auth: Authorization): {
    auth: Authorization;
    chainId: string;
    transact: (args: TransactArgs, options?: TransactOptions) => Promise<any>;
    link: {
        walletType: string;
        client: JsonRpc;
    };
}
```

### restoreSession(requestAccount: string, auth: any)
Restores a previous session.

```typescript
async restoreSession(requestAccount: string, auth: any): Promise<any>
```

### removeSession(appIdentifier: string, auth: any, chainId: any)
Removes a session from storage.

```typescript
async removeSession(appIdentifier: string, auth: any, chainId: any): Promise<{
    appIdentifier: string;
    auth: any;
    chainId: any;
}>
```