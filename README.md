# Wifi-senitinel-


flowchart LR
  subgraph Internet
    A[Websites / Applications]
  end

  B[Server Host]
  C[WiFi Router\n(Private IP, Secure)]
  D[WiFi Device\n(WiFi Sentinel)\nacts like firewall]
  E[Security Monitoring\n(Alerts / Logs / Response)]
  F[Hacker / Threat Actor]

  A -->|HTTP/HTTPS, API| B
  B -->|Private connection| C
  C -->|Local WiFi| D
  D -->|Inspect / Filter / Block| E
  F -.->|Attack Attempts| D
  F -.->|Target| C
  E -->|Mitigation / Notify| B

  %% Styling for emphasis
  classDef device fill:#e6f7ff,stroke:#0366d6,color:#042a4b;
  classDef server fill:#fff7e6,stroke:#ff8a00,color:#5a3b00;
  classDef internet fill:#f0fdf4,stroke:#0f5132,color:#08331a;
  classDef threat fill:#fff0f0,stroke:#d62828,color:#6f0b0b;

  class A internet;
  class B server;
  class C server;
  class D device;
  class E device;
  class F threat;
