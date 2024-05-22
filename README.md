### Simple Node JS GRPC client to stream solana data

## Subscribe to an account
```typescript
const req: SubscribeRequest = {"slots": { "slots": {} }, "accounts": { "wsol/usdc": { "account": ["8BnEgHoWFysVcuFFX7QztDmzuH8r5ZFvyP3sYwn1XTh6"] } }, "transactions": {}, "blocks": {}, "blocks_meta": {}, "accounts_data_slice": [], "commitment": 1}
```