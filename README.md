# 🌐 Static Content Hosting en Azure - Luis Pinillos y Sara Cardona


Este documento explica cómo configurar una cuenta de almacenamiento en **Azure** para alojar contenido estático, utilizando el patrón de diseño **Static Content Hosting**.  

## 1️⃣ Creación del Resource Group  

El primer paso es crear un **Resource Group**, que servirá como contenedor para todos los recursos del proyecto.  

![Resource Group](https://github.com/user-attachments/assets/e321464e-8f70-4184-846a-1bc15b1a3c91)  

## 2️⃣ Creación de una Storage Account  

A continuación, creamos una **cuenta de almacenamiento** (*Storage Account*), que será el servicio donde se alojará el contenido estático.  

![Storage Account](https://github.com/user-attachments/assets/916218a9-bc3a-4d60-9c37-20ad20d679a3)  

## 3️⃣ Habilitar Static Website  

Dentro de la **Storage Account**, activamos la opción **Static website** (*Página Web Estática*).  

![Activar Static Website](https://github.com/user-attachments/assets/cd544159-6b6c-4c04-84aa-c31c98ca2ffd)  

Al activarlo, aparecerán dos campos:  

- **Index document name** → Archivo principal de la web (*Ejemplo: index.html*).  
- **Error document path** → Página de error en caso de rutas no encontradas (*Ejemplo: 404.html*).  

Los configuramos con los valores adecuados:  

![Configuración Static Website](https://github.com/user-attachments/assets/be286772-be4e-4a6a-9279-287a5878e4b8)  

Al guardar, Azure generará una **URL pública** donde se alojará el contenido de la página estática.  

![URL Generada](https://github.com/user-attachments/assets/92094f19-6e7c-442b-8494-7e91f915a6a6)  

## 4️⃣ Subir Contenido a $web  

El contenido de la web debe almacenarse en un **contenedor especial llamado `$web`** dentro de la **Storage Account**.  

Para ello, navegamos a la sección de **Containers** y accedemos a `$web`:  

![Container $web](https://github.com/user-attachments/assets/b1557515-89bf-49c8-99c5-3573a08a9b46)  

Aquí subimos todos los archivos estáticos (*HTML, CSS, JS, imágenes, videos, etc.*):  

![Subir archivos](https://github.com/user-attachments/assets/2bc508f7-ad13-447d-9b6d-42883ab1857d)  

---

## 📄 Ejemplo de Código  

Este es un ejemplo de una página web estática alojada en Azure:  

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Página Estática</title>
    <link rel="stylesheet" href="https://sch123.z13.web.core.windows.net/css/style.css">
</head>
<body>
    <div class="container">
        <h1>Bienvenido a mi sitio</h1>
        
        <img class="logo" src="https://sch123.z13.web.core.windows.net/images/liberty_status.jpg" alt="Logo">
        
        <video class="video" controls>
            <source src="https://sch123.z13.web.core.windows.net/videos/subaru.mp4" type="video/mp4">
            Tu navegador no soporta videos.
        </video>

        <a class="button" href="https://sch123.z13.web.core.windows.net/docs/test.pdf" download>📄 Descargar Manual</a>
    </div>
</body>
</html>
```  

El resultado se verá así en el navegador:  

![Ejemplo desplegado](https://github.com/user-attachments/assets/1f5f0e0e-42af-46b8-b90f-c84aee0b7eae)  

---

## 📌 Recursos Adicionales  

- 📖 [Documentación Oficial de Azure - Static Content Hosting](https://learn.microsoft.com/en-us/azure/architecture/patterns/static-content-hosting)  
- 🎥 [Video explicativo en YouTube](https://youtu.be/gYpNC_tdbQQ?si=Oj5Jq-cSAuuMCXsw)
