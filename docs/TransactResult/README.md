# TransactResult Interface

The TransactResult interface represents the result of a transaction operation in the Proton blockchain.

## Properties

### resolved
The resolved signing request.
```typescript
resolved: ResolvedSigningRequest
```

### chain
The chain that was used for the transaction.
```typescript
chain: LinkChain
```

### signatures
The transaction signatures.
```typescript
signatures: Signature[]
```

### payload
The callback payload.
```typescript
payload: CallbackPayload
```

### signer
The signer authority.
```typescript
signer: PermissionLevel
```

### transaction
The resulting transaction.
```typescript
transaction: Transaction
```

### resolvedTransaction
Resolved version of transaction, with the action data decoded.
```typescript
resolvedTransaction: ResolvedTransaction
```

### processed
Push transaction response from API node, only present if transaction was broadcast.
```typescript
processed?: {[key: string]: any}
```

## Usage Example

```typescript
const result: TransactResult = await link.transact({
    actions: [/* your actions here */]
});

// Access the transaction signatures
console.log(result.signatures);

// Access the resolved transaction data
console.log(result.resolvedTransaction);

// Check if transaction was processed (if broadcast)
if (result.processed) {
    console.log(result.processed);
}
```