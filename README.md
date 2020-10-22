# k8s-config-demo

This is a demo app for testing Spring Boot external configuration via Kubernetes configmaps.

You need [Skaffold](https://skaffold.dev/docs/install/).

Build defaults to your user name as the Docker ID repo prefix.
If you want a different repo prefix change `$USER` to the one you prefer. 

To build the app:

```
skaffold build --default-repo $USER
```

To deploy the app to Kubernetes:

```
skaffold run --default-repo $USER --port-forward
```

> This will port forward to http://localhost:8080

To test the configuration:

```
$ curl -w'\n' localhost:8080/
Hello world!
```

To inspect the environment:

```
$ curl -w'\n' localhost:8080/actuator/env
```

To clean up:

```
skaffold delete
```
