# BACKEND

## PASOS PARA REALIZAR DESPLIEGUE  DEL BACKEND EN GOOGLE CLOUD RUN

La guía a seguir se encuentra en el link:<br>

<https://cloud.google.com/run/docs/quickstarts/build-and-deploy/deploy-java-service>

1. inicializar el Google Cloud CLI:<br>

>  *gcloud init*


2. Luego configurar el ID del Proyecto en el que se desplegará la aplicación:<br>

>  *gcloud config set project PROJECT_ID*


3. Luego se habilitan Cloud Run Admin API y Cloud Build API:<br>

>  *gcloud services enable run.googleapis.com cloudbuild.googleapis.com*

4. Luego se crean los roles para permitir a Cloud Build crear y desplegar aplicaciones desde el código fuente:<br>

>  *gcloud projects add-iam-policy-binding PROJECT_ID \*
>      *--member=serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com \*
>      *--role=roles/cloudbuild.builds.builder*

5. Finalmente para desplegar la aplicación spring boot, <br>
nos ubicamos en el directorio del código fuente y ejecutamos el comando:<br>

>  *gcloud run deploy --source .*

   **Nota: La aplicación spring boot, debe tener configurado el puerto 8080 para el servidor integrado**

   ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/albuquerque.jpg?auto=format&fit=clip&q=40&w=1080)


# FRONTEND

## PASOS PARA REALIZAR DESPLIEGUE DEL FRONTEND EN AMAZON AWS S3

La guía para desplegar el frontend se encuentra en el link:<br>

<https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html>

1. Ubicados en la carpeta raiz del proyecto, se exporta el frontend usando el comando:<br>

	*ng build --configuration production*

2. Luego se crea el bucket en AWS S3, desactivando casilla para bloquear todo el acceso público.<br>

   ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/albuquerque.jpg?auto=format&fit=clip&q=40&w=1080)

3. Luego se suben los archivos ubicados en la carpeta “build” dentro del directorio del proyecto.<br>


4. Se habilita el alojamiento de sitio web estático de AWS S3 en la pestaña propiedades del bucket:<br>

   ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/albuquerque.jpg?auto=format&fit=clip&q=40&w=1080)

5. Finalmente, se crea una política tipo bucket para permitir el acceso público de solo lectura:<br>

   ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/albuquerque.jpg?auto=format&fit=clip&q=40&w=1080)





