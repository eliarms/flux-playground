# Flux demo repository

https://github.com/eliarms/flux-playground

# Installation

```
kubectl create ns flux
export GHUSER=eliarms
fluxctl install \
--git-user=${GHUSER} \
--git-email=${GHUSER}@users.noreply.github.com \
--git-url=git@github.com:${GHUSER}/flux-demo \
--git-path=namespaces,workloads \
--git-branch=main
--namespace=flux | kubectl apply -f -
```
kubectl -n flux rollout status deployment/flux
```

# Setup SSH key
```
fluxctl identity --k8s-fwd-ns flux
```

# Sync repo manually
```
fluxctl sync --k8s-fwd-ns flux
```
