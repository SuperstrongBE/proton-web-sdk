# Link Class

The Link class is the main class for interacting with the Proton blockchain. It handles transaction signing, chain communication, and session management.

## Constructor

```typescript
constructor(options: LinkOptions)
```

### Parameters
- `options`: Configuration object containing:
  - `transport`: Required. Transport used to deliver requests to the user's wallet
  - `chains`: Array of chain configurations (required if chainId/client not provided)
  - `chainId`: Single chain ID (alternative to chains array)
  - `client`: Client URL (alternative to chains array)
  - `service`: Optional callback service configuration
  - `storage`: Optional storage adapter
  - `verifyProofs`: Optional flag to verify identity proofs
  - `encodeChainIds`: Optional flag to encode chain IDs
  - `scheme`: Request scheme
  - `walletType`: Optional wallet type identifier

## Public Properties

- `chains`: Array of LinkChain instances this Link is configured with
- `transport`: Transport instance used to deliver requests
- `storage`: Optional storage adapter for session persistence
- `scheme`: Scheme used for requests
- `walletType`: Optional wallet type identifier
- `client`: APIClient instance for the first configured chain

## Public Methods

### getChain(chain: LinkChainType)
Returns a LinkChain object for the given chain reference.

```typescript
getChain(chain: LinkChainType): LinkChain
```

### transact(args: TransactArgs, options?: TransactOptions, transport?: LinkTransport)
Signs and optionally broadcasts a transaction.

```typescript
async transact(
    args: TransactArgs,
    options?: TransactOptions,
    transport?: LinkTransport
): Promise<TransactResult>
```

### createRequest(args: SigningRequestCreateArguments, chain?: LinkChain, transport?: LinkTransport)
Creates a SigningRequest instance configured for this link.

```typescript
async createRequest(
    args: SigningRequestCreateArguments,
    chain?: LinkChain,
    transport?: LinkTransport
): Promise<{ request: SigningRequest; callback: LinkCallback }>
```

### sendRequest(request: SigningRequest, callback: LinkCallback, chain?: LinkChain, transport?: LinkTransport, broadcast?: boolean)
Sends a SigningRequest instance using this link.

```typescript
async sendRequest(
    request: SigningRequest,
    callback: LinkCallback,
    chain?: LinkChain,
    transport?: LinkTransport,
    broadcast?: boolean
): Promise<TransactResult>
```