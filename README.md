# appstore

![Version: 1.2.1](https://img.shields.io/badge/Version-1.2.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.4.1](https://img.shields.io/badge/AppVersion-1.4.1-informational?style=flat-square)

A Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | 10.16.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| ACCOUNT_DEFAULT_HTTP_PROTOCOL | string | `"http"` | Choose http or https for the protocol that is used by external users to access the appstore web service. |
| SET_BUILD_ENV_FROM_FILE | bool | `false` | Set environment variables from a file. |
| affinity | object | `{}` |  |
| ambassador.flag | bool | `true` | register appstore with ambassador flag: <True or False> |
| appStorage.claimName | string | `nil` |  |
| appStorage.existingClaim | bool | `false` |  |
| appStorage.storageClass | string | `nil` |  |
| appStorage.storageSize | string | `"2Gi"` |  |
| apps.DATASOURCE_PASSWORD | string | `""` |  |
| apps.DATASOURCE_URL | string | `""` |  |
| apps.DATASOURCE_USERNAME | string | `""` |  |
| apps.DICOMGH_GOOGLE_CLIENT_ID | string | `""` |  |
| apps.FLYWAY_DATASOURCE_PASSWORD | string | `""` |  |
| apps.FLYWAY_DATASOURCE_URL | string | `""` |  |
| apps.FLYWAY_DATASOURCE_USERNAME | string | `""` |  |
| appstoreEntrypointArgs | string | `"make start"` | Allow for a custom entrypoint command via the values file. |
| artillery.loadArrivalRate | int | `10` |  |
| artillery.loadDuration | int | `10` |  |
| artillery.loadTest | bool | `false` |  |
| artillery.smokeTest | bool | `false` | When either smokeTest or loadTest is true, set CREATE_TEST_USERS, TEST_USERS_PATH under django settings. |
| createHomeDirs | bool | `true` | Create Home directories for users |
| db.host | string | `"postgresql"` |  |
| db.name | string | `"appstore"` |  |
| db.port | int | `5432` |  |
| django.ALLOW_DJANGO_LOGIN | string | `""` | show Django log in fields (true | false) |
| django.ALLOW_SAML_LOGIN | string | `""` | show SAML log in fields (true | false) |
| django.APPSTORE_DJANGO_PASSWORD | string | `""` |  |
| django.APPSTORE_DJANGO_USERNAME | string | `"admin"` |  |
| django.AUTHORIZED_USERS | string | `""` | user emails for oauth providers |
| django.CREATE_TEST_USERS | string | `"false"` | create test users for load testing |
| django.DEV_PHASE | string | `"prod"` |  |
| django.DOCKSTORE_APPS_BRANCH | string | `"master"` | Defaults to "master". Specify "develop" to switch. |
| django.EMAIL_HOST_PASSWORD | string | `""` | password of account to use for outgoing emails |
| django.EMAIL_HOST_USER | string | `""` | email of account to use for outgoing emails |
| django.IMAGE_DOWNLOAD_URL | string | `""` | Specify URL to use for the "Image Download" link on the top part of website. |
| django.RECIPIENT_EMAILS | string | `""` | list of appstore registration emails |
| django.REMOVE_AUTHORIZED_USERS | string | `""` | user emails to remove from an already-existing database |
| django.SESSION_IDLE_TIMEOUT | int | `3600` | idle timeout for user web session |
| django.TEST_USERS_PATH | string | `"/usr/src/inst-mgmt/artillery-tests/payloads"` | parent directory where the users.txt would be mounted |
| django.TEST_USERS_SECRET | string | `"test-users-secret"` | secret file deployed on the cluster to fetch the test users |
| djangoSettings | string | `"cat"` | set the theme for appstore (cat, braini, restartr, scidas) |
| extraEnv | object | `{}` |  |
| fetcherImage.pullPolicy | string | `"IfNotPresent"` | pull policy |
| fetcherImage.repository | string | `"helxplatform/url-fetch"` | repository where image is located |
| fetcherImage.tag | string | `"latest"` |  |
| fullnameOverride | string | `""` |  |
| global.ambassador_id | string | `nil` | specify the id of the ambassador for Tycho-launched services. |
| global.stdnfsPvc | string | `"stdnfs"` | the name of the PVC to use for user's files |
| gunicorn.workers | int | `5` | Set the number of gunicorn workers. |
| helx_ui | object | `{"REACT_APP_ANALYTICS":"","REACT_APP_HELX_SEARCH_URL":"","REACT_APP_SEMANTIC_SEARCH_ENABLED":"true","REACT_APP_UI_BRAND_NAME":"","REACT_APP_WORKSPACES_ENABLED":"true"}` | Setting for helx-ui |
| helx_ui.REACT_APP_ANALYTICS | string | `""` | HeLx Mixpanel project analytics token |
| helx_ui.REACT_APP_HELX_SEARCH_URL | string | `""` | Helx Search URL |
| helx_ui.REACT_APP_SEMANTIC_SEARCH_ENABLED | string | `"true"` | Enable/Disable helx-ui search. |
| helx_ui.REACT_APP_UI_BRAND_NAME | string | `""` | Helx Branding (cat, braini, restartr, scidas, eduhelx) |
| helx_ui.REACT_APP_WORKSPACES_ENABLED | string | `"true"` | Enable/Disable helx-ui workspaces. |
| image.pullPolicy | string | `"IfNotPresent"` | pull policy |
| image.repository | string | `"containers.renci.org/helxplatform/appstore"` | repository where image is located |
| image.tag | string | `nil` |  |
| imagePullSecrets | list | `[]` | credentials for a private repo |
| init | object | `{"resources":{"cpus":"250m","memory":"250Mi"}}` | Resource for Tycho init container. Defaults cpus|250m memory|250Mi |
| irods.BRAINI_RODS | string | `""` |  |
| irods.IROD_COLLECTIONS | string | `""` |  |
| irods.IROD_ZONE | string | `""` |  |
| irods.NRC_MICROSCOPY_IRODS | string | `""` |  |
| irods.RODS_PASSWORD | string | `""` |  |
| irods.RODS_USERNAME | string | `""` |  |
| irods.enabled | bool | `false` | enable irods support (true | false) |
| logLevel | string | `"info"` | Set the log level for the application. Overriden to be "debug" if DEBUG setting is true in the configmap. |
| nameOverride | string | `""` |  |
| networkPolicyLabels.role | string | `"appstore"` |  |
| nodeSelector | object | `{}` |  |
| oauth.GITHUB_CLIENT_ID | string | `""` |  |
| oauth.GITHUB_KEY | string | `""` |  |
| oauth.GITHUB_NAME | string | `""` |  |
| oauth.GITHUB_SECRET | string | `""` |  |
| oauth.GITHUB_SITES | string | `""` |  |
| oauth.GOOGLE_CLIENT_ID | string | `""` |  |
| oauth.GOOGLE_KEY | string | `""` |  |
| oauth.GOOGLE_NAME | string | `""` |  |
| oauth.GOOGLE_SECRET | string | `""` |  |
| oauth.GOOGLE_SITES | string | `""` |  |
| oauth.OAUTH_PROVIDERS | string | `""` | oauth providers separated by commas (google, github) |
| oauth.claimName | string | `"appstore-oauth-pvc"` |  |
| oauth.existingClaim | bool | `false` |  |
| oauth.storageClass | string | `nil` |  |
| parent_dir | string | `"/home"` | directory that will be used to mount user's home directories in |
| podAnnotations | object | `{}` |  |
| postgresql | object | `{"audit":{"logConnections":true,"logHostname":true},"enabled":true,"global":{"postgresql":{"postgresqlDatabase":"appstore-oauth","postgresqlPassword":"renci","postgresqlUsername":"renci"}},"networkPolicyEnabled":true,"persistence":{"existingClaim":"appstore-postgresql-pvc","mountPath":"/postgresql/12","storageClass":null,"subPath":"postgresql12"},"postgresqlDataDir":"/postgresql/12/data","postgresqlPostgresPassword":"renciAdmin","primary":{"labels":{"np-label":"appstore-db"},"podLabels":{"np-label":"appstore-db"}},"volumePermissions":{"enabled":true}}` | postgresql settings |
| postgresql.audit | object | `{"logConnections":true,"logHostname":true}` | postgresql logs |
| postgresql.global.postgresql | object | `{"postgresqlDatabase":"appstore-oauth","postgresqlPassword":"renci","postgresqlUsername":"renci"}` | postgresql credentials |
| postgresql.networkPolicyEnabled | bool | `true` | enable/disable postgresql network policy, allows traffic to and from appstore pod only. |
| postgresql.persistence | object | `{"existingClaim":"appstore-postgresql-pvc","mountPath":"/postgresql/12","storageClass":null,"subPath":"postgresql12"}` | postgresql persistence storage |
| postgresql.postgresqlDataDir | string | `"/postgresql/12/data"` | postgresql DATA DIR |
| postgresql.primary | object | `{"labels":{"np-label":"appstore-db"},"podLabels":{"np-label":"appstore-db"}}` | postgresql labels |
| replicaCount | int | `1` |  |
| resources.limits.cpu | string | `"400m"` |  |
| resources.limits.memory | string | `"625Mi"` |  |
| resources.requests.cpu | string | `"100m"` |  |
| resources.requests.memory | string | `"300Mi"` |  |
| runAsRoot | bool | `true` |  |
| saml.ASSERTION_URL | string | `""` |  |
| saml.AUTHORITY_URL | string | `""` |  |
| saml.ENTITY_ID | string | `""` |  |
| saml.cache.APPSTORE_DIRECTORY | string | `"/saml"` |  |
| saml.cache.APPSTORE_FILE | string | `"saml_metadata.xml"` |  |
| saml.cache.FETCH_FILE | string | `"/data/saml_metadata.xml"` |  |
| saml.cache.FETCH_INTERVAL | string | `"60000"` |  |
| saml.cache.claimName | string | `"saml-cache"` |  |
| saml.cache.enabled | bool | `false` |  |
| saml.cache.storageClass | string | `""` |  |
| saml.cache.storageSize | string | `"20M"` |  |
| security.isolatedApps | bool | `true` |  |
| service.name | string | `"http"` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.create | bool | `true` | specifies whether a service account should be created |
| serviceAccount.name | string | `nil` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| shared_dir | string | `"shared"` | name of directory to use for shared data |
| subpath_dir | string | `nil` | Name of directory to use for a user's home directory.  If null then the user's username will be used. |
| tolerations | list | `[]` |  |
| updateStrategy.type | string | `"Recreate"` | 'RollingUpdate' or 'Recreate'. Must use Recreate if mounting PVCs due to multi-attach errors. |
| useSparkServiceAccount | bool | `false` | Set to true, when using blackbalsam. |
| userStorage.createPVC | bool | `false` | Create a PVC for user's files.  If false then the PVC needs to be created outside of the appstore chart. |
| userStorage.nfs.createPV | bool | `false` |  |
| userStorage.nfs.path | string | `nil` |  |
| userStorage.nfs.server | string | `nil` |  |
| userStorage.storageClass | string | `nil` |  |
| userStorage.storageSize | string | `"10Gi"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
