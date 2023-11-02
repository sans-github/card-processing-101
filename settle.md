# Settle flow
```mermaid
  sequenceDiagram
    actor Merchant
    Merchant->>+Processor: Batch of approved auth tx
    Processor->>+Acquiring bank: Batch of approved auth tx
    Acquiring bank->>+Card Network: Batch of approved auth tx
    Card Network->>+Issuing bank: Settle
    Issuing bank->>Issuing bank: Charge customer account
    Issuing bank->>Issuing bank: Keep it's share of the interchange fee
    Issuing bank->>Card Network: Share remaining of Interchange fee
    Issuing bank->>-Acquiring bank: Funds (less interchange)
    Card Network->>Card Network: Keep Network cut
    Card Network->>Acquiring bank: Acquirer's cut
    Acquiring bank->>Processor: Funds(less interchange)
    Processor->>Processor: Keep merchant discount
    Processor->>-Merchant: Fund (less interchange, merchant discount)
  ```
