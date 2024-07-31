# Branch Creation and Merging Guidelines

## 1. Branch Creation

### 1.1 Branch Types

#### Feature Branch

- **Purpose:** To develop new features or enhancements.
- **Naming Convention:** `feature/feature-name-vX.Y.Z`
- **Example:** `feature/new-dashboard-v2.0.2`

**Creation Steps:**
1. **Branch from Develop:** Create the feature branch from the latest develop branch.
2. **Branch Version:** Ensure the branch name reflects the version of master/main the feature targets.

**Example Command:**
```bash
git checkout develop
git pull origin develop
git checkout -b feature/new-dashboard-v2.0.2
