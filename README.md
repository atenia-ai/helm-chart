# Helm Charts

To update the index:

```bash
helm repo index ./docs --url https://chart.atenia.ai/
```

## Fluvio

```bash
mkdir -p docs
helm package fluvio-app --destination docs
helm package fluvio-sys --destination docs
```

## HiK8s

```bash
helm package hik8s --destination docs
```

Render templates

```bash
helm template hik8s ./hik8s --output-dir rendered-templates \
  -n hik8s-system \
  --set-string auth.createSecret=false
```

Manual installation from local

```bash
kubectl create namespace hik8s-system
kubectl label namespace hik8s-system pod-security.kubernetes.io/enforce=privileged

helm install hik8s ./hik8s \
  -n hik8s-system \
  --set-string auth.credentials.clientId="abc" \
  --set-string auth.credentials.clientSecret="abc"
```

Uninstall chart and remove repo

```bash
helm uninstall hik8s && kubectl delete namespace hik8s-system && helm repo remove atenia
```
