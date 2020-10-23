# IHostedServiceDemo

## Proyecto en Net Core 3.1 creando 2 servicios que implementan la interfaz IHostedService

### 

NOTA: es importante detener el sitio desde el IIS express, IIS comun o donde tengamos el sitio, para que el servicio no siga corriendo.

(Imagen con el ejemplo de un servicio que guarda txt)
(En este ejemplo, se guardara un txt en la carpeta wwwroot del proyecto)

NOTA: debemos agregar el/los servicios creados en la clase Startup.cs en el metodo ConfigureServices:
services.AddTransient<IHostedService, WriteToFileHostedService>();
