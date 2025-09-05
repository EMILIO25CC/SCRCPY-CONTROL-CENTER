# SCRCPY Control Center v2.0

![Vista previa](./presentacionadb.png)

## Descripción General

SCRCPY Control Center es una aplicación de escritorio desarrollada en JavaFX que ofrece una interfaz gráfica intuitiva para gestionar dispositivos Android mediante SCRCPY y ADB (Android Debug Bridge). La aplicación permite controlar remotamente dispositivos Android tanto por conexión USB como por WiFi de forma automatizada y sencilla. Además, el programa no almacena información una vez que la PC se apaga, garantizando mayor seguridad y privacidad.

### Tecnologías Utilizadas
- **JavaFX 21+** - Framework de interfaz de usuario moderna
- **FXML** - Diseño declarativo de interfaces
- **CSS** - Personalización y temas visuales
- **ADB (Android Debug Bridge) 36.0.0** - Comunicación con dispositivos Android
- **SCRCPY 3.3.1** - Transmisión y control de pantalla

### ¿Qué es SCRCPY?
Es una herramienta de código abierto que permite visualizar y controlar un dispositivo Android desde la computadora, con baja latencia y sin necesidad de acceso root. Soporta conexión USB y WiFi, ideal para presentaciones, grabación o pruebas de aplicaciones.

### ¿Qué es ADB?
Es una utilidad de línea de comandos que actúa como un puente de comunicación entre la PC y el dispositivo Android. Permite instalar aplicaciones, transferir archivos, ejecutar comandos del sistema y obtener información del dispositivo, siendo esencial para depuración y desarrollo.

## Información de Desarrollo

**Versión:** 2.0  
**Fecha de lanzamiento oficial:** 04/09/2025  
**Fases de prueba finalizadas:** 26/08/2025  
**Disponibilidad:** Windows (Portable e Instalador)  
**Idioma:** Español  
**Estado:** Nuevo - puede presentar fallos o incompatibilidades

## Temas Visuales

El programa incluye dos temas personalizables:

- **Tema Claro:** ![Tema claro](./modo_claro.png)
- **Tema Oscuro:** ![Tema oscuro](./modo_oscuro.png)

La configuración del tema se guarda automáticamente y se restaura al reiniciar el programa.

## Estructura de la Interfaz

### Barra Superior
- **Función Salir:** Notifica al usuario si hay transmisiones activas y solicita cerrarlas antes de salir
- **Función Ayuda:** Muestra manual de uso detallado con funcionamiento del sistema
- **Función Apariencia:** Permite alternar entre tema claro y oscuro, recordando la configuración
- **Función Reiniciar ADB:** Detiene y reinicia el servicio ADB para solucionar problemas de conectividad

### Barra de Estado
- **Dispositivos Detectados:** Contador dinámico de dispositivos Android conectados
- **Transmisiones Activas:** Indica la cantidad de transmisiones en tiempo real

### Panel Principal de Controles
- **Actualizar:** Escanea y actualiza la lista de dispositivos USB y WiFi
- **Conectar:** Inicia SCRCPY con el dispositivo seleccionado para control remoto
- **Modo WiFi:** Configura conexión inalámbrica TCP/IP en puerto 5555
- **Mostrar IDs:** Alterna la visibilidad de los identificadores de dispositivo
- **Cerrar Todo:** Cierra todas las transmisiones activas simultáneamente

### Tabla de Dispositivos
Muestra información detallada de cada dispositivo conectado:
- **Fabricante:** Nombre del fabricante del dispositivo
- **Modelo:** Nombre del modelo específico
- **N° Serie/IP:** Identificador único (enmascarado por seguridad)
- **Android:** Versión del sistema operativo Android
- **Batería:** Nivel de carga con indicadores de color según el estado
- **Conexión:** Tipo de conexión (USB o WiFi)
- **Estado:** CONECTADO / DESCONECTADO / ACTIVO

### Control de Audio
- **Sin Audio/Con Audio:** Controla la transmisión de audio del dispositivo hacia la PC
- **Requisitos:** Funciona solo en Android 10 o superior
- **Recomendación:** Mejor rendimiento por conexión USB que por WiFi

### Registro del Sistema
Panel de log en tiempo real que muestra:
- Configuraciones WiFi iniciadas
- Dispositivos USB conectados/desconectados
- Establecimiento de conexiones WiFi
- Cierre de múltiples dispositivos
- Procesos de escaneo completados
- Estado del audio y configuraciones

### Registro Expandido
La función expandir permite abrir una ventana adicional con herramientas avanzadas:
- Pantalla ampliada de logs
- Buscador integrado
- Detector de caracteres inexistentes
- Contador de palabras y números
- Navegación entre resultados de búsqueda

## Funcionalidades Clave

### Detección Automática
- Monitoreo continuo de dispositivos USB y WiFi
- Actualización automática de la tabla cuando se conectan o desconectan dispositivos
- Recuperación automática de dispositivos WiFi temporalmente desconectados

### Conexión WiFi Inteligente
- Configuración automática del modo TCP/IP en puerto 5555
- Una vez establecida la conexión WiFi, permite desconectar el cable USB
- Gestión de IPs dinámicas para reconexión automática

### Seguridad y Privacidad
- Los IDs de los dispositivos se enmascaran por defecto para proteger información sensible
- Control total del usuario sobre la visibilidad de información identificativa
- No almacena datos persistentes después del apagado de la PC

### Menú Contextual (Clic Derecho)
Para dispositivos WiFi, permite:

**Estado DESACTIVADO:**
- Eliminar dispositivo del programa si se perdió la señal
- Reconexión manual si el dispositivo está en la misma red

**Estado CONECTADO:**
- Eliminar dispositivo cuando ya no sea necesario

## Configuración de Dispositivos Android

### Activación del Modo Desarrollador
1. Ve a "Ajustes" o "Configuración" en tu dispositivo
2. Busca "Acerca del teléfono" o "Información del dispositivo"
3. Localiza "Número de compilación" o "Número de versión"
4. Toca repetidamente (7 veces) sobre "Número de compilación"
5. Aparecerá el mensaje: "Ahora eres un desarrollador"

### Activación de Depuración USB
1. Ingresa a "Opciones de desarrollador"
2. Localiza "Depuración USB" o "Depuración por USB"
3. Activa el interruptor
4. Confirma en la ventana emergente
5. Al conectar por primera vez, acepta la autorización de la PC

### Activación de Depuración Inalámbrica
**Disponible en Android 11 (API nivel 30) y superior**

1. En "Opciones de desarrollador", activa "Depuración inalámbrica"
2. Asegúrate de que dispositivo y PC estén en la misma red WiFi
3. Usa "Emparejar dispositivo con código QR" o código de 6 dígitos
4. Utiliza los datos mostrados para establecer la conexión

## Flujo de Trabajo

1. **Conexión inicial:** Conecta el dispositivo Android vía USB con depuración habilitada
2. **Detección:** La aplicación detecta automáticamente el dispositivo
3. **Configuración WiFi:** Usa 'MODO WIFI' para establecer conexión inalámbrica
4. **Activar audio:** Opcional - elige mantener audio en dispositivo o transmitir a PC
5. **Control remoto:** Selecciona dispositivo y usa 'CONECTAR' para iniciar SCRCPY
6. **Desconexión USB:** Una vez en WiFi, el cable USB puede desconectarse

## Función de Restauración de Servicio ADB

La función de Reinicio de ADB incluye:
- Restablecimiento completo del servicio ADB
- Desconexión automática de dispositivos WiFi configurados
- Contador de seguridad de 30 segundos antes de ejecutar
- Notificación si existen transmisiones activas
- Recomendación de reiniciar el programa después del proceso

## Beneficios del Sistema

- **Interfaz intuitiva:** No requiere conocimientos de línea de comandos
- **Gestión centralizada:** Control de múltiples dispositivos desde una aplicación
- **Conexión flexible:** Soporte completo para USB y WiFi
- **Monitoreo en tiempo real:** Estado actualizado constantemente
- **Recuperación automática:** Reintento de conexiones perdidas
- **Diseño profesional:** Interfaz moderna con temas personalizables

## Solución de Problemas

### Errores de Reconexión WiFi
Si tu dispositivo se desconecta del WiFi:
1. Revisa la conexión de red WiFi
2. Si persiste el problema, conecta nuevamente el cable USB
3. El botón 'MODO WIFI' se habilitará para nueva reconexión si es necesario

**Causas comunes de desconexión:**
- Reinicio del módem/router
- Reinicio del dispositivo móvil
- Cortes de energía eléctrica
- Cambios en la configuración de red

### Errores de Conexión USB
Si el dispositivo no es reconocido:
1. Verifica que el cable USB sea de datos (no solo carga)
2. Asegúrate que la depuración USB esté habilitada
3. Confirma la autorización en la pantalla del dispositivo
4. Si persiste, reinicia dispositivo y/o computadora

## Archivos Disponibles

### Versión Portable
Descarga directa sin necesidad de instalación:  
[Descargar Portable](https://github.com/EMILIO25CC/SCRCPY-CONTROL-CENTER/releases/download/v2.0/Portable_SCRCPY_Control_Center_v2.0.zip)

### Versión Instalador
Crea accesos directos y se integra al sistema:  
[Descargar Instalador](https://github.com/EMILIO25CC/SCRCPY-CONTROL-CENTER/releases/download/v2.0/Instalador_SCRCPY_Control_Center_v2.0.zip)

### Selección de Idioma en el Instalador
El software detecta el idioma seleccionado y muestra avisos informativos:
- **Español:** Nota: Este idioma solo aplica al instalador. El programa seguirá en su idioma original
- **Inglés:** Note: This language only applies to the installer. The program will remain in its original language

## Instrucciones de Uso

1. Elige la versión que prefieras: **Portable** o **Instalador**
2. Descarga el archivo correspondiente
3. **Para versión Portable:** Abre directamente el archivo .exe
4. **Para versión Instalador:** Ejecuta el .exe y sigue los pasos del instalador
5. Conecta tu dispositivo Android mediante USB o WiFi según preferencia
6. Disfruta del control completo desde la interfaz gráfica

## Nota sobre Windows SmartScreen

Al ejecutar por primera vez SCRCPY Control Center, es posible que Windows muestre una advertencia de seguridad:

![SmartScreen](/seguridad.png)

Esto ocurre porque el programa **no está firmado digitalmente** y es una versión nueva sin reputación en Microsoft. No significa que el archivo sea peligroso - la advertencia aparece porque es la primera vez que este archivo circula en internet.

El software ha sido probado exhaustivamente durante sus fases de desarrollo y no presentó problemas en los distintos entornos utilizados.

**Para continuar con la ejecución:**
1. Hacer clic en **Más información**
2. Seleccionar **Ejecutar de todas formas**

## Información del Desarrollador

**SCRCPY Control Center v2.0**  
Desarrollado por: Carlos Cabrera  
Rol: Estudiante de Informática

**Enlaces:**
- GitHub: https://github.com/EMILIO25CC
- LinkedIn: https://www.linkedin.com/in/carlos-emilio-cabrera-castañeda-1b8abb34a/
- YouTube: https://www.youtube.com/@DeSofCC

*Una solución ligera para el control de dispositivos Android*

## Licencia y Terceros

Este proyecto integra los binarios de **Scrcpy** y **ADB**, los cuales son software libre distribuidos bajo **Licencia Apache 2.0**.

**Repositorio oficial de Scrcpy:** [Scrcpy en GitHub](https://github.com/Genymobile/scrcpy)

Mi proyecto también se distribuye bajo **Licencia Apache 2.0**.  
Consulte la licencia oficial aquí: [Licencia Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)

## Contacto y Soporte

Para dudas, sugerencias o reportes de errores, puedes abrir un **issue** en este repositorio o contactarme directamente a través de los enlaces proporcionados en la sección del desarrollador.

---

**Nota importante:** Este es un programa relativamente nuevo y puede presentar fallos o incompatibilidades. El uso es bajo responsabilidad del usuario y está recomendado para redes locales únicamente.
