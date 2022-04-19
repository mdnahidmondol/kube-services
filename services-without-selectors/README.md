#Special Service Types: Services without selectors

Services without selectors are used abstract others kinds of backends
- You want use a database during development/testing and a prod database in production
- You want to point your service to a service in a differnet Namespace or on another cluster
- You want to gradually migrate your workload to kubernetes


## note: this endpoint cannot be a clusterIP


