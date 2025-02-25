# Cloud-Based Architecture Diagram

```mermaid
graph TD;
    A[User] -->|Internet| B[Load Balancer]
    B --> C[Web Server Cluster]
    B --> F1[Firewall]
    F1 --> C[Web Server Cluster]
    C --> D[Database Server]
    C --> E[Cache Server]
    D -->|Data Storage| F[Cloud Storage Service]
    E -->|Cached Data| F[Cloud Storage Service]
    C --> G[Application Server]
    G -->|API Requests| H[External API Service]
    H -->|API Responses| G
    F -->|Backup/Recovery| I[Backup Service]
    I -->|Restored Data| F
    G --> IDS1[Intrusion Detection System]
    IDS1 --> SIEM1[SIEM System]
    F1 --> IDS2[Intrusion Detection System]
    IDS2 --> SIEM2[SIEM System]
    B -->|Traffic| WAF[Web Application Firewall]
    WAF --> C

