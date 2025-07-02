# Kubernetes Essentials Cheat Sheet

| Concept                     | One‑liner                                                                  |
| --------------------------- | -------------------------------------------------------------------------- |
| **Pod**                     | Smallest deployable unit; one or more containers sharing network + volumes |
| **Deployment**              | Declarative controller for stateless pods (rolling update, rollback)       |
| **StatefulSet**             | Ordered, sticky identities; stable PVCs (e.g., databases)                  |
| **DaemonSet**               | Ensure exactly one pod per node (logs, metrics)                            |
| **Job / CronJob**           | Run finite or scheduled tasks                                              |
| **Service**                 | Stable virtual IP; ClusterIP / NodePort / LoadBalancer / Headless          |
| **Ingress / Gateway API**   | Route HTTP(S); TLS termination                                             |
| **ConfigMap / Secret**      | Inject config & sensitive data                                             |
| **RBAC**                    | `Role`, `ClusterRole`, `RoleBinding`, `ClusterRoleBinding`                 |
| **HorizontalPodAutoscaler** | Scale pods on CPU/memory/custom metrics                                    |
| **kubectl**                 | Primary CLI—`kubectl get pods`, `kubectl describe node`, etc.              |
| **Helm**                    | Package manager (`helm install nginx nginx-stable/nginx`)                  |

> **Tip:** Prefer **Infrastructure‑as‑Code** (`kubectl apply -f`, Helm, Kustomize, Terraform provider) and GitOps (ArgoCD, Flux).
