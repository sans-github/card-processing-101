# Settle flow
```mermaid
  sequenceDiagram
    actor Gateway
    Gateway->>Gateway: Create batch settlement file, nightly
    Gateway->>+Acquirer: Settle funds 
    Acquirer->>+Issuer or Card Network: Settle funds 
    Issuer or Card Network->>-Acquirer: Deposit funds from from customer->acquirer
    Acquirer->>-Gateway: Settlement complete
    Acquirer->>Merchant bank: Fund movement customer->acquirer (2-5 biz days)
  ```
