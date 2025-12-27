# Branching Strategy & Branch Protection Rules — Application Repository

## 1. Purpose of This Document

This document explains how branches are used and managed in the application repository.  
The intention is to support fast development, predictable releases, and a stable production environment.  
Every engineer working in this repository should follow this strategy to ensure consistent workflows and controlled changes.

> **Branching strategy:** Trunk-Based Development  
> **Production branch:** `main`  
> **Daily development branch:** `develop`

---

## 2. Branch Types and How We Use Them

There are four branch types in this repository, each serving a specific role in the development process.

### `main`
`main` represents the production state of the system.  
Everything in this branch should be tested and ready to deploy.  
Only maintainers merge changes into `main`, and changes always arrive through pull requests, never direct commits.

### `develop`
`develop` is where active development comes together.  
Developers base new work from this branch.  
Once a feature or improvement is completed, reviewed, and tested, it merges back into `develop`.

### `feature/<name>`
Feature branches are temporary spaces for individual tasks.  
They originate from `develop` and return to `develop` through a pull request once complete.  
These branches are expected to be short-lived to avoid falling out of sync.


### `hotfix/<name>`
Hotfix branches exist only to resolve urgent production issues.  
They are created from `main` when something in production needs immediate attention.  
After fixing the issue, the hotfix is merged back into `main` and also into `develop` so future work includes the same fix.

---

## 3. How Daily Development Happens (Workflows)

Work begins by updating the local `develop` branch and creating a feature branch from it.  
Developers modify code within their feature branch, pushing changes regularly to keep integration smooth.  
When a developer is ready to contribute work back, they open a pull request into `develop`.

Regular pull requests make collaboration smoother, keep changes smaller, and reduce the difficulty of merging.

---

## 4. How Features Move Into the Codebase (Merging)

When a feature is complete:

1. The developer opens a pull request from the feature branch into `develop`.
2. Automated checks must pass to confirm the changes don’t introduce errors.
3. Another engineer reviews the pull request to ensure quality and clarity.
4. After approval, the branch is merged using **squash merge**, creating a single clean commit in `develop`.

Once enough features have been accumulated and tested together in `develop`, maintainers merge `develop` into `main` to release the changes to production.

---

## 5. Fixing Problems in the Code (Bug Handling)

Smaller bugs that do not affect production are handled the same way as features.  
A developer creates a feature branch, fixes the bug, and submits a pull request to `develop`.

Critical bugs that break production or significantly affect users are treated differently.  
In those cases, a hotfix branch is created directly from `main`, the fix is applied, and the branch is merged back into `main`.  
After deployment, the same fix is merged into `develop` to ensure future work is not missing the fix.

This approach ensures production is restored quickly without losing consistency between branches.

---

## 6. Handling Urgent Situations (Emergency Flow)

When production breaks or a major issue impacts users, time matters.  
A maintainer creates a `hotfix` branch from `main` and applies a fix as soon as possible.  
After confirming the issue is resolved, the fix is merged back into `main` and deployed immediately.  
The same change is then pulled into `develop` to keep both branches aligned.

During emergencies, merging non-critical features may pause until the hotfix is fully integrated into all branches.

---

## 7. Protecting the Important Branches (Branch Protections)

To prevent accidental changes or force pushes, certain protections are applied:

- `main` is protected to ensure nothing reaches production without review and checks.
- Pull requests are mandatory for merging into `main` and `develop`.
- Automated checks must pass before merging to catch issues early.
- Direct pushes are blocked to avoid bypassing review and automation.

These protections help maintain code quality, prevent accidental overwrites, and ensure only intentional changes reach production or the integration branch.

---
