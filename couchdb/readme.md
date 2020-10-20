```
helm repo add couchdb https://apache.github.io/couchdb-helm
helm repo update
helm inspect values couchdb/couchdb
helm pull --untar couchdb/couchdb
modify values.yaml
helm install my-couchdb ./couchdb -n demo1


# helm install my-couchdb couchdb/couchdb
# helm upgrade my-couchdb ./couchdb -n demo1
```
