# Kubernetes

Run Krynetic as a **single replica** backed by a persistent volume. Do not scale a Deployment that shares one volume beyond one replica.

## Community edition

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: database
spec:
  replicas: 1
  selector:
    matchLabels:
      app: database
  template:
    metadata:
      labels:
        app: database
    spec:
      containers:
        - name: database
          image: ghcr.io/krynetic/database-releases:latest
          args: ["--server", "graphql"]
          env:
            - name: STORAGE_DIRECTORY
              value: /data
            - name: HOST
              value: "*"
          ports:
            - containerPort: 8085
          volumeMounts:
            - name: data
              mountPath: /data
      volumes:
        - name: data
          persistentVolumeClaim:
            claimName: db-data
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: db-data
spec:
  accessModes: [ReadWriteOnce]
  resources:
    requests:
      storage: 5Gi
---
apiVersion: v1
kind: Service
metadata:
  name: database
spec:
  selector:
    app: database
  ports:
    - name: http
      port: 8085
      targetPort: 8085
      protocol: TCP
```

## Licensed edition

Mount the license from a Secret and set `LICENSE_FILE`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: database
spec:
  replicas: 1
  selector:
    matchLabels:
      app: database
  template:
    metadata:
      labels:
        app: database
    spec:
      containers:
        - name: database
          image: ghcr.io/krynetic/database-releases:latest
          args: ["--server", "graphql"]
          env:
            - name: LICENSE_FILE
              value: /license.key
            - name: STORAGE_DIRECTORY
              value: /data
            - name: HOST
              value: "*"
          ports:
            - containerPort: 8085
          volumeMounts:
            - name: data
              mountPath: /data
            - name: license
              mountPath: /license.key
              subPath: license.key
      volumes:
        - name: data
          persistentVolumeClaim:
            claimName: db-data
        - name: license
          secret:
            secretName: db-license
```

```bash
kubectl create secret generic db-license --from-file=license.key=./license.key
```

## Health probes

Start the [KubernetesProbe server](../Servers/KubernetesProbe/README.md) next to your protocol servers:

```yaml
          args: ["--server", "graphql", "--server", "KubernetesProbe"]
          ports:
            - containerPort: 8085
            - containerPort: 9999
          startupProbe:
            httpGet: { path: /health/startup, port: 9999 }
            failureThreshold: 30
            periodSeconds: 2
          readinessProbe:
            httpGet: { path: /health/ready, port: 9999 }
            periodSeconds: 5
          livenessProbe:
            httpGet: { path: /health/live, port: 9999 }
            periodSeconds: 10
```

## Several protocols

```yaml
          args: ["--server", "GraphQL:8085", "--server", "MQTT:1883", "--server", "GRPC:50051"]
          ports:
            - { name: graphql, containerPort: 8085 }
            - { name: mqtt,    containerPort: 1883 }
            - { name: grpc,    containerPort: 50051 }
```

Expose only what you need in the Service. Use a separate Service (or none) for protocols that should stay internal.

## Restrict access

Allow only the workloads that need the database to reach it:

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: database-allow-app
spec:
  podSelector:
    matchLabels:
      app: database
  policyTypes: [Ingress]
  ingress:
    - from:
        - podSelector:
            matchLabels:
              app: my-app
      ports:
        - port: 8085
```

## Termination

Set a grace period of at least 30 seconds so the database finishes pending work on shutdown:

```yaml
    spec:
      terminationGracePeriodSeconds: 30
```
