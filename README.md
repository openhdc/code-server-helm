# Code Server Helm

## Packaging Helm Charts

To package the Helm charts for `code-server-go` and `code-server-python`, use the following commands:

```bash
helm package code-server-go
helm package code-server-python
```

## Updating the Helm Repository Index

After packaging the charts, update the Helm repository index with the following command:

```bash
helm repo index . --url ./helm
```

This will generate or update the `index.yaml` file in the current directory, pointing to the specified URL.
