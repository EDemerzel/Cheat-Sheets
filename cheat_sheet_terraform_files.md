# Terraform Files Cheat Sheet

## 1 · Core Configuration Files

| File                   | Purpose                                                       |
|------------------------|---------------------------------------------------------------|
| **`main.tf`**          | Defines compute, networking, storage & other resources        |
| **`variables.tf`**     | Declares input variables for reuse & parameterisation         |
| **`outputs.tf`**       | Lists values to show after `terraform apply` (endpoints, IDs) |
| **`terraform.tfvars`** | Provides default variable values                              |
| **`providers.tf`**     | Configures required providers & versions                      |
| **`versions.tf`**      | Locks Terraform / provider versions                           |
| **`backend.tf`**       | Remote state backend (S3, GCS, Azure Blob, etc.)              |

## 2 · Module‑Specific Structure

```text
modules/
└─ <module_name>/
   ├─ main.tf      # resources for this module
   ├─ variables.tf # module inputs
   └─ outputs.tf   # module outputs
```

## 3 · CI/CD & Automation

| File                               | Typical Location   | Description                       |
|------------------------------------|--------------------|-----------------------------------|
| `.github/workflows/terraform.yml`  | GitHub Actions     | Plan / apply pipeline             |
| `.gitlab-ci.yml`                   | GitLab CI          | Equivalent CI steps               |
| `Jenkinsfile`                      | Jenkins CI         | Declarative stages for plan/apply |

## 4 · Security & Secrets Management

| File                  | Notes                                                 |
|-----------------------|-------------------------------------------------------|
| `.gitignore`          | Exclude `terraform.tfstate*`, `.terraform/`, secrets  |
| `secrets.auto.tfvars` | **Encrypted / vaulted** values—never plaintext in VCS |

## 5 · Environment‑Specific Patterns

```text
environments/
├─ dev/     main.tf  terraform.tfvars
├─ staging/ main.tf  terraform.tfvars
└─ prod/    main.tf  terraform.tfvars
```

## 6 · Custom Scripts & Helpers

| Script                 | Purpose                                         |
|------------------------|-------------------------------------------------|
| `scripts/init.sh`      | Runs `terraform init` with plugins & backends   |
| `scripts/validate.sh`  | Runs `terraform validate` + `fmt`               |
| `scripts/destroy.sh`   | Automated `terraform destroy` cleanup           |

## 7 · State Management & Locking

| File                      | Role                                         |
|---------------------------|----------------------------------------------|
| `terraform.tfstate`        | Current state map of real infrastructure    |
| `terraform.tfstate.backup` | Last known good state                       |
| `terraform.lock.hcl`       | Provider version consistency                |
