# Выполнено ДЗ №4
# Тема: Volumes, Storages, StatefulSet

 - [x] Основное ДЗ
 - [x] Задание с * secrets


## В процессе сделано:
 - Развернут StatefulSet с локальным хранилищем типа S3 MiniIO с PV размером 10 ГБ на основе PVC
 - Создан простой секрет
	- Данные секрета добавлены в конфигурацию MIMIIO

## Как запустить проект:
		- Из рабочего каталога запустить
				kubectl apply -f miniio-statefulset-with-secrets.yaml
				
## Как проверить работоспособность:
        - kubectl get statefulsets
		- kubectl get pv
		- kubectl get pvc
		
## PR checklist:
    - [x] Выставлен label с темой домашнего задания
    - [x] Высталвен label с необходимстью Review
