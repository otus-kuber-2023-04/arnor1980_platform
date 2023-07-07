# Выполнено ДЗ №7
# Тема: Операторы, CustomResourceDefinition

 - [x] Основное ДЗ
 - [ ] Задание с ?_


## В процессе сделано:
### Создание CustomResourceDefinition
 - Создан CustomResourceDefinition для сервиса MySQL
 - Создан pod с типом MySQL
 - Проверил что ресурс создается с необходимыми параметрами
 - Добавил в описание определения проверку на наличие обязательных параметров
### Создание оператора управления MySQL
 - Развернул оператор из готовых манифестов
 - Задания с ?_ просмотрел по диагонали ( Попытка запустить контроллер из предложнных вариантов реализации функций к успеху не привела ).
	- Скрипт зависает на определенном этапе. Причину не выяснял.
 - Проверил работу MySQL pod
 - CREATE, INSERT, SELECT отрабатывают
 - Задания резервного копирования базы и восстановления так же работают.
	- Единственный момент, если задание резервного копировния не прошло, то при восстановлении база будет пустая.

## Как запустить проект:
		- Из рабочего каталога запустить
				kubectl apply -f deploy/crd.yaml
				kubectl apply -f deploy/cr.yaml
				kubectl apply -f deploy/crd.yaml
				kubectl apply -f deploy/service-account.yml
				kubectl apply -f deploy/role.yml
				kubectl apply -f deploy/role-binding.yml
				kubectl apply -f deploy/deploy-operator.yml

## Как проверить работоспособность:
		Вывод: kubectl get jobs
			NAME                         COMPLETIONS   DURATION   AGE
			backup-mysql-instance-job    1/1           5s         32m
			restore-mysql-instance-job   1/1           23s        32m
		Вывод: export MYSQLPOD=$(kubectl get pods -l app=mysql-instance -o jsonpath="{.items[*].metadata.name}")
			   kubectl exec -it $MYSQLPOD -- mysql -potuspassword -e "select * from test;" otus-database
		
			mysql: [Warning] Using a password on the command line interface can be insecure.
			+----+-------------+
			| id | name        |
			+----+-------------+
			|  1 | some data   |
			|  2 | some data-2 |
			+----+-------------+
		
## PR checklist:
    - [x] Выставлен label с темой домашнего задания
