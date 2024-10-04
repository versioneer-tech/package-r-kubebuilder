<img src="https://github.com/versioneer-tech/package-r/raw/main/frontend/public/img/logo.png" height="40"/> 

# packageR-kubebuilder

Scaffolded Kubernetes APIs for the [packageR](https://github.com/versioneer-tech/package-r) tool as generated via [kubebuilder](https://github.com/kubernetes-sigs/kubebuilder).

Note: Relevant code and the CRDs are manually vendored into packageR.

```
kubebuilder init --domain package.r --repo github.com/versioneer-tech/package-r-kubebuilder

kubebuilder create api --group package.r --version alphav1 --kind Source --namespaced=true

make manifests

rsync -av  ./package-r-kubebuilder/config/crd/bases/ ./package-r/k8s/crds  

rsync -av  ./package-r-kubebuilder/api ./package-r/k8s  
```