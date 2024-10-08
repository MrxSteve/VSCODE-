# Configuración de C++ en Visual Studio Code con MinGW en Windows

Este documento te guiará a través de los pasos completos para configurar C++ en Visual Studio Code utilizando MinGW como compilador en Windows.

## Paso 1: Instalar MinGW (Minimalist GNU for Windows)

MinGW incluye `g++`, el compilador necesario para C++ en Windows.

### 1.1 Descargar MinGW:
1. Visita la página oficial de MinGW: [https://sourceforge.net/projects/mingw/](https://sourceforge.net/projects/mingw/).
2. Haz clic en el botón **Download** y espera que se descargue el instalador (`mingw-get-setup.exe`).

### 1.2 Instalar MinGW:
1. Abre el archivo descargado `mingw-get-setup.exe`.
2. Sigue las instrucciones del instalador.
3. En la ventana **Select Components**, asegúrate de seleccionar el paquete `mingw32-gcc-g++`, que incluye el compilador C++.
4. Haz clic en **Apply Changes** para instalar los componentes seleccionados.
5. Espera a que se complete la instalación.

### 1.3 Agregar MinGW al PATH del sistema:
1. Abre el **Panel de Control**.
2. Ve a **Sistema > Configuración avanzada del sistema**.
3. En la ventana de **Propiedades del sistema**, selecciona **Variables de entorno**.
4. En **Variables del sistema**, busca la variable llamada `Path` y haz clic en **Editar**.
5. Haz clic en **Nuevo** y añade la ruta donde instalaste MinGW (por defecto suele ser `C:\MinGW\bin`).
6. Haz clic en **Aceptar** para guardar los cambios.
7. Reinicia tu computadora para asegurarte de que los cambios surtan efecto.

### 1.4 Verificar la instalación de MinGW:
1. Abre el **Símbolo del sistema** (CMD).
2. Escribe el siguiente comando para verificar si `g++` está correctamente instalado:
   ```bash
   g++ --version
