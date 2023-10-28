Kustomize example:

To install kustomize:

curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash

$ tree .
├── base
│   ├── configMap.yaml
│   ├── deployment.yaml
│   ├── kustomization.yaml
│   ├── route.yaml
│   └── service.yaml
├── overlays
│   ├── production
│   │   ├── configmap.yaml
│   │   ├── deployment.yaml
│   │   ├── kustomization.yaml
│   │   └── route.yaml
│   └── staging
│       ├── configmap.yaml
│       ├── kustomization.yaml
│       └── route.yaml
└── README.md

$ for i in dev staging production; do oc new-project $i; done

$ oc project dev

$ kustomize build base | kubectl apply -f -
$ kustomize build overlays/staging | kubectl apply -f -
$ kustomize build overlays/production | kubectl apply -f -

$ oc get route 
$ oc get route -n staging
$ oc get route -n production
