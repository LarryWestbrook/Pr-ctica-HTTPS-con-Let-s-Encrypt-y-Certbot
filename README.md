# Práctica HTTPS con Let's Encrypt y Certbot

En esta práctica tendremos que realizar la instalación de la pila LAMP y la configuración de un certificado SSL/TLS con Let’s Encrypt y Certbot en el servidor web Apache, en una instancia EC2 de Amazon Web Services (AWS) con la última versión de Ubuntu Server.

## 1.1 Conceptos básicos
- 1.1.1 ¿Qué es HTTPS?
HTTPS (Hyptertext Transfer Protocol Secure) o protocolo seguro de transferencia de hipertexto, es un protocolo de la capa de aplicación basado en el protocolo HTTP, destinado a la transferencia segura de datos de hipertexto. (Fuente: Wikipedia)

Para poder habilitar el protocolo HTTPS en un sitio web es necesario obtener un certificado de seguridad. Este certificado tiene que ser emitido por una autoridad de certificación (AC). En esta práctica vamos a obtener un certificado para un dominio de la Autoridad de Certificación Let’s Encrypt.

- 1.1.2 ¿Qué es Let’s Encrypt?
Let’s Encrypt​ es una autoridad de certificación que se puso en marcha el 12 de abril de 2016 y que proporciona certificados X.509 gratuitos para el cifrado de seguridad de nivel de transporte (TLS) a través de un proceso automatizado diseñado para eliminar el complejo proceso actual de creación manual, la validación, firma, instalación y renovación de los certificados de sitios web seguros. (Fuente: Wikipedia)

- 1.1.3 Cómo funciona Let’s Encrypt
Se recomienda la lectura de la sección Cómo Funciona Let’s Encrypt de la documentación oficial.

- 1.1.4 ¿Qué es Certbot?
Para poder obtener un certificado de Let’s Encrypt para un dominio de un sitio web es necesario demostrar que se tiene control sobre ese dominio. Para realizar esta tarea es necesario utilizar un cliente del protocolo ACME (Automated Certificate Management Environment). El cliente ACME recomendado para esta tarea es Certbot porque es fácil de usar, tiene soporte para muchos sistemas operativos y dispone de una excelente documentación.

## 1.2 Tareas a realizar
A continuación se describen muy brevemente algunas de las tareas que tendrá que realizar.

- 1.2.1 Paso 1
Crear una instancia EC2 en Amazon Web Services (AWS).

Cuando esté creando la instancia deberá configurar los puertos que estarán abiertos para poder conectarnos por SSH y para poder acceder por HTTP/HTTPS.

SSH (22/TCP)
HTTP (80/TCP)
HTTPS (443/TCP)

- 1.2.2 Paso 2
Obtener la dirección IP pública de su instancia EC2 en AWS.

- 1.2.3 Paso 3
Realizar la instalación y configuración de un sitio web. Para esta tarea puede hacer uso de los scripts que ha realizado en las prácticas anteriores.

- 1.2.4 Paso 4
Registrar un nombre de dominio en algún proveedor de nombres de dominio gratuito. Por ejemplo, puede hacer uso de Freenom o No-IP.

- 1.2.5 Paso 5
Configurar los registros DNS del proveedor de nombres de dominio para que el nombre de dominio de ha registrado pueda resolver hacia la dirección IP pública de su instancia EC2 de AWS.

Si utiliza el proveedor de nombres de dominio Freenom tendrá que acceder desde el panel de control, a la sección de sus dominios contratados y una vez allí seleccionar Manage Freenom DNS.

Tendrá que añadir dos registros DNS de tipo A con la dirección IP pública de su instancia EC2 de AWS. Un registro estará en blanco para que pueda resolver el nombre de dominio sin las www y el otro registro estará con las www.

Ejemplo: En la siguiente imagen se muestra cómo sería la configuración de los registros DNS para resolver hacia la dirección IP 54.236.57.173.
