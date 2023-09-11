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



