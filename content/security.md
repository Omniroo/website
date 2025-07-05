---
title: "Security"
layout: "simple"
---

## Security Overview

At Omniroo, we understand the importance of data security and privacy. We are committed to protecting your information and maintaining the highest standards of security. This page outlines the measures we take to secure your data.

### Data Encryption

*   **In Transit:** All data transmitted between your browser, our servers, and third-party services (like Stripe and HubSpot) is encrypted using industry-standard TLS (Transport Layer Security).
*   **At Rest:** Sensitive data stored on our servers is encrypted using AES-256 encryption.

### Data Privacy and Handling

*   **Data Streaming Service:** Omniroo operates as a data streaming service that does not store any payment or customer data received from Stripe. All Stripe data is processed in real-time and immediately passed through to HubSpot without being stored on our servers.
*   **Data Minimization:** We only collect and store the minimal configuration data necessary to provide the service (such as connection settings and authentication tokens).
*   **Access Control:** Access to user data is strictly limited to authorized personnel on a need-to-know basis.
*   **Third-Party Services:** We use reputable third-party services with strong security policies:
    *   [Stripe Security](https://stripe.com/docs/security/stripe)
    *   [HubSpot Security](https://trust.hubspot.com/)
    *   [Google Cloud Platform Security](https://cloud.google.com/security)
*   **Data Deletion:** When you close your account, your configuration data will be permanently deleted from our systems within 30 days.

### Authentication and Authorization

*   **Secure Authentication:** We use secure authentication methods (OAuth 2.0) for connecting to third-party services like Stripe and HubSpot.
*   **Password Security:** We use bcrypt to hash and salt passwords, ensuring strong password security.

### Infrastructure and Network Security

*   **Cloud Provider:** We host our infrastructure on Google Cloud Platform, a leading provider with robust security measures.
*   **Firewalls and Network Segmentation:** We use firewalls and network segmentation to protect our infrastructure.

### Compliance and Certifications

*   **PCI DSS Compliance:** Our payment processing is handled by Stripe, a PCI DSS compliant service.
*   **SOC 2 Compliance:** We follow SOC 2 compliance standards.

### Vulnerability Management

*   **Regular Scans:** We regularly scan our systems for vulnerabilities.
*   **Responsible Disclosure:** If you discover a security vulnerability, please report it via our [contact form](/contact).

### Incident Response

*   **Monitoring and Alerting:** We have monitoring and alerting systems in place to detect and respond to security incidents.
*   **Communication:** In the event of a security breach, we will promptly notify affected users.
