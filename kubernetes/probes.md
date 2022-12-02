# Kubernetes Probes

A **Liveness probe** is used to check when containers should be restarted. Probe a service to find deadlocks in which the application is running but unable to make progress.

A **Readiness probe** is used to check when a container is ready to start accepting traffic. When a pod is not ready, it is removed from service load balancers.

A **Startup probe** is used to know when an application has started. When used, liveness and readiness probes are disabled until startup is complete. This avoids the scenario of a long application startup being restarted when liveness isn't yet successful.

## Resources

[Configure Liveness, Readiness and Startup Probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)
