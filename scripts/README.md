# 1

1. Создаем s3-бакет:

```bash
bash create_bucket.sh
```

1. Создаем сервисный аккаунт:

```bash
bash create_service_account.sh
```

1. Создаем виртуальную сеть, подсеть, NAT для доступа в Интернет и группу безопасности:

```bash
bash create_dataproc_cluster.sh
```

1. Создаем jump-сервер для доступа в кластер из вне:

```bash
bash create_jump_vm.sh
```

Копируем на созданную машину пбличный ключ:

```bash

```bash
scp -i $HOME/.ssh/yc $HOME/.ssh/yc {публичный-IP-вашей-ВМ}:.ssh/yc
```

1. Попадаем через Jupyter

```bash
# Проброс порта с вашей машины на Jump Server
ssh -i ~/.ssh/yc -L 8888:localhost:8888 {публичный-IP-вашей-ВМ}

# Проброс порта с Jump Server на мастер-ноду
ssh -i .ssh/yc -L 8888:localhost:8888 ubuntu@{fqdn-мастер-ноды}

# Запуск Jupyter
jupyter notebook
```
