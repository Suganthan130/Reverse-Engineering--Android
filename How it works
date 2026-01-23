sequenceDiagram
    participant App as Your App (Client)
    participant Play as Google Play
    participant Server as Your Backend Server
    participant Google as Google Server
    Note over App: 1. User opens App
    App->>App: Generate Nonce
    App->>Play: Request Integrity Token
    Play-->>App: Return Encrypted Token
    
    Note over App: 2. Token received
    App->>Server: Send Token via API
    
    Note over Server: 3. Verify Token
    Server->>Google: Decrypt & Verify Token
    Google-->>Server: Result (Device matches? App license valid?)
    
    alt Secure
        Server-->>App: Allow Login / Access
    else Insecure
        Server-->>App: Block / Force Exit
    end
