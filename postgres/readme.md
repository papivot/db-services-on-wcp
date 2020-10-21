helm install mypostgres bitnami/postgresql -n demonamespace1
 1581  kubectl get pods mypostgres-postgresql-0 -n demonamespace1
 1582  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1586  helm uninstall mypostgres -n demonamespace1
 1588  helm install mypostgres bitnami/postgresql -n demonamespace1 --persistence.storageClass=pacific-gold-storage-policy
 1591  helm show values bitnami/postgresql
 1594  mkdir postgres
 1595  cd postgres
 1596  helm show values bitnami/postgresql > values.yaml
 1603  helm install mypostgres bitnami/postgresql -n demonamespace1 --help
 1604  helm install mypostgres bitnami/postgresql -n demonamespace1 -f values.yaml
 1606  helm install mypostgres bitnami/postgresql -n demonamespace1 -f values.yaml
 1607  helm uninstall mypostgres -n demonamespace1
 1608  helm install mypostgres bitnami/postgresql -n demonamespace1 -f values.yaml
 1610  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1615  kubectl describe pvc data-mypostgres-postgresql-0
 1616  kubectl describe pvc data-mypostgres-postgresql-0 -n demonamespace1
 1617  kubectl get pvc data-mypostgres-postgresql-0 -n demonamespace1
 1618  kubectl get pvc data-mypostgres-postgresql-0 -n demonamespace1 -o yaml
 1622  helm uninstall mypostgres -n demonamespace1
 1623  helm install mypostgres bitnami/postgresql -n demonamespace1 -f values.yaml
 1625  kubectl describe pvc data-mypostgres-postgresql-0 -n demonamespace1
 1626  kubectl get pvc data-mypostgres-postgresql-0 -n demonamespace1 -o yaml
 1628  helm install mypostgres bitnami/postgresql -n demonamespace1 --help
 1629  helm uninstall mypostgres -n demonamespace1
 1630  helm install mypostgres bitnami/postgresql -n demonamespace1 --set persistence.storageClass=pacific-gold-storage-policy,persistence.size=1Gi,service.type=LoadBalancer
 1632  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1633  kubectl describe pvc data-mypostgres-postgresql-0 -n demonamespace1
 1637  kubectl get statefulset mypostgres-postgresql -n demonamespace1 -o yaml
 1639  kubectl get pvc data-mypostgres-postgresql-0 -o yaml
 1640  kubectl get pvc data-mypostgres-postgresql-0 -o yaml -n demonamespace1
 1641  kubectl get statefulset mypostgres-postgresql -n demonamespace1 -o yaml
 1644  helm uninstall mypostgres -n demonamespace1
 1645  helm install mypostgres bitnami/postgresql -n demonamespace1 --set persistence.storageClass=pacific-gold-storage-policy,persistence.size=1Gi,service.type=LoadBalancer,global.storageClass=pacific-gold-storage-policy
 1648  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1649  kubectl get pods mypostgres-postgresql-0 -n demonamespace1 -o yaml
 1650  kubectl get pvc data-mypostgres-postgresql-0 -o yaml -n demonamespace1
 1651  helm install mypostgres bitnami/postgresql -n demonamespace1 --set persistence.storageClass=pacific-gold-storage-policy --set persistence.size=1Gi --set service.type=LoadBalancer --set global.storageClass=pacific-gold-storage-policy
 1652  helm uninstall mypostgres -n demonamespace1
 1653  helm install mypostgres bitnami/postgresql -n demonamespace1 --set persistence.storageClass=pacific-gold-storage-policy --set persistence.size=1Gi --set service.type=LoadBalancer --set global.storageClass=pacific-gold-storage-policy
 1655  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1656  kubectl get pvc data-mypostgres-postgresql-0 -o yaml -n demonamespace1
 1657  kubectl edit pvc data-mypostgres-postgresql-0  -n demonamespace1
 1658  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1659  kubectl get pvc data-mypostgres-postgresql-0 -o yaml -n demonamespace1
 1660  kubectl get statefulset mypostgres-postgresql -n demonamespace1 -o yaml
 1663  helm uninstall mypostgres -n demonamespace1
 1672  kubectl describe pvc data-mypostgres-postgresql-0 -n demonamespace1
 1675  helm uninstall mypostgres -n demonamespace1
 1678  kubectl delete pvc data-mypostgres-postgresql-0 -n demonamespace1
 1707  vi postgress-pvc.yaml
 1708  kubectl apply -f postgress-pvc.yaml
 1709  vi postgress-pvc.yaml
 1710  kubectl apply -f postgress-pvc.yaml -n demonamespace1
 1711  vi postgress-pvc.yaml
 1712  kubectl apply -f postgress-pvc.yaml -n demonamespace1
 1714  kubectl describe pvc postgress-pvc -A
 1715  kubectl describe pvc postgress-pvc -n demonamespace1
 1716  kubectl describe pvc postgres-pvc -n demonamespace1
 1719  helm install mypostgres bitnami/postgresql -n demonamespace1 --set service.type=LoadBalancer,persistence.existingClaim=postgres-pvc
 1722  kubectl get pods mypostgres-postgresql-0 -n demonamespace1 -o yaml
 1723  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1725  kubectl describe pods mypostgres-postgresql-0 -n demonamespace1
 1731  helm status mypostgres -n demonamespace1
 1732  kubectl get secret --namespace demonamespace1 mypostgres-postgresql -o jsonpath="{.data.postgresql-password}" | base64 --decode
 1733  kubectl get secret --namespace demonamespace1 mypostgres-postgresql -o jsonpath="{.data.postgresql-password}" | base64 --decode;echo
 1734  export POSTGRES_PASSWORD=$(kubectl get secret --namespace demonamespace1 mypostgres-postgresql -o jsonpath="{.data.postgresql-password}" | base64 --decode)
 1737  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace1 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host mypostgres-postgresql -U postgres -d postgres -p 5432 -n demonamespace1
 1738  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace1 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host mypostgres-postgresql -U postgres -d postgres -p 5432
 1739  helm status mypostgres -n demonamespace1
 1740  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace1 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host mypostgres-postgresql.demonamespace1.svc.cluster.local -U postgres -d postgres -p 5432
 1741  export POSTGRES_PASSWORD=$(kubectl get secret --namespace demonamespace1 mypostgres-postgresql -o jsonpath="{.data.postgresql-password}" | base64 --decode)
 1742  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace1 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host mypostgres-postgresql.demonamespace1.svc.cluster.local -U postgres -d postgres -p 5432
 1744  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace2 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host mypostgres-postgresql.demonamespace1.svc.cluster.local -U postgres -d postgres -p 5432
 1746  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace2 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host 192.168.3.130 -U postgres -d postgres -p 5432
 1747  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace1 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host mypostgres-postgresql.demonamespace1.svc.cluster.local -U postgres -d postgres -p 5432
 1748  cd workspace/postgres
 1753  kubectl get svc mypostgres-postgresql-headless
 1754  kubectl get svc mypostgres-postgresql-headless -n demonamespace1
 1755  kubectl get svc mypostgres-postgresql-headless -n demonamespace1 -o yaml
 1763  kubectl run mypostgres-postgresql-client --rm --tty -i --restart='Never' --namespace demonamespace1 --image docker.io/bitnami/postgresql:11.9.0-debian-10-r48 --env="PGPASSWORD=$POSTGRES_PASSWORD" --command -- psql --host postgres.demonamespace2.svc.cluster.local -U postgres -d postgres -p 5432
