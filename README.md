# RabbitMQ
Der ScorpioBroker wird mti dem Messagebus RabbitMQ betrieben. Die Installation erfolgt über den Bitnami Helm Chart.

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

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.