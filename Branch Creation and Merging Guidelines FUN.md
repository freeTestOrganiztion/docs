# Branch Creation and Merging Guidelines

<details>
<summary><h2>1. Branch Creation 🛠️</h2></summary>

## 1.1 Branch Types

### 1. Feature Branch 🌟

- **Purpose:** Create and innovate! Feature branches are your playground for developing new features or enhancements.
- **Naming Convention:** `feature/feature-name-vX.Y.Z`
- **Example:** `feature/new-dashboard-v2.0.2`

- **Creation Steps:**
  1. **Branch from Develop:** Start your feature branch from the latest `develop` branch to ensure you’re working with the most recent code.
  2. **Branch Version:** Name your branch with the version of `master/main` it targets, so everyone knows exactly which version it’s aligned with.

- **Example Command:**
  ```bash
  git checkout develop
  git pull origin develop
  git checkout -b feature/new-dashboard-v2.0.2
  ```
  
### 2. Bug Branch 🐛
- **Purpose:** Squash those bugs! Use bug branches to address specific issues and keep the codebase smooth.
- **Naming Convention:** `bug/bug-description-vX.Y.Z`
- **Example:** `bug/fix-login-error-v2.0.2`

- **Creation Steps:**
  1. **Branch from Develop:** Create your bug branch from the latest `develop` branch to make sure you’re working with the most up-to-date code.
  2. **Branch Version:** Use a branch name that reflects the version of `master/main` that the bug fix targets.
 
- **Example Command:**
  ```bash
  git checkout develop
  git pull origin develop
  git checkout -b bug/fix-login-error-v2.0.2
  ```

  ### 3. Develop Branch 🔄
- **Purpose:** The integration hub! The `develop` branch is where all features and bug fixes come together before hitting `master/main`.
- **Naming Convention:** Align with the base version of `master/main` with a suffix indicating development progress.
- **Example:** `2.0.2-dev-0.0.0` for starting development from `2.0.2`.
  
- **Creation Steps:**
  1. **Branch from Master/Main:** Create the `develop` branch from the latest `master/main` to start fresh.
 
- **Example Command:**
  ```bash
  git checkout master
  git pull origin master
  git checkout -b develop
  ```
  </details>
