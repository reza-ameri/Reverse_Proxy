Envoy Reverse Proxy for Nexus Repository

This project provides an Envoy Proxy configuration to securely expose a Sonatype Nexus Repository
 through HTTPS with TLS termination, domain-based routing, and automatic HTTP → HTTPS redirection.


Features

🔒 TLS termination with support for strong cipher suites

🌍 Domain-based routing for multiple subdomains:

repo.deployacademy.ir → Nexus UI (port 8081)

pub.deployacademy.ir → Nexus Public (port 8082)

🔁 HTTP to HTTPS redirection for both domains

📜 Access logs written to /var/log/envoy/access.log

⚙️ Admin interface on port 9901 for monitoring and troubleshooting




Architecture
        Client
          │
    ┌─────┴─────┐
    │   Envoy   │
    │ (443/80)  │
    └─────┬─────┘
          │
 ┌────────┴────────┐
 │                 │
Nexus UI (8081)   Nexus Public (8082)
