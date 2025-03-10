# Instrucciones


# Requisitos

- Kubernetes
- Kubectl
- Helm
- OpenLens: Recomendable para visualizar los objetos creados en Kubernetes 

# Instalación

- Instala los manifest en Kuberentes
helm install alcoyano -f values-desarrollo.yaml --create-namespace --namespace mi-proyecto .
- Para secesivos cambios
helm upgrade alcoyano -f values-desarrollo.yaml --create-namespace --namespace mi-proyecto .
- Cambia el namespace de trabajo para que no tengas que especificarlo continuamente
kubectl config set-context --current --namespace=mi-proyecto

- Visualiza los Cronjobs creados
kubectl get cronjob 
- Crea un job específico
kubectl create job --from=cronjob/procesar-imagenes procesamiento-$(date +%s)
- Visualiza los jobs
kubectl get job
- Visualiza los pods
kubectl get pod
- Visualiza los logs de los pods
kubectl logs -l app=alcoyano
- Elimina los jobs
kubectl delete jobs -l app=alcoyano