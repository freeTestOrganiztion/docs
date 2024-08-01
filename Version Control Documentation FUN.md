# 🎯 Version Control Documentation

Welcome to the **Version Control Documentation**! This guide will walk you through our branching strategy, versioning schemes, and workflows. Ready to dive in? Let's get started!

<details>
<summary><h2>🛠️ Detailed Branching Strategy</h2></summary>

Here’s a clear guide to understanding our branching strategy. This section outlines the different types of branches we use and how they work together.

## 1.1 Branch Types

### Branch Types Overview

**Understanding Our Branches:**

- **📦 Master/Main Branch:**
  - **Purpose:** This is our stable branch, containing production-ready code. All code that’s deployed to clients is merged into this branch.
  - **Versioning:** Follows Semantic Versioning (SEMVER): `MAJOR.MINOR.PATCH`.
    - **MAJOR:** For breaking changes.
    - **MINOR:** For new features that are backward-compatible.
    - **PATCH:** For minor bug fixes.
  - **Update Rules:** 
    - **MAJOR Changes:** Increase the MAJOR version.
    - **MINOR Changes:** Increase the MINOR version.
    - **PATCH Fixes:** Increase the PATCH version.

- **🚀 Develop Branch:**
  - **Purpose:** This branch serves as the integration point for new features and bug fixes before they are merged into `master/main`.
  - **Versioning:** Uses the format `MAJOR.MINOR.PATCH-dev-FEATURE.BUG.ITERATION`.
    - **dev:** Indicates the development stage.
    - **FEATURE, BUG, ITERATION:** Tracks the progress of development.
  - **Update Rules:** 
    - **FEATURE Increment:** When a new feature branch is merged.
    - **BUG Increment:** When a bug fix branch is merged.
    - **ITERATION Increment:** For each development iteration or change.

- **🔨 Feature/Bug Branches:**
  - **Purpose:** These branches are used to develop new features or fix bugs. They are created from the `develop` branch and are intended to keep the main codebase stable.
  - **Naming Convention:**
    - Feature branches: `feature/feature-name-vX.Y.Z`
    - Bug branches: `bug/bug-description-vX.Y.Z`
  - **Update Rules:** 
    - **Versioning:** These branches inherit their version from the `develop` branch but do not have their own version numbers.

### Example Branch Structure

Here’s an example of how our branches might evolve:

```plaintext
master/main -> 2.0.0
      |
      v
develop -> 2.0.0-dev-0.0.0
      |
      v
feature/login-screen-v2.0.0
bug/fix-login-error-v2.0.0
      |
      v
develop -> 2.0.0-dev-1.1.0
      |
      v
master/main -> 2.1.0
```
- **Starting Point:** `master/main` at version `2.0.0`.
- **Development Stage:** `develop` at `2.0.0-dev-0.0.0`, with feature and bug branches.
- **Updates:** `develop` progresses to `2.0.0-dev-1.1.0` as changes are integrated, and `master/main` is updated to `2.1.0`.
This structure ensures smooth integration of new features and bug fixes, leading to stable releases.
</details>

<details>
<summary><h2>📋 Document for Master/Main </h2></summary>

This section outlines how we manage versioning and updates for our `master/main` branch. Understanding these guidelines helps ensure that our releases are consistent and well-documented.

## 2.1 Versioning Scheme

### Versioning Scheme for `master/main`

- **Semantic Versioning (SEMVER):** We use the format `MAJOR.MINOR.PATCH` for our releases.
  - **MAJOR:** Represents significant changes that break backward compatibility.
  - **MINOR:** Indicates backward-compatible new features or enhancements.
  - **PATCH:** Denotes small bug fixes or minor improvements that are backward-compatible.

## 2.2 Rules for Versioning

### Versioning Rules

**How to Increment Versions:**

- **MAJOR Version Increment:**
  - Triggered by breaking changes or major updates.
  - **Example:** Updating from `1.0.0` to `2.0.0` might involve a complete redesign of the application.

- **MINOR Version Increment:**
  - Applied when new features are added that do not break backward compatibility.
  - **Example:** Moving from `2.0.0` to `2.1.0` could introduce new functionality such as a new payment gateway.

- **PATCH Version Increment:**
  - Used for backward-compatible bug fixes or minor tweaks.
  - **Example:** Changing from `2.1.0` to `2.1.1` may fix a minor issue like a small UI glitch.

## 2.3 Examples

### Versioning Examples

**Here’s how different versions look:**

- **Version 1.0.0:** The initial release featuring core functionalities.
- **Version 1.1.0:** Introduced additional reporting features.
- **Version 1.1.1:** Addressed minor bugs related to user settings.
- **Version 2.0.0:** Marked a major overhaul of the user interface and core features.

These examples illustrate how our version numbers reflect the nature and scale of changes in each release.

</details>
