1º Passo
Rodar o arquivo configmap-catalog.yaml 
`#kubectl apply -f configmap-catalog.yaml`

2º Passo
Rodar o arquivo configmap-coordinator.yaml
`#kubectl apply -f configmap-coordinator.yaml`

OBSERVAÇÃO: 
-------------
Dentro do arquivo configmap-coordinator.yaml, foi necessário remover a linha: `query.max-total-memory-per-node=2GB`, pois os testes foram feitos em um minikube.

3º Passo
Rodar o arquivo deployment-coordinator.yaml
`#kubectl apply -f deployment-coordinator.yaml`

Rodar 
`#kubectl apply -f trino-service.yaml`

expor trino 

`kubectl expose deployment tcb-trino-coordinator -n dados --type=LoadBalancer --name=lb-trino`
