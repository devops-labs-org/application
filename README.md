# Application Repository

---

## What this repository is for

This repository contains the main application source code and  meant only for application development.
All changes here affect how the application behaves in production.

---

## What type of changes are allowed

- Application source code changes
- Bug fixes and feature updates
- Documentation related to application behavior

All changes must go through a Pull Request.
Code should be reviewed before merging to main branch.

---

## What changes are NOT allowed

- Infrastructure files (servers, networks, cloud resources)
- CI/CD pipeline configurations
- Direct pushes to the main branch

These changes must be done in their respective repositories.

---

## What happens when things fail

If the application runs into errors, some user actions might fail or show incomplete results.  
When services the app depends on stop working, features can slow down or temporarily not work, and users may see fallback screens or retries.  
If issues last too long, important features may stay unavailable, which can reduce user confidence until everything is stable again.

---

## How rollback or recovery works

When something goes wrong, we bring back the last stable version of the application instead of trying to fix issues directly in production.  
This restores expected behavior quickly, even if it means removing recent changes that were causing problems.  
Some new features may temporarily disappear after a rollback, but the product becomes stable again while fixes are prepared safely.

---

## Who is impacted by failure

When the application breaks, users might face slow responses, missing results, or features that don’t work as expected.  
Product and engineering teams may need to stop new releases or development work until the app is stable again.  
Keeping everyone informed during these issues helps set expectations and reduces confusion while recovery is in progress.

---

## Who owns this repository

This repository is owned by the application or product engineering team.  
They are responsible for reviewing changes, maintaining quality standards, and ensuring the product delivers value without unexpected behaviour.  
Final approval and merge decisions are handled by Admins.

---

## Risk if misused

If someone adds infrastructure code or sensitive data here, deployments may break or expose information to the wrong people.  
These mistakes can cause outages, make rollback harder, and delay new feature releases while problems are fixed.  
Keeping this repo focused only on application behavior helps avoid security issues and keeps the product stable.

---
