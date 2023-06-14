# Выполнено ДЗ №5
# Тема: Мониторинг сервиса в кластере k8s

 - [x] Основное ДЗ

## В процессе сделано:
 - Кастомный образ nginx отдающий метрики в формате nginx
 - Развенут deployment из 3х pod nginx
 - Развернут nginx exporter для преобразования метрик nginx в формат prometheus  
 - Установлен CRD Prometheus Operator
 - Создан ServiceMonitor для мониторинга сервиса nginx

## PR checklist:
    - [x] Выставлен label номером домашнего задания
