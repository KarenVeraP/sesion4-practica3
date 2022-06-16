# Práctica 3. Conectar dos Máquinas Virtuales

## Crear las máquinas virtuales
Comenzamos buscando las máquinas vituales en [Azure Portal](https://portal.azure.com/#home).

![p3p1](imagenes\p3p1.png)

A continuación crearemos una dando click en "Crear" y seleccionando la primera opción (Máquina virtual de Azure).

![p3p2](imagenes\p3p2.png)

Para crear la máquina virtual introducimos los datos solicitados:
- Suscripción: Azure for Students
- Grupo de recursos: sesion4
- Nombre de la máquina vitual: sesion4-vm1
- Región: en este caso hemos establecido la región de Australia East ya que es la que nos permite establecer diferentes tamaños.
- Imagen: Windows 10 Pro
- Tamaño: Standard_DS1_v2 -1 vcpu

![p3p3](imagenes\p3p3.png)

- Nombre de usuario
- Contraseña
- Confirmación de licencia

Los demás parámetros los dejaremos como Azure los establece.

Damos click en Revisar y crear para luego crear la máquina virtual. El proceso deberá depetirse para una segunda máquina virtual.

![p3p4](imagenes\p3p4.png)

--------------------------------

## Inicio de la primer máquina virtual
En Azure seleccionamos una de las máquinas virtuales que hemos creado, damos click en "Conectar" y seleccionamos RDP, y descargamos el archivo RDP.

![p3p5](imagenes\p3p5.png)

Abrimos el archivo que se ha descargado.

![p3p7](imagenes\p3p7.png)

Ingresamos con el nombre de usuario y contraseña que introducimos durante la creación de la máuina virtual.

![p3p8](imagenes\p3p8.png)

La máquina virtual se iniciará.

![p3p9](imagenes\p3p9.png)

Aceptamos la configuración de Windows.

![p3p10](imagenes\p3p10.png)

La primer máquina virtual se ha iniciado :D

![p3p11](imagenes\p3p11.png)

-------------------------------
## Conexión de la segunda máuina virtual
Abrimos como administrador Windows PowerShell.

![p3p12](imagenes\p3p12.png)

Ejecutamos el comando: 
*New-NetFirewallRule -DisplayName "Allow ICPMv4-In" -Protocol ICPMv4*

![p3p13](imagenes\p3p13.png)

Ahora usaremos la IP de la segunda máquina virtual, la cual podemos ver en los Dispositivos conectados de la red virtual de una de las máquinas virtuales, en este caso en 10.0.0.5. Usaremos el comando:
*mstsc /v:10.0.0.5*

![p3p14](imagenes\p3p14.png)

A continuación se nos pedirá el usuario y la contraseña de la segunda máquina virtual.

![p3p15](imagenes\p3p15.png)

Se iniciará la segunda máquina virtual.

![p3p16](imagenes\p3p16.png)

Aceptamos de nuevo la configuración de Windows y nuestra segunda máquina virtual habrá sido creada :D

![p3p17](imagenes\p3p17.png)

----------------------------------------
## Extra
### Apagado de las máquinas virtuales
Para que las máquinas virtuales no consuman nuestro crédito las apagaremos o las eliminaremos.
Para apagar la máquina virtual sólo se necesita seleccionarla y dar click en "Detener"

![p3p18](imagenes\p3p18.png)

### Recursos creados
Para cada máquina virtual:
- Máquina virtual.
- Dirección IP pública.
- Grupo de seguridad de red
- Interfaz de red normal
- Disco

Red virtual única para ambas VM. 

![p3p19](imagenes\p3p19.png)