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

## HiK8s system

```bash
helm package hik8s-system --destination docs
```

Render templates

```bash
helm template hik8s-system ./hik8s-system --output-dir rendered-templates -n hik8s-system
```
