Kustomize example:

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


