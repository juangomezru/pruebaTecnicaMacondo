# Prueba Técnica Ingeniero Junior Cloud 

Este es un proyecto de ejemplo que utiliza Docker y Nginx para desplegar una aplicación de React en Google Cloud Run.

## Requisitos

- Docker
- Google Cloud SDK

## Instrucciones de Despliegue

1. Construye la imagen Docker con el siguiente comando:

```sh
docker build -t my-app .
```

2. Etiqueta la imagen Docker con el nombre del registro de GCR:

```sh
docker tag my-app gcr.io/techassmacondo-418123/my-app
```

3. Configura Docker para usar gcloud como ayudante de credenciales:

```sh
gcloud auth configure-docker
```

4. Sube la imagen Docker a GCR:

```sh
docker push gcr.io/techassmacondo-418123/my-app
```

5. Despliega la aplicación en Cloud Run:

```sh
gcloud run deploy my-app --image gcr.io/techassmacondo-418123/my-app --platform managed --region us-central1
```
