```
1664  helm install mysql stable/mysql -n demonamespace1 --set service.type=LoadBalancer,mysqlRootPassword=secretpassword,mysqlUser=my-user,mysqlPassword=my-password,mysqlDatabase=my-database,persistence.size=1Gi,persistence.storageClass=pacific-gold-storage-policy
 1666  helm install mysql stable/mysql -n demonamespace1 --set service.type=LoadBalancer,mysqlRootPassword=secretpassword,mysqlUser=my-user,mysqlPassword=my-password,mysqlDatabase=my-database,persistence.size=1Gi,persistence.storageClass=pacific-gold-storage-policy
 1667  helm install mysql bitnami/mysql -n demonamespace1 --set service.type=LoadBalancer,mysqlRootPassword=secretpassword,mysqlUser=my-user,mysqlPassword=my-password,mysqlDatabase=my-database,persistence.size=1Gi,persistence.storageClass=pacific-gold-storage-policy
 1669  kubectl get pods mysql-master-0 -n demonamespace1
 1670  kubectl describe pods mysql-master-0 -n demonamespace1
 1673  kubectl get pvc data-mysql-master-0 -o yaml
 1674  kubectl get pvc data-mysql-master-0 -o yaml -n demonamespace1
 1676  helm uninstall mysql -n demonamespace1
 1679  kubectl delete pvc -n demonamespace1 data-mysql-master-0
 1680  kubectl delete pvc -n demonamespace1 data-mysql-slave-0
 1682  helm uninstall mysql -n demonamespace1
 1683  helm install mysql bitnami/mysql -n demonamespace1 --set service.type=LoadBalancer,mysqlRootPassword=secretpassword,mysqlUser=my-user,mysqlPassword=my-password,mysqlDatabase=my-database,persistence.size=1Gi,persistence.storageClass=pacific-gold-storage-policy
 1697  kubectl describe pvc data-mysql-master-0
 1698  kubectl describe pvc data-mysql-master-0 -n demonamespace1
 1699  kubectl get pvc data-mysql-master-0 -n demonamespace1 -o yaml
 1700  helm uninstall mysql -n demonamespace1
 1702  kubectl delete pvc -n demonamespace1 data-mysql-slave-0
 1703  kubectl delete pvc -n demonamespace1 data-mysql-master-0
 ```
