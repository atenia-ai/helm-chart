# Helm Charts

## Fluvio

```bash
mkdir -p charts
helm package fluvio-app --destination charts
helm package fluvio-sys --destination charts
mv 
```

```bash
helm repo index ./charts --url https://atenia.github.io/helm-chart
```
