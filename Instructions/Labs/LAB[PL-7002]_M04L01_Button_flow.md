---
lab:
  title: "Laboratorio\_5: Flujo de botón"
  module: 'Module 4: Build flows to manage user information'
---

# Laboratorio de práctica 5: flujo de botón

En este laboratorio, creará un flujo de botón.

## Aprendizaje

- Creación de un flujo de botón instantáneo de Power Automate

## Pasos de alto nivel del laboratorio

- Crear un flujo de botón
- Uso de tokens de desencadenador
- Adición de entrada de usuario
- Prueba del flujo
  
## Requisitos previos

- Debe de haber completado la práctica **Laboratorio 2: Modelo de datos**

## Pasos detallados

## Ejercicio 1: Creación de un flujo de botón

### Tarea 1.1: Creación del desencadenador

1. Ve al portal de Power Automate `https://make.powerautomate.com`

1. Asegúrese de que está en el entorno **Dev One**.

1. Seleccione la pestaña **+ Crear** en el menú de la izquierda.

1. Seleccione **Flujo de nube instantáneo.**

1. Escriba `Create opportunity` en **Nombre de flujo**.

1. Seleccione **Desencadenar manualmente un flujo**.

1. Seleccione **Crear**.


### Tarea 1.2: Adición de entrada de usuario

1. Seleccione el paso **Desencadenar manualmente un flujo**.

1. Selecciona el nombre del paso **Desencadenar manualmente un flujo** y escribe `Button triggered`

1. Seleccione **Agregar una entrada**.

1. Selecciona **Texto**.

1. Escriba `Customer Name` en **Entrada**.

1. Escriba `Please enter the customer name` en **Escriba la entrada**.

1. Seleccione **Agregar una entrada**.

1. Seleccione **Texto**

1. Escriba `Comments` en **Entrada**.

1. Escriba `Any comments` en **Escriba la entrada**.

1. Seleccione **Agregar una entrada**.

1. Seleccione **Número**

1. Escribe `Potential Sale` en **Número**.

    ![Captura de pantalla de la entrada del usuario.](../media/user-input.png)


### Tarea 1.3: Adición de la acción Crear oportunidad

1. Seleccione el icono **+** en el paso del desencadenador y elija **Agregar una acción**.

1. Escriba `add row` en el cuadro de búsqueda.

1. Selecciona **Agregar una nueva fila** en **Microsoft Dataverse**.

1. Seleccione **Iniciar sesión**.

1. Use sus credenciales de inquilino.

1. Seleccione el nombre del paso **Agregar una nueva fila** y escriba `New opportunity`.

1. Selecciona **Oportunidades** para **Nombre de tabla**

1. Escribe `/` en el campo **Cliente** y selecciona **Insertar contenido dinámico** y, después, **Ver más**.

1. Seleccione **Nombre de cliente**.

1. Selecciona el campo **Nombre del propietario** y escribe `MOD Administrator`

1. Seleccione **Mostrar todo**.

1. Selecciona el campo **Asunto de la oportunidad** y escribe `New opportunity`

1. Escribe `/` en el campo **Importe** y selecciona **Insertar contenido dinámico**.

1. Seleccione **Venta potencial**.

1. Selecciona el campo **Notas**, el icono Contenido dinámico y **Ver más**.

1. Seleccione **Comentarios**.

1. Escribe `/` en el campo **Fecha de cierre estimada** y selecciona **Insertar expresión**.

1. Escriba la expresión `utcNow()` y seleccione **Agregar**.

    ![Captura de pantalla de la nueva acción de oportunidad.](../media/new-opportunity-action.png)

1. Seleccione **Guardar**.


## Ejercicio 2: Prueba del flujo de botón

### Tarea 2.1: Ejecución del flujo de botón

1. Seleccione **Probar**

1. Seleccione **Manualmente**.

1. Seleccione **Probar**.

    ![Captura de pantalla de la prueba del flujo de botón.](../media/user-input-test.png)

1. Escriba la siguiente información:

   1. Nombre del cliente=`Button test`
   1. Comentarios=`This is a test`
   1. Venta potencial=`9999`

1. Seleccione **Ejecutar flujo**.

1. Seleccione **Listo**.

1. En la parte superior izquierda de la barra de comandos, seleccione el botón **<-** Atrás.


### Tarea 2.2: Comprobación del registro de oportunidades creado

1. Vaya al portal de Power Apps Maker `https://make.powerapps.com`.

1. Asegúrese de que está en el entorno **Dev One**.

1. Seleccione **Tablas** en el panel de navegación izquierdo.

1. Seleccione **Oportunidad**.

