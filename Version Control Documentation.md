# Version Control Documentation

## 1. Detailed Branching Strategy

### 1.1 Branch Types

#### Master/Main Branch:
- **Purpose:** The production-ready branch. All code that is deployed to clients will be merged into this branch.
- **Versioning:** Uses Semantic Versioning (SEMVER) format: `MAJOR.MINOR.PATCH`.
- **Update Rules:** Increment the version number based on the changes being introduced (e.g., breaking changes, new features, bug fixes).

#### Develop Branch:
- **Purpose:** Serves as the integration branch for new features and bug fixes. It’s a staging area before merging into `master/main`.
- **Versioning:** Uses a pre-release suffix format: `MAJOR.MINOR.PATCH-dev-FEATURE.BUG.ITERATION`.
- **Update Rules:** The version number reflects the base version of `master/main` and includes a suffix to indicate development progress, broken down into FEATURE, BUG, and ITERATION.

#### Feature/Bug Branches:
- **Purpose:** Created from the `develop` branch to work on new features or bug fixes.
- **Naming Convention:**
  - Feature branches: `feature/feature-name-vX.Y.Z`
  - Bug branches: `bug/bug-description-vX.Y.Z`
- **Update Rules:** These branches do not have their own versioning. The versioning of the feature/bug is determined by the version of the `develop` branch they are merged into.

### 1.2 Example Branch Structure

```
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


## 2. Document for Master/Main

### 2.1 Versioning Scheme

- **Semantic Versioning (SEMVER):** `MAJOR.MINOR.PATCH`
  - **MAJOR:** Significant changes that break backward compatibility.
  - **MINOR:** Backward-compatible additions or enhancements.
  - **PATCH:** Backward-compatible bug fixes or minor improvements.

### 2.2 Rules for Versioning

- **MAJOR Version Increment:**
  - When there are breaking changes or significant updates to core features.
  - **Example:** Moving from `1.0.0` to `2.0.0` could represent a complete redesign of the UI.

- **MINOR Version Increment:**
  - When new features are added that are backward-compatible.
  - **Example:** Moving from `2.0.0` to `2.1.0` could include new payment gateway integration.

- **PATCH Version Increment:**
  - For minor bug fixes or small improvements that are backward-compatible.
  - **Example:** Moving from `2.1.0` to `2.1.1` could address a minor UI bug.

### 2.3 Examples

- **Version 1.0.0:** Initial release with core functionalities.
- **Version 1.1.0:** Added new reporting features.
- **Version 1.1.1:** Fixed minor bugs related to user settings.
- **Version 2.0.0:** Major overhaul of the user interface and core features.

## 3. Document for Develop

### 3.1 Versioning Scheme

- **Version Format:** `MAJOR.MINOR.PATCH-dev-FEATURE.BUG.ITERATION`
  - **MAJOR.MINOR.PATCH:** Reflects the base version of `master/main`.
  - **dev:** Indicates that this version is in development.
  - **FEATURE:** Represents the number of feature branches merged.
  - **BUG:** Represents the number of bug branches merged.
  - **ITERATION:** Indicates the individual iterations or changes made during development.

### 3.2 Rules for Versioning

- **Maintain Alignment with Master/Main:**
  - Ensure that the version on the `develop` branch aligns with the `master/main` version, with an additional suffix to indicate development status.
  - **Example:** If `master/main` is `2.0.2`, `develop` could start as `2.0.2-dev-0.0.0`.

- **Version Increment Rules:**
  - **FEATURE:** Increment this number with each new feature branch merged into the `develop` branch.
    - **Example:** `2.0.2-dev-1.0.0` indicates 1 feature branch has been merged.
  - **BUG:** Increment this number with each bug branch merged into the `develop` branch.
    - **Example:** `2.0.2-dev-1.1.0` indicates 1 feature branch and 1 bug branch have been merged.
  - **ITERATION:** Increment this number for each individual development iteration or change made after merging features and bugs.
    - **Example:** `2.0.2-dev-1.1.1` indicates 1 feature, 1 bug, and 1 iteration.

### 3.3 Examples

- **Develop Branch Version 2.0.2-dev-0.0.0:**
  - **Base version:** `2.0.2`
  - **Development progress:** No features or bug fixes yet, no iterations.

- **Develop Branch Version 2.0.2-dev-1.1.0:**
  - **Base version:** `2.0.2`
  - **Development progress:** 1 feature merged, 1 bug fix merged, no additional iterations yet.

- **Develop Branch Version 2.1.0-dev-2.2.1:**
  - **Base version:** `2.1.0`
  - **Development progress:** 2 features merged, 2 bug fixes merged, 1 iteration.

## 4. Document for Bug/Feature Branches

### 4.1 Versioning Scheme

- **Branch Naming:**
  - **Feature Branches:** `feature/feature-name-vX.Y.Z`
    - **Example:** `feature/new-dashboard-v2.0.2`
  - **Bug Branches:** `bug/bug-description-vX.Y.Z`
    - **Example:** `bug/fix-login-error-v2.0.2`
- The version part (vX.Y.Z) indicates the version of the `master/main` branch that the branch is targeting.

### 4.2 Rules for Versioning

- **Feature Branches:**
  - **Naming:** Use `feature/feature-name-vX.Y.Z` to denote the version of the `master/main` branch the feature is targeting.
    - **Example:** `feature/new-dashboard-v2.0.2` targets version 2.0.2 of the `master/main` branch.

- **Bug Branches:**
  - **Naming:** Use `bug/bug-description-vX.Y.Z` to indicate the version of the `master/main` branch that the bug fix is targeting.
    - **Example:** `bug/fix-login-error-v2.0.2` targets version `2.0.2` of the `master/main` branch.

### 4.3 Examples

- **Feature Branch Example:** `feature/new-payment-v2.0.2` for adding a new payment feature.
- **Bug Branch Example:** `bug/fix-header-issue-v2.0.2` for fixing an issue with the header.

## 5. Workflow and Version Handling

### 5.1 Workflow

- **Create Branches:**
  - **Feature Branch:** Created from the `develop` branch for new features.
  - **Bug Branch:** Created from the `develop` branch for bug fixes.
  - **Naming Convention:** Include the version of the `master/main` branch the branch is targeting.

- **Develop Code:**
  - Work on the feature or bug fix on the respective branch.
  - Ensure code follows all guidelines and performs as expected.

- **Merge to Develop:**
  - After testing and validation, merge the feature or bug branch into the `develop` branch.
  - Ensure that the `develop` branch is updated to reflect the changes.

- **Test Develop Branch:**
  - Perform thorough testing on the `develop` branch.
  - Update the version of the `develop` branch as needed to reflect the changes (using the `FEATURE.BUG.ITERATION` suffix).

- **Merge to Master/Main:**
  - Once the `develop` branch is stable and production-ready, merge it into the `master/main` branch.
  - Increment the `master/main` version according to the changes (MAJOR, MINOR, PATCH).

- **Tag and Release:**
  - Tag the release on the `master/main` branch with the updated version number.
  - Create release notes detailing the changes, compatibility, and deployment information.

### 5.2 Versioning and Version Control Handling

- **Feature and Bug Fixes:**
  - The version number of the feature and bug branches should align with the `master/main` version they target.
    - **Example:** If `master/main` is at `2.0.2`, a feature branch targeting this version would be named `feature/feature-name-v2.0.2`.

- **Develop Branch Versions:**
  - The `develop` branch should include an additional suffix to differentiate it from the `master/main` branch (e.g., `2.0.2-dev-1.1.1`).
  - Update the `develop` branch version as new features or fixes are integrated, using the `FEATURE.BUG.ITERATION` suffix.

- **Release Management:**
  - Ensure that each release from the `master/main` branch is tagged and documented properly.
  - Maintain a clear history of changes and version increments to facilitate rollback if necessary.

### Example Workflow

- **Create Feature Branch:**
  - **Branch Name:** `feature/new-dashboard-v2.0.2`
  - Work on the new-dashboard feature targeting `master/main 2.0.2`.

- **Merge Feature Branch:**
  - Merge `feature/new-dashboard-v2.0.2` into the `develop` branch.
  - Update `develop` branch version to `2.0.2-dev-1.0.0` if this is the first feature branch merged.

- **Prepare for Release:**
  - Ensure the `develop` branch is stable and incorporates all features and bug fixes.

- **Merge the Develop Branch into Master/Main:**
  - Tag: `v2.1.0` if new features were added.
  - Create release notes and deploy the new version.
