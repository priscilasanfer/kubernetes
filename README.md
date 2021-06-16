# Kubernetes

## Cursos:
 - [Kubernetes: Pods, Services e ConfigMaps](https://cursos.alura.com.br/course/kubernetes-pods-services-configmap)
 - [Kubernetes: Deployments, Volumes e Escalabilidade](https://cursos.alura.com.br/course/kubernetes-deployments-volumes-escalabilidade) 

## Comandos

*recursos:*
- svc (service )
- node
- pod
- rs (replicaset)
- deployment
- replicaset
- configmap
- pv (persistence volume)
- pvc (persistent volume claim) 
- hpa ( horizontal Pod Autoscaler)

*Listar todos os recursos:*
kubectl get RECURSO

*Listar todos os recursos de forma wide*
kubectl get RECURSO -o wide

*Ver os detalhes de um recursos*
kubectl describe RECURSO NOME_RECURSO

*Criar pod de forma imperativa:*
kubectl run NOME_POD --image=IMAGEM_CONTAIER:VERSÃO
kubectl run nginx-pod --image=nginx:latest

*Acompanhar o pod em tempo real*
kubectl get pods -- watch

*Ver os detalhes de um recurso*
kubectl describe RECURSO RECURSO_NAME

*Editar um pod*
kubectl edit pod NOME_POD

*Criar um recurso de forma declarativa*
kubectl apply -f .\NOME_DO_ARQUIVO.yaml

*Deletar um serviço* 
kubectl delete RECURSO NOME_RECURSO

*Deletar um serviço a partir do yaml*
kubectl delete -f .\NOME_DO_ARQUIVO.yaml

*Executar comandos dentro do pod*
kubectl exec -it NOME_POD  -- bash
kubectl exec -it portal-noticias -- bash

ou acessar um container específico dentro do pod:
kubectl exec-it NOME_DO_POD --container NOME_DO_CONTAINER --bash 

ctrl + d - sair do modo iterativo

*Deletar todos os recursos pelo tipo*
kubectl delete RECURSO --all

*Ver histórico de deploy*
kubectl rollout history deployment NOME_RECURSO

*Colocar uma anotação*
kubectl apply -f .\NOME_DO_ARQUIVO.yaml --record

*Alterar a causa do deploy*
kubectl annotate deployment NOME_DO_DEPLOYMENT kubernetes.io/change-cause=”DESCRIÇ O”

*Rollback de uma versão específica*
kubectl rollout undo deployment NOME_RECURSO --to-revision=NUMERO_DA_VERSAO
