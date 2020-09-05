# AgnOps umbrella chart configuration:

The following table lists the configurable parameters of the AgnOps chart and their default values.

|              Parameter               |                 Description                  |            Default            |
| ------------------------------------ | -------------------------------------------- | ----------------------------- |
| `global.scmProvider`                 | SCM Provider [github/gitlab/bitbucket]       | `github`                      |
| `global.cloudName`                   | Be used in pipeline.cloudFilters - Optional  | `myCloudAliasName`            |
| `global.nodeSelector`                | Pod's Node assignment                        | `{}`                          |
| `global.tolerations`                 | Pod tolerations                              | `[]`                          |
| `global.affinity`                    | Pod affinity policy                          | `{}`                          |
| `global.ingress.tls`                 | Verifies the SSL certificate of the host     | `true`                        |
| `oauth2-proxy.enabled`               | Enable oauth2-proxy deployment               | `true`                        |
| `oauth2-proxy.clientId`              | OAuth Client ID                              | `""`                          |
| `oauth2-proxy.clientSecret`          | OAuth Client Secret                          | `""`                          |
| `oauth2-proxy.cookieSecret`          | OAuth Cookie Secret                          | `""`                          |
| `cloud-wrapper.enabled`              | Enable cloud-wrapper deployment              | `true`                        |
| `cloud-wrapper.cloudProvider`        | AWS/Azure/GCP/Alibaba                        | `AWS`                         |
| `notification.enabled`               | Enable notification deployment               | `true`                        |
| `notification.slack.enabled`         | Enable Slack notifications for a status      | `false`                       |
| `notification.slack.webhookUrl`      | Slack Webhook URL                            | `""`                          |
| `notification.smtpDetails.enabled`   | Enable Email notifications for a status      | `false`                       |
| `notification.smtpDetails.host`      | SMTP host                                    | `"smtp.gmail.com"`            |
| `notification.smtpDetails.port`      | SMTP port                                    | `"587"`                       |
| `notification.smtpDetails.username`  | SMTP username                                | `""`                          |
| `notification.smtpDetails.password`  | SMTP password                                | `""`                          |
| `notification.mailgun.enabled`       | Enable Email notifications for a status      | `false`                       |
| `notification.mailgun.apiKey`        | mailgun Private API key                      | `""`                          |
| `notification.mailgun.domain`        | mailgun registered domain                    | `""`                          |
| `webhook-manager.webhookSecret`      | Webhook secret (automatically randomize)     | `"<random 20H string>"`       |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```
helm upgrade --install aws-github agnops/agnops --set global.scmProvider=github --set cloud-wrapper.cloudProvider=AWS --namespace=ci-cd-tools
```