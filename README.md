Install **Operator Lifecycle Manager** (OLM) onto the cluster using Homebrew:

<https://sdk.operatorframework.io/docs/installation/#install-from-github-release>

```bash
operator-sdk olm install
```

Create Doppler secret in `/bootstrap/init`:

```bash
kubectl create secret generic \
 doppler-service-token \
  --from-literal dopplerToken=$(doppler configs tokens create --project avelin --config prd doppler-auth-token --plain) \
  --dry-run=client \
  -o yaml > doppler-secret.yaml
```
