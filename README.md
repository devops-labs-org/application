# Application 

# What this repository is for

This repository contains the main application source code and  meant only for application development.
All changes here affect how the application behaves in production.

---

# What type of changes are allowed

- Application source code changes
- Bug fixes and feature updates
- Documentation related to application behavior

All changes must go through a Pull Request.
Code should be reviewed before merging to main branch.

---

# What changes are NOT allowed

- Infrastructure files (servers, networks, cloud resources)
- CI/CD pipeline configurations
- Direct pushes to the main branch

These changes must be done in their respective repositories.

---

# Who owns this repository

This repository is owned by the organization.
Admins manage repository settings and branch rules.
Developers can contribute through Pull Requests.

Final approval and merge decisions are handled by Admins.

---

# Risk if this repository is misused

If infrastructure files or secrets are added here by mistake, more people may see them than they should.
This can lead to security problems or even break the live application.

Keeping the right files in the right repository helps keep the system safe.
