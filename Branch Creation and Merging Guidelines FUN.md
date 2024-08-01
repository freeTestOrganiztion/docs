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

<details>
<summary><h2>2. Branch Merging 🔄</h2></summary>

## 2.1 Merging Bug Branches into Develop 🐛

- **Purpose:** Integrate those bug fixes! Bring fixes from bug branches into the development branch to ensure stability.
- **Merge Commit Comment Format:**
  ```vbnet
  <Develop Branch Version>
  Bug Branch Merged - <Branch Name>
  - List of fixed bugs
  ```
- **Merge Commit Comment Example :**
  ```vbnet
  2.0.2-dev-0.1.0
  Bug Branch Merged - bug/fix-login-error-v2.0.2
  - Fixed login error on user authentication
  - Resolved session timeout issue
  ```
- **Merge Steps:**
    1. **Checkout Develop:** Switch to the `develop` branch to prepare for the merge.
    2. **Merge Bug Branch:** Bring the bug branch changes into `develop`.
    3. **Add Merge Message:** Craft a clear and descriptive merge message.
- **Merge Commands:**
  ```bash
  git checkout develop
  git pull origin develop
  git merge bug/fix-login-error-v2.0.2
  git push origin develop
  ```
  When prompted, enter the multiline commit message:
  ```vbnet
  2.0.2-dev-0.1.0
  Bug Branch Merged - bug/fix-login-error-v2.0.2
  - Fixed login error on user authentication
  - Resolved session timeout issue
  ```

## 2.2 Merging Feature Branches into Develop 🌟

- **Purpose:** Integrate new features! Bring the exciting new features from feature branches into `develop`.
- **Merge Commit Comment Format:**
 ```vbnet
  <Develop Branch Version>
  Feature Branch Merged - <Branch Name>
  - List of added features
  ```
- **Merge Commit Comment Example :**
  ```vbnet
  2.0.2-dev-1.1.0
  Feature Branch Merged - feature/new-dashboard-v2.0.2
  - Added new dashboard feature
  - Enhanced user interface with widgets
  ```
- **Merge Steps:**
  1. **Checkout Develop:** Make sure you're on the `develop` branch for the merge.
  2. **Merge Feature Branch:** Bring the feature branch changes into `develop`.
  3. **Add Merge Message:** Craft a clear and descriptive merge message.
- **Merge Commands:**
  ```bash
  git checkout develop
  git pull origin develop
  git merge feature/new-dashboard-v2.0.2
  git push origin develop
  ```
  When prompted, enter the multiline commit message:
  ```vbnet
  2.0.2-dev-1.1.0
  Feature Branch Merged - feature/new-dashboard-v2.0.2
  - Added new dashboard feature
  - Enhanced user interface with widgets
  ```

## 2.3 Merging Develop into Master/Main 🚀

- **Purpose:** Prepare for release! Merge the `develop` branch into the production-ready `master/main` branch.
- **Merge Commit Comment Format:**
  ```vbnet
  <Master/Main Branch Version>
  Develop Branch Merged - <Branch Name>
  Features:
  - List of added features
  Bugs:
  - List of fixed bugs
  ```
- **Merge Commit Comment Example :**
  ```vbnet
  2.1.0
  Develop Branch Merged - develop-2.0.2-dev-1.1.0
  Features:
  - Added new dashboard feature
  - Enhanced user interface with widgets
  Bugs:
  - Fixed login error on user authentication
  - Resolved session timeout issue
  ```
- **Merge Steps:**
  1. **Checkout Master/Main:** Switch to the `master/main` branch to prepare for the merge.
  2. **Merge Develop Branch:** Integrate changes from `develop` into `master/main`.
  3. **Create Tag and Release:** Tag the release version and push changes.
- **Merge Commands:**
  ```bash
  git checkout master
  git pull origin master
  git merge develop
  git tag -a v2.1.0 -m "Release version 2.1.0"
  git push origin master --tags
  ```
  When prompted, enter the multiline commit message:
  ```vbnet
  2.1.0
  Develop Branch Merged - develop-2.0.2-dev-1.1.0
  Features:
  - Added new dashboard feature
  - Enhanced user interface with widgets
  Bugs:
  - Fixed login error on user authentication
  - Resolved session timeout issue
  ```

  ## 2.4 Merging Master/Main into Develop 🔄

- **Purpose:** Keep `develop` in sync! Bring the latest updates from `master/main` into the `develop` branch.
- **Merge Commit Comment Format:**
  ```vbnet
  <Develop Branch Version>
  Develop Branch <Branch Name> synced with Master/Main Branch <Version>
  ```
- **Merge Commit Comment Example :**
  ```vbnet
  2.0.3-dev-0.0.0
  Develop Branch 2.0.3-dev-0.0.0 synced with Master/Main Branch 2.0.3
  ```
- **Merge Steps:**
  1. **Checkout Develop:** Switch to the `develop` branch for the merge.
  2. **Merge Master/Main Branch:** Bring changes from `master/main` into `develop`.
  3. **Push Changes:** Update the remote `develop` branch.
- **Merge Commands:**
  ```bash
  git checkout develop
  git pull origin develop
  git merge master
  git push origin develop
  ```
  When prompted, enter the multiline commit message:
  ```vbnet
  2.0.3-dev-0.0.0
  Develop Branch 2.0.3-dev-0.0.0 synced with Master/Main Branch 2.0.3
  ```

</details>

<details>
<summary><h2>3. Tag Creation and Release Notes 🏷️</h2></summary>

## 3.1 Release Tag Format 📍

- **Tag Name:** Use the format `vMAJOR.MINOR.PATCH` for clear versioning.
- **Example Tag:** `v2.1.0`

## 3.2 Release Notes Structure 📝

- **Title:**
  ```vbnet
  Release vMAJOR.MINOR.PATCH - Release Date
  ```
- **Body:**
  ```text
  ## Overview
  This release includes the following updates:
  
  ## Features
  - **Feature 1:** Description of the feature.
  - **Feature 2:** Description of the feature.
    
  ## Bug Fixes
  - **Bug 1:** Description of the bug fix.
  - **Bug 2:** Description of the bug fix.
  
  ## Known Issues
  - **Issue 1:** Description of known issues or limitations.
  
  # Compatibility
  - **Repository 1:** Version of Repository it works with.
  - **Repository 2:** Version of Repository it works with.
  
  ## Additional Information
  - **Release Date:** YYYY-MM-DD
  - **Deployed To:** Indicate whether the release is live on client environments or in staging.
  - **Release Notes Prepared By:** Your Name or Team
  ```

## 3.3 Example Release Notes Body 📄

Here’s how the body of the release notes might look when creating a new tag after merging `develop` into `master/main`:
- **Tag Name:** `v2.1.0`
- **Release Notes Body:**
  ```vbnet
  Release v2.1.0 - 2024-07-30
  
  ## Overview
  This release brings new features, bug fixes, and improvements to enhance the overall functionality and user experience.
  
  ## Features
  - **New Dashboard Feature:** Added a new dashboard with customizable widgets to improve user interaction and data visualization.
  - **Enhanced User Interface:** Updated the user interface with a more modern design, including improved navigation and responsive elements.
  
  ## Bug Fixes
  - **Login Error Fix:** Resolved a critical login error that prevented users from accessing their accounts.
  - **Session Timeout Issue:** Fixed an issue where sessions were timing out too quickly, causing inconvenience to users.
  
  ## Known Issues
  - **Mobile Layout Bug:** Minor issues with layout on smaller mobile screens. A fix is planned for the next release.
  
  # Compatibility
  - **Authentication Service:** v2.0.1
  - **Payment Gateway:** v3.1.4
  
  ## Additional Information
  - **Release Date:** 2024-07-30
  - **Deployed To:** Production environment; live for all users.
  - **Release Notes Prepared By:** Release Management Team
  ```

## 3.4 Command for Creating the Tag and Release 🛠️

- **Create Tag:**
  ```bash
  git tag -a v2.1.0 -m "Release v2.1.0 - Includes new features and bug fixes"
  ```
- **Push Tag:**
  ```bash
  git push origin v2.1.0
  ```

</details>
