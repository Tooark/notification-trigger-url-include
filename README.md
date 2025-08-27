# 📦 Gitlab include for Notification Trigger URL — `notification-trigger-url-include`

This Gitlab include sends a notification to a specified URL with details about the status of a pipeline, including vulnerability scan results from Trivy.

## 🔧 Inputs

- **`webhook-url`**: URL to send the notification to.
- **`status`**: Status of the pipeline (e.g., success, failure).
- **`message`**: Main message for the notification.
- **`project`**: Name of the project.
- **`branch`**: Branch name.
- **`repository`**: Repository name.
- **`commit`**: Commit hash.
- **`cloud-provider`**: Cloud provider (e.g., AWS, Azure, GCP).
- **`user`**: User who triggered the include.
- **`build-url`**: URL of the build.

### Optional Inputs - Vulnerability Docker Image Counts
- **`critical-count`**: Number of critical vulnerabilities.
- **`high-count`**: Number of high vulnerabilities.
- **`medium-count`**: Number of medium vulnerabilities.
- **`low-count`**: Number of low vulnerabilities.
- **`unknown-count`**: Number of unknown vulnerabilities.
- **`total-count`**: Total number of vulnerabilities.

## 🚀 How to Use

```yaml
include:
- remote: 'https://raw.githubusercontent.com/Tooark/notification-trigger-url-include/main/.gitlab-ci.yml'
  inputs:
    webhook-url: "https://example.com/webhook"
    status: "success"
    message: "Pipeline CI/CD - success"
    project: "$CI_PROJECT_NAME"
    branch: "$CI_COMMIT_BRANCH"
    repository: "$CI_REPOSITORY_URL"
    commit: "$CI_COMMIT_SHORT_SHA"
    cloud-provider: "AWS"
    user: "$GITLAB_USER_NAME"
    build-url: "$CI_PIPELINE_URL"
```

## 🚀 How to Use with Docker Vulnerabilities Report

```yaml
include:
- remote: 'https://raw.githubusercontent.com/Tooark/notification-trigger-url-include/main/.gitlab-ci.yml'
  inputs:
    webhook-url: "https://example.com/webhook"
    status: "success"
    message: "Pipeline CI/CD - success"
    project: "$CI_PROJECT_NAME"
    branch: "$CI_COMMIT_BRANCH"
    repository: "$CI_REPOSITORY_URL"
    commit: "$CI_COMMIT_SHORT_SHA"
    cloud-provider: "AWS"
    user: "$GITLAB_USER_NAME"
    build-url: "$CI_PIPELINE_URL"
    ####
    critical-count: "2"
    high-count: "5"
    medium-count: "8"
    low-count: "3"
    unknown-count: "1"
    total-count: "19"
```

## Contribution

Contributions are welcome! Feel free to open issues and pull requests in the [Notification Trigger Url](https://Gitlab.com/Tooark/notification-trigger-url-include/issues) repository.

---

## Contributors

The following users are contributing to the project:

| <img src="https://avatars.Gitlabusercontent.com/u/97809060?v=4" width=120> | 
| :-------------------------------------------------------------------------: |
| [**Stenio Ignacio**](https://Gitlab.com/stenioignacio) |