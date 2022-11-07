# TPKubernetes-AySo
Integrantes: Thiago Cingolani 50533 - Lucas Lodigiani 50641 - Azul Cura 50539 - Sebastián Helguero 50624 - Nicolas Casa 50640
### Creamos el archivo html
vim index.html
### Creamos un Dockerfile
vim Dockerfile
### Costruir imagen con tag v1
docker build --tag v1 .
### Construimos container
docker run -d -p 8080:80 --name grupo3 v1
### Indicamos el dockerhub
docker tag v1:latest thiagocingolani/grupo3-ayso:v1
### Nos logeamos en docker hub
docker login
### Pusheamos la imagen en docker hub
docker push thiagocingolani/grupo3-ayso:v1
### Creamos un cluster
kind create cluster --name tp-ayso
### Creamos un namespace
kubectl create ns grupo3
### Creamos el replicaset
vim replicaset.yaml
### Aplicamos los cambios 
kubectl apply -f replicaset.yaml
### Verificamos que funcione
kubectl get nodes
