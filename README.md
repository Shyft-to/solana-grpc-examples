# Simple Node JS gRPC client to stream solana data

## Subscribe to slots
```typescript
const req: SubscribeRequest = {
  accounts: {},
  slots: {
    incoming_slots: {},
  },
  transactions: {},
  transactionsStatus: {},
  entry: {},
  blocks: {},
  blocksMeta: {},
  accountsDataSlice: [],
  ping: undefined,
  commitment: CommitmentLevel.PROCESSED,
};
```

## Subscribe to an account
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {
    "wsol/usdc": {
      account: ["Czfq3xZZDmsdGdUyrNLtRhGc47cXcZtLG4crryfu44zE"],
      owner: [],
      filters: [],
    },
  },
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [],
  commitment: CommitmentLevel.CONFIRMED,
};
```

## Subscribe to an account with `accountsDataSlice`
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {
    usdc: {
      account: [],
      owner: ["TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA"],
      filters: [
        {
          tokenAccountState: true,
        },
        {
          memcmp: {
            offset: String(0),
            base58: "EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v",
          },
        },
      ],
    },
  },
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [{ offset: String(32), length: String(40) }],
  commitment: CommitmentLevel.CONFIRMED,
};
```

## Subscribe to a program account updates
```typescript
const req: SubscribeRequest = {
  slots: {
    slots: {},
  },
  accounts: {
    openbookV2: {
      owner: ["opnb2LAfJYbRMAHHvqjCwQxanZn7ReEHp1k81EohpZb"],
      account: [],
      filters: [],
    },
  },
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  accountsDataSlice: [],
  commitment: CommitmentLevel.PROCESSED,
  entry: {},
};
```

## Subscribe to a program account updates
```typescript
const req: SubscribeRequest = {
  slots: {
    slots: {},
  },
  accounts: {
    openbookV2: {
      owner: ["opnb2LAfJYbRMAHHvqjCwQxanZn7ReEHp1k81EohpZb"],
      account: [],
      filters: [],
    },
  },
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  accountsDataSlice: [],
  commitment: CommitmentLevel.PROCESSED,
  entry: {},
};
```

## Subscribe to transactions mentioning accounts
```typescript
const req: SubscribeRequest = {
  accounts: {},
  slots: {},
  transactions: {
    raydiumLiquidityPoolV4: {
      vote: false,
      failed: false,
      signature: undefined,
      accountInclude: ["675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8"],
      accountExclude: [],
      accountRequired: [],
    },
    jupiterV6: {
      vote: false,
      failed: false,
      signature: undefined,
      accountInclude: ["JUP6LkbZbjS1jKKwapdHNy74zcZ3tLUZoi5QNyVTaV4"],
      accountExclude: [],
      accountRequired: [],
    },
    openbookV2: {
      vote: false,
      failed: false,
      signature: undefined,
      accountInclude: ["opnb2LAfJYbRMAHHvqjCwQxanZn7ReEHp1k81EohpZb"],
      accountExclude: [],
      accountRequired: [],
    },
  },
  transactionsStatus: {},
  entry: {},
  blocks: {},
  blocksMeta: {},
  accountsDataSlice: [],
  ping: undefined,
  commitment: CommitmentLevel.CONFIRMED,
};
```

## Subscribe to transactions excluding accounts
```typescript
const req: SubscribeRequest = {
  accounts: {},
  slots: {},
  transactions: {
    serum: {
      vote: false,
      failed: false,
      signature: undefined,
      accountInclude: [],
      accountExclude: [
        "9xQeWvG816bUx9EPjHmaT23yvVM2ZWbrrpZb9PusVFin",
        "TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA"
      ],
      accountRequired: [],
    },
  },
  transactionsStatus: {},
  entry: {},
  blocks: {},
  blocksMeta: {},
  accountsDataSlice: [],
  ping: undefined,
  commitment: CommitmentLevel.CONFIRMED,
};
```

## Subscribe to transactions mentioning accounts & excluding certain accounts
```typescript
const req: SubscribeRequest = {
  accounts: {},
  slots: {},
  transactions: {
    serum: {
      vote: false,
      failed: false,
      signature: undefined,
      accountInclude: ["9xQeWvG816bUx9EPjHmaT23yvVM2ZWbrrpZb9PusVFin"],
      accountExclude: ["9wFFyRfZBsuAha4YcuxcXLKwMxJR43S7fPfQLusDBzvT"],
      accountRequired: [],
    },
  },
  transactionsStatus: {},
  entry: {},
  blocks: {},
  blocksMeta: {},
  accountsDataSlice: [],
  ping: undefined,
  commitment: CommitmentLevel.CONFIRMED,
};
```

## Subscribe to a transaction signature
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {},
  transactions: {
    sign: {
      vote: false,
      failed: false,
      signature:
        "58JnUKrMWwLbRMEwPC7z6dFXMBo5pst4r1YYWDkUdsz7TWHvZw4LLNzCAYj583KXNUdePM4CVQhHSkhaHZ7JfoX6",
      accountInclude: [],
      accountExclude: [],
      accountRequired: [],
    },
  },
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [],
};
```

## Subscribe to all finalized transactions
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {},
  transactions: {
    alltxs: {
      vote: true,
      failed: true,
      signature: undefined,
      accountInclude: [],
      accountExclude: [],
      accountRequired: [],
    },
  },
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [],
  commitment: CommitmentLevel.FINALIZED,
};
```

## Subscribe to blocks
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {},
  transactions: {},
  transactionsStatus: {},
  blocks: {
    blocks: {
      accountInclude: [],
      includeTransactions: false,
      includeAccounts: false,
      includeEntries: false,
    },
  },
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [],
};
```

## Subscribe to block metadata
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {},
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: { blockmetadata: {} },
  entry: {},
  accountsDataSlice: [],
};
```

## Modifying subscription
The subscribe method provides a two-way stream, so you can modify the subscription by simply sending the newly updated subscription string and you'll start receiving updates on your modified filters.

This will completely overwrite the previous subscription, so make sure your client maintains a local registry of the entire subscription configuration you're interested in.

## Unsubscribing
If you want to unsubscribe from all streams, send the following request:
```typescript
const req: SubscribeRequest = {
  slots: {},
  accounts: {},
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [],
};
```
This will clear all current subscriptions but keep the connection open for future subscriptions.

## Managing commitment levels
The gRPC streams happen by default on the processed commitment level.

For maximum performance, however, we recommend handling the commitment layer client side.

To specify commitment level
```typescript
enum CommitmentLevel {
  PROCESSED = 0;
  CONFIRMED = 1;
  FINALIZED = 2;
}

const req: SubscribeRequest = {
  slots: {},
  accounts: {},
  transactions: {},
  transactionsStatus: {},
  blocks: {},
  blocksMeta: {},
  entry: {},
  accountsDataSlice: [],
  commitment: CommitmentLevel.FINALIZED, // specify commitment levels here
};
```