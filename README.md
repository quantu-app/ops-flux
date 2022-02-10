# ops-flux

## Sealed secrets

```bash
kubeseal --fetch-cert --controller-name=sealed-secrets --controller-namespace=kube-public > pub-sealed-secrets.pem
```

## Docker creds

```bash
kubectl create secret generic regcred \
    --namespace kube-system \
    --from-file=.dockerconfigjson=/home/$USER/.docker/config.json \
    --type=kubernetes.io/dockerconfigjson \
    --dry-run=client \
    -o yaml
```
