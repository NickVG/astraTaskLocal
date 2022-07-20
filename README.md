# astraTask
## Тестовое задание.
### Предварительные требоваия!
Установлены Virtualbox, vagrant, ansible. Есть VPN до неподсанкционных стран.

В Vagrantfile параметр `config.vm.box = "generic/ubuntu2004"`. Если нет VPN, то требуется скачать и добавить vagrant box. При добавлении vagrant box вручную требуется изменить config.vm.box на новое имя.

Запуск стенда `vagrant up`


`.\Vagrantfile` - описание ВМ используемой для тестовго задания.

`.\provisioning` - файлы необхожмые для запуска provisioning (ansible, docker-compose, prometheus, grafana)

  - `inventory` - inventory ansible
  - `main.yml` - основной плейбук ansible

`.\provisioning\roles\node_exporter` - роль ansible Для node_exporter

`.\provisioning\compose` - набор файлов для docker-compose 
 
  - `docker-compose.yml` - файл docker-compose
  - `prometheus.yml` - файл настроек prometheus

`.\provisioning\compose\grafana` - директория с файлами настроек grafana (dashboard и конфигурация)


