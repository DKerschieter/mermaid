# Cloud-Based Architecture Diagram

```mermaid
graph TD;
    A[User] -->|Internet| B[Load Balancer]
    B --> C[Web Server Cluster]
    B --> F1[Firewall]
    F1 --> C[Web Server Cluster]
    C --> D[Database Server]
    C --> E[Cache Server]
    D -->|Data Storage| F[Google Cloud Storage]
    E -->|Cached Data| F[Google Cloud Storage]
    C --> G1[Application Server 1]
    C --> G2[Application Server 2]
    G1 -->|API Requests| H[External API Service]
    G2 -->|API Requests| H[External API Service]
    H -->|API Responses| G1
    H -->|API Responses| G2
    F -->|Backup/Recovery| I[Google Cloud Backup Service]
    I -->|Restored Data| F
    G1 --> IDS1[Intrusion Detection System]
    G2 --> IDS3[Intrusion Detection System]
    IDS1 --> SIEM1[SIEM System]
    IDS3 --> SIEM3[SIEM System]
    F1 --> IDS2[Intrusion Detection System]
    IDS2 --> SIEM2[SIEM System]
    B -->|Traffic| WAF[Web Application Firewall]
    WAF --> C
    A -->|Internet| CDN[CDN]
    CDN --> B
    B --> LB1[Load Balancer West]
    B --> LB2[Load Balancer East]
    LB1 --> C1[Web Server Cluster West]
    LB2 --> C2[Web Server Cluster East]
    C1 --> D1[Database Server West]
    C2 --> D2[Database Server East]
    D1 -->|Data Storage| F1[Google Cloud Storage West]
    D2 -->|Data Storage| F2[Google Cloud Storage East]
    F1 -->|Backup/Recovery| I1[Google Cloud Backup West]
    F2 -->|Backup/Recovery| I2[Google Cloud Backup East]
    G1 --> LG1[Cloud Logging and Monitoring]
    G2 --> LG2[Cloud Logging and Monitoring]








