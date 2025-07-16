# Kargo WorkShop

* Clonar kargo-helm, portall, portall-manifests
```shell
git clone git@github.com:softonic-development/kargo-helm.git
git clone git@github.com:softonic-development/portall.git
git clone git@github.com:softonic-development/portall-manifests.git
```
* dentro del repositorio de manifiestos
portall-manifests/helm/portall

```shell
cp -fr dev-roldyx dev-<nickname>
cp -fr prod-roldyx dev-<nickname>
```
**IMPORTANTE** Reemplazar tanto dentro de dev como de prod el nombre de host del ingress template, se reemplaza roldyx en 2 lugares

* Push a HEAD

---
### Parte 2 - Trabajando con Kargo
* Dentro de kargo-helm ir al directorio kargo y copiar el directorio example2 a example-<nickname>
```shell
cp -fr example-2 example-roldyx
```

* Seleccionar cluster kube-eu crear la applicacion
```shell
# ingresar al directorio nuevo/application y cambiar los nombres de los archivos Roldyx por el del nickname
# Tambien los editamos y modificamos roldyx por el nickname
kubectl apply -f .
# verificamos que el application este mirando el stage/dev/nickname

```

* Abrimos la url de Kargo
    * https://kargo.softonic.io

RMO86dA3MzboT3foF7mISPJ2oVrLqSSB <---esto se los va a pedir

* creamos un project
```
kubectl apply -f project.yaml
```
* vamos al namespace del projecto creado
```
kubens portall-example-nickname
```
* creamos la configuracion del proyecto
```
#kaf=kubectl apply -f
kaf projectconfig.yaml
```
* creamos nuestros warehouse
```
kaf warehouse-image.yaml
kaf warehouse-git.yaml
kaf promotiontask.yaml
```
* Editamos los stage y reemplazamos roldyx por nickname

```
kaf stage-dev.yaml
kaf stage-prod.yaml
```
