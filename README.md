# Выполнено ДЗ №5
# Тема: Security

 - [x] Основное ДЗ

## В процессе сделано:
### Задача № 1
 - Создана сервисная учетная запись bob
 - Создана привязка учетной записи bob к кластероной роли Cluster-Admin
 
### Задача №2 
 - Создано простанство имен prometheus
 - Создана сервисная учетная запись carol в рамках пространства имен prometheus
 - Создана кластерная роль дающая право чтения и мониторинга POD'ов всего кластера
 - Создана привязка всех севрисных учетных записей пространства имен prometheus: "system:serviceaccounts:prometheus" 
   к созданной кластерно роли
### Задача №3
 - Создано простнаство имен dev
 - Создана сервисная учетная запись jane
 - Создана привязка кластерной роли admin к учетной записи jane в рамках пространства dev
 - Создана сервисная учетная запись ken
 - Создана привязка кластерной роли view к учетной записи ken в рамках пространства dev

## Как запустить проект
    - Запустить minikube в режиме авторизации RBAC: mikube start --extra-config=apiserver.authorization-mode=RBAC

## Как проверить работоспособность:
### Задача #1
    - kubectl describe clusterrolebindings.rbac.authorization.k8s.io bob-clusterrolebinding

### Задача #2
    - kubectl describe sa carol -n prometheus
    - kubectl describe clusterrole cluster-pod-reader
    - kubectl describe clusterrolebindings.rbac.authorization.k8s.io prometheus-cluster-pod-read

### Задача #3
    - kubectl describe rolebindings.rbac.authorization.k8s.io -n dev dev-admin
    - kubectl describe rolebindings.rbac.authorization.k8s.io -n dev dev-view				
		
## PR checklist:
    - [x] Выставлен label с темой домашнего задания
