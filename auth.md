# Auth flow
```mermaid
  sequenceDiagram
      actor Cardholder
      Cardholder->>+Merchant: Card swipe
      Merchant->>+Processor: Card details 
      Processor->>+Acquirer: Card details
      Acquirer->>+Card Network: Card details
      Card Network->>+Issuing bank: Auth request
      Issuing bank->>Issuing bank: Validate card details
      Issuing bank->>Issuing bank: Fund availability
      Issuing bank->>Issuing bank: Assess risk & compliance
      Issuing bank->>Issuing bank: Place a hold on customer funds
      Issuing bank->>-Card Network: Auth response
      Card Network->>-Acquirer: Auth response
      Acquirer->>-Processor: Auth response
      Processor->>-Merchant: Auth response
      Merchant->>-Cardholder: Auth response
  ```
