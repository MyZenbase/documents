# Zenbase Security Policy 🔐

Our security policy is not a legal document full of long hard-to-read statements. It's an easy to follow set of guidelines and rules that merely summarise practices already in use. When some part of this document is still in implementation phase, it's stated so.

## General Policy

Security policy is for everyone. Anyone can be the target of a cyber attack and anybody can leak data by accident. That's why it's essential this policy covers all aspects of company's routines for all the roles.

### Be aware, be cautious
- No security policy can prevent any cyber attacks. Up to [98% cyber attacks rely on social engineering](https://purplesec.us/cyber-security-trends-2021/) in some way and it's impossible to plan, prepare or train people for all the possible scenarios. That's why general alert and suspicion for any communication is essential

### Accounts and credentials

- All employees and contractors get issued a personal Google Account
- All personal Google accounts are 2FA enabled
- Everyone uses a password manager for storing their credentials
- No password is reused between multiple accounts

### Laptops and devices
- Storage on all work laptops is encrypted
- Both computers and mobile phones are password-protected and auto-lock mechanism is turned on
- This is common sense, but still, don't leave your work laptop unattended in a public space, don't leave it in a parked car

## Software Development

The same as quality or performance, security is also everyone's job. All software engineers and everyone involved in building, running or maintaining software are equally responsible for security. Over the time and with the increasing numbers and sophistication of cyber attacks, security aspect takes bigger part of everyone's individual role.

Especially for software development, the following policies and guidelines cannot ever be a complete list of checks to follow. If you see a potential loophole or vulnerability that is not covered in here, either fix it right away or at least report it! **Our security depends on everyone!**

### Development process

- All proprietary company source code is store in Github under company’s private repository
- All secrets (DB passwords, API keys, etc.) are stored in a secure cloud storage only accessible to CI/CD tools and to developers on “as needed” basis

### Cloud Infrastructure

#### Services
- All services in Google Cloud
- Cloud logging enabled for:
    - PUT/POST/PATCH endpoints
    - Server-side errors

#### Databases
- All users credentials are stored within Google Firebase framework
- Databases accessible only via Google Cloud Proxy
  - or via SSL-enabled connection and public IP allowlist
- Each service has a specific DB account with a restricted access (_to be implemented_)
- Only CI/CD scripts can alter structures (_to be implemented_)
- Each developer has a named account for accessing DB
- Auditlog is enabled on all essential tables containing business critical or PII data

## Monitoring

- Automated alerts if the amount of errors logged over certain time period exceeds a threshold
- A regular on-call rotation in place with a clear person responsible for monitoring at any given moment
- On-call person monitors logs regularly

## Security incidents

- Security incidents are reported to security@myzenbase.com
- Security incidents are logged under Jira project “Security”
- All non-sensitive documentation related to the incident is kept together with the Jira ticket
- All relevant partners are notified about the incident
