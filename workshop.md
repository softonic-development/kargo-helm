# Kargo WorkShop

* Clonar kargo-helm, portall, portall-manifests
```shell
git clone git@github.com:softonic-development/kargo-helm.git
git clone git@github.com:softonic-development/portall.git
git clone git@github.com:softonic-development/portall-manifests-<nickname>.git
```

* Dentro de kargo-helm ir al directorio kargo y copiar el directorio example2 a example-<nickname>
```shell
cp -fr example-2 example-roldyx
```

* Seleccionar cluster kube-eu crear la applicacion
```shell
# reemplazar los valores de Roldyx por el del nickname
kubectl apply -f application.yaml
# verificamos que el application este funcionando

```

* Abrimos la url de Kargo
    * https://kargo.softonic.io

* creamos un project
kubectl apply -f project.yaml

* vamos al namespace del projecto creado
kubens portall-example-roldyx

* creamos la configuracion del proyecto
kaf projectconfig.yaml

* creamos nuestro warehouse
kaf warehouse-image.yaml
