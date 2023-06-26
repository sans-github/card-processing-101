# Auth flow
```mermaid
  sequenceDiagram
    actor Customer
    Customer->>+Merchant: Card Info
    Merchant->>+Gateway: Auth
    Gateway->>+Acquirer: Auth
    Acquirer->>+Card Association: Auth
    Card Association->>+Issuer: Auth
    Issuer->>-Card Association: Success(Auth code)
    Card Association->>-Acquirer: Auth code
    Acquirer->>-Gateway: Auth code
    Gateway->>-Merchant: Auth code
    Merchant->>-Customer: Auth success
  ```
