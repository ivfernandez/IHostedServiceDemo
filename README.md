# IHostedServiceDemo

## Proyecto en Net Core 3.1 creando 2 servicios que implementan la interfaz IHostedService

### 

Implementamos los 2 metodos: 
StartAsync (para cuando se levante el servidor)
StopAsync (cuando se frenea/apague/reinicio etc el servidor)

NOTA: el StopAsync podria no funcionar siempre... ya que si por algun motivo la aplicacion se detiene por ejemplo... quizas no pase por el StopAsync...

NOTA: es importante detener el sitio desde el IIS express, IIS comun o donde tengamos el sitio, para que el servicio no siga corriendo.

Usando un timer, podemos hacer que el metodos del servicio corran cada cierto tiempo que le indiquemos.

(Imagen con el ejemplo de un servicio que guarda txt)
(En este ejemplo, se guardara un txt en la carpeta wwwroot del proyecto)

NOTA: debemos agregar el/los servicios creados en la clase Startup.cs en el metodo ConfigureServices:
services.AddTransient<IHostedService, WriteToFileHostedService>();

Tambien implementamos IDisposable para liberar recursos del timer que vamos a usar.
