# Helm Charts

## Fluvio

```bash
mkdir -p charts
helm package fluvio-app --destination charts
helm package fluvio-sys --destination charts
mv 
```

```bash
helm repo index ./docs --url https://chart.atenia.ai/
```

## HiK8s system

```bash
helm template hik8s-system ./hik8s-system --output-dir rendered-templates -n hik8s-system
```
