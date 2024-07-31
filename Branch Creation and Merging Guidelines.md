# Branch Creation and Merging Guidelines

## 1. Branch Creation

### 1.1 Branch Types

#### 1. Feature Branch

- **Purpose:** To develop new features or enhancements.
- **Naming Convention:** `feature/feature-name-vX.Y.Z`
- **Example:** `feature/new-dashboard-v2.0.2`

- **Creation Steps:**
  1. **Branch from Develop:** Create the feature branch from the latest develop branch.
  2. **Branch Version:** Ensure the branch name reflects the version of master/main the feature targets.

- **Example Command:**
```bash
git checkout develop
git pull origin develop
git checkout -b feature/new-dashboard-v2.0.2
```

#### 2. Bug Branch

- **Purpose:** To fix specific bugs or issues.
- **Naming Convention:** `bug/bug-description-vX.Y.Z`
- **Example:** `bug/fix-login-error-v2.0.2`

- **Creation Steps:**
  1. **Branch from Develop:** Create the bug branch from the latest develop branch.
  2. **Branch Version:** Ensure the branch name reflects the version of master/main the bug fix targets.

- **Example Command:**
```bash
git checkout develop
git pull origin develop
git checkout -b bug/fix-login-error-v2.0.2
```
#### 3. Develop Branch

- **Purpose:** Integration branch for all features and bug fixes before merging into master/main.
- **Naming Convention:** Align with the base version of master/main with a suffix indicating development progress.
- **Example:** `2.0.2-dev-0.0.0` for initial development from `2.0.2`.

- **Creation Steps:**
  1. **Branch from Master/Main:** Create develop branch from the latest master/main.
 
- **Example Command:**
```bash
git checkout master
git pull origin master
git checkout -b develop
```

## 2. Branch Merging

### 2.1 Merging Bug Branches into Develop

- **Purpose:** Integrate bug fixes into the development branch.
- **Merge Commit Comment Format:**
```
<Develop Branch Version>
Bug Branch Merged - <Branch Name>
- List of fixed bugs
```
- **Example:**
```
2.0.2-dev-0.1.0
Bug Branch Merged - bug/fix-login-error-v2.0.2
- Fixed login error on user authentication
- Resolved session timeout issue
```
- **Merge Steps:**
  1. **Checkout Develop:** Ensure you are on the `develop` branch.
  2. **Merge Bug Branch:** Merge the bug branch into `develop`.
  3. **Add Merge Message:**
```bash
git checkout develop
git pull origin develop
git merge bug/fix-login-error-v2.0.2
git push origin develop
```
When prompted, enter the multiline commit message:
```
2.0.2-dev-0.1.0
Bug Branch Merged - bug/fix-login-error-v2.0.2
- Fixed login error on user authentication
- Resolved session timeout issue
```
