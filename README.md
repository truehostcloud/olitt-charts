# Olitt Helm Charts

## Usage

```bash
helm repo add olitt https://<organization>.github.io/olitt-charts
helm repo update
helm install my-app olitt/olitt-app --set image.repository=<image> --set image.tag=<tag>
```

## Charts

| Chart | Description |
| --- | --- |
| [olitt-app](charts/olitt-app) | Runs a single containerized web application |

## olitt-app values

| Key | Default | Description |
| --- | --- | --- |
| `image.repository` | `nginx` | Container image |
| `image.tag` | chart `appVersion` | Image tag |
| `imagePullSecrets` | `[]` | Secrets for pulling from a private registry |
| `service.port` | `80` | Port the container listens on |
| `ingress.enabled` | `true` | Expose the app through an Ingress |
| `ingress.className` | `""` | Ingress class |
| `ingress.hosts` | `chart-example.local` | Hostnames and paths |
| `resources` | `{}` | CPU and memory requests and limits |
| `serviceAccount.automount` | `false` | Mount the service account token |
| `livenessProbe`, `readinessProbe` | TCP check on the service port | Health checks |
