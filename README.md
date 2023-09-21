# SpringIO Kubernetes Notes

## Utilities

Generates kubernetes deployment yaml.  Integrates with skaffold nicely.

```xml
<dependency>
    <groupId>io.dekorate</groupId>
    <artifactId>kubernetes-spring-starter</artifactId>
</dependency>
```

```bash
skaffold run
```

## Ingress.  Expose services outside cluster.

Install nginx Ingress Controller

```java
@SpringBootApplication
@KubernetesApplication(ingress = @Ingress(expose = true))
```

## TAP Commands

List Packages

```bash
tanzu package installed list -n tap-install
```

List Supply Chains

```bash
tanzu apps cluster-supply-chain list
```

Get App details

```bash
ubuntu@master:~$ tanzu apps cluster-supply-chain get basic-image-to-url
---
# basic-image-to-url: Ready
---
Supply Chain Selectors
   TYPE          KEY                                   OPERATOR   VALUE
   fields        spec.image                            Exists
   expressions   apps.tanzu.vmware.com/workload-type   In         web
   expressions   apps.tanzu.vmware.com/workload-type   In         server
   expressions   apps.tanzu.vmware.com/workload-type   In         worker
```

Update TAP after changing tap-values.yaml

```bash
tanzu package installed update tap --values-file $HOME/tap-values.yaml -n tap-install
```