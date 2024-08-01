# Version Control Documentation

## 1. Detailed Branching Strategy

### 1.1 Branch Types

#### Master/Main Branch:
- **Purpose:** The production-ready branch. All code that is deployed to clients will be merged into this branch.
- **Versioning:** Uses Semantic Versioning (SEMVER) format: `MAJOR.MINOR.PATCH`.
- **Update Rules:** Increment the version number based on the changes being introduced (e.g., breaking changes, new features, bug fixes).

#### Develop Branch:
- **Purpose:** Serves as the integration branch for new features and bug fixes. It’s a staging area before merging into master/main.
- **Versioning:** Uses a pre-release suffix format: `MAJOR.MINOR.PATCH-dev-FEATURE.BUG.ITERATION`.
- **Update Rules:** The version number reflects the base version of master/main and includes a suffix to indicate development progress, broken down into FEATURE, BUG, and ITERATION.

#### Feature/Bug Branches:
- **Purpose:** Created from the develop branch to work on new features or bug fixes.
- **Naming Convention:**
  - Feature branches: `feature/feature-name-vX.Y.Z`
  - Bug branches: `bug/bug-description-vX.Y.Z`
- **Update Rules:** These branches do not have their own versioning. The versioning of the feature/bug is determined by the version of the develop branch they are merged into.

### 1.2 Example Branch Structure

