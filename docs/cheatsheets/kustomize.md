# Kustomize CheatSheet

## Kustomize Secrets

Literal:
```sh
kustomize edit add secret sl-demo-app --from-literal=db-password=xxxxx
```

From File:
```sh
kustomize edit add secret sl-demo-app --from-file=file/path
kustomize edit add secret sl-demo-app --from-env-file=env/path.env
```

The file will be modified with those values:
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

(...)

secretGenerator:
- literals:
  - db-password=xxxxx
  name: sl-demo-app
  type: Opaque
```

## Kustomize Images

```sh
TAG_VERSION=3.4.5 # Usually this var comes from a pipeline
kustomize edit set image foo/bar=foo/bar:$TAG_VERSION
```

The file will be modified with those values:
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

(...)

images:
- name: foo/bar
  newName: foo/bar
  newTag: 3.4.5
```