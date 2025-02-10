# RabbitMQ
Der ScorpioBroker wird mit dem Messagebus RabbitMQ betrieben. Die Installation erfolgt über den Bitnami Helm Chart.

## Voraussetzungen

* Kubernetes 1.23+
* Helm 3.8.0+

## Installation

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
 
# Chart installieren
helm install rabbitmq bitnami/rabbitmq -n scorpio --create-namespace -f values.yaml
 
# Passwort ermitteln
kubectl get secret --namespace scorpio rabbitmq -o jsonpath="{.data.rabbitmq-password}" | base64 -d
 
# Upgrade
helm upgrade rabbitmq bitnami/rabbitmq -n scorpio -f values.yaml
```

## Parameter
Die wichtigen Parameter werden im values.yaml konfiguriert.

## License

Copyright © 2024 ADDIX GmbH.
