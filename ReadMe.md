## Helm Tolgee

This is the unofficial helm package for [Tolgee.io](https://tolgee.io/) project.

> With Tolgee, developers are not involved in localization process after the process of development itself. They develop the app, integrate Tolgee integration libraries and deploy an instance, where translators can change the localization texts in the context of web application. Texts are then synchronized with Tolgee server (REST API) and there is no need for developers to be part of the localization process.

This chart provide :

- Tolgee
- PostgreSQL or External PosgresSQL connection

## Quick Start

```bash
helm repo add tolgee https://throrin19.github.io/helm-tolgee/

helm install tolgee tolgee/tolgee \
--set postgresql.auth.password=moreSecurePassword
```
## Values

| Value | Description | Default Value   |
| --- | --- |-----------------|
| image.tag | Tolgee version | 3.37.0          |
| service.port | Service port | 8080            |
| ingress.enabled | Enable or not Ingress | `false`         |
| tolgee.persistence.enabled | Activate or not postgres persistence | `true`          |
| tolgee.persistence.storageClass | PVC Storage class | -               |
| tolgee.persistence.size | PVC size | 1Gi             |
| postgresql.host | Database host | -               |
| postgresql.auth.database | Tolgee database | tolgee          |
| postgresql.standalone.enabled | Enable or not postgres installation in kubernetes cluster | `true`          |
| postgresql.auth.username | Tolgee Database user | tolgee          |
| postgresql.auth.password | Tolgee password | tolgee_password |
| postgresql.auth.postgresPassword | Root password | root_password   |
| postgresql.auth.secret | Secret file parameters to use | -               |
| postgresql.auth.secret.enabled | Enable or not the secret configuration file | false           |
| postgresql.auth.secret.name | Secret file name | -               |
| postgresql.auth.secret.passwordKey | Secret parameter password key | -               |
| postgresql.auth.secret.usernameKey | Secret parameter username key | -               |
| postgresql.primary.persistence.size | PVC size | 1Gi             |

> You can see all [postgres configs here](https://artifacthub.io/packages/helm/bitnami/postgresql)