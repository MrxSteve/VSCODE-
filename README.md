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

## Paso 2: Descargar e instalar VS Code

### 2.1 Descargar Visual Studio Code:
- Ve a la página oficial de Visual Studio Code: [https://code.visualstudio.com/](https://code.visualstudio.com/).
- Haz clic en **Download for Windows** y descarga el instalador.
- Abre el instalador y sigue las instrucciones para instalar Visual Studio Code en tu computadora.

### 2.2 Instalar la extensión de C++ en Visual Studio Code:
- Abre **Visual Studio Code**.
- Haz clic en el ícono de **Extensiones** en la barra lateral izquierda (o presiona `Ctrl + Shift + X`).
- En el cuadro de búsqueda, escribe `C/C++`.
- Selecciona la extensión **C/C++** desarrollada por Microsoft y haz clic en **Instalar**.

## Paso 3: Configurar tareas de compilación y depuración

### 3.1 Crear un archivo de C++:
- Abre **Visual Studio Code**.
- Crea un nuevo archivo de C++ con el nombre `hola_mundo.cpp`.
- Agrega el siguiente código de ejemplo:

    ```cpp
    #include <iostream>
    using namespace std;

    int main() {
        cout << "Hola mundo" << endl;
        return 0;
    }

### 3.2 Configurar tareas de compilación en VS Code:
- Presiona `Ctrl + Shift + B` o ve a **Terminal > Configure Default Build Task**.
- Selecciona la opción **"g++ build active file"**.
- Esto creará automáticamente un archivo de configuración llamado `tasks.json` en la carpeta `.vscode` de tu proyecto.
- Si no se crea el archivo automáticamente, puedes crear manualmente la carpeta `.vscode` en el directorio de tu proyecto y dentro de esta, crear un archivo llamado `tasks.json` con el siguiente contenido:

    ```json
    {
        "version": "2.0.0",
        "tasks": [
            {
                "label": "build",
                "type": "shell",
                "command": "g++",
                "args": [
                    "-g",
                    "${file}",
                    "-o",
                    "${fileDirname}/${fileBasenameNoExtension}.exe"
                ],
                "group": {
                    "kind": "build",
                    "isDefault": true
                },
                "problemMatcher": ["$gcc"],
                "detail": "Tarea generada automáticamente por VS Code"
            }
        ]
    }

### 3.3 (Opcional) Configurar la depuración en VS Code:
- Si deseas depurar tu código, ve a **Run > Add Configuration**.
- Selecciona la opción **C++ (gdb)**.
- Esto generará un archivo `launch.json` que permitirá configurar puntos de interrupción y depurar el programa en Visual Studio Code.

## Paso 4: Compilar y ejecutar el programa

### 4.1 Compilar el programa:
- Guarda tu archivo `hola_mundo.cpp`.
- Presiona `Ctrl + Shift + B` para compilar el programa.
- Si la compilación es exitosa, se generará un archivo ejecutable `.exe` en el mismo directorio que tu archivo de código fuente.

### 4.2 Ejecutar el programa compilado:
- Abre el **terminal de Visual Studio Code** (o el **Símbolo del sistema** en Windows).
- Navega al directorio donde se generó el archivo `.exe` utilizando el comando `cd`.
- Ejecuta el programa escribiendo el siguiente comando:

```bash
./hola_mundo.exe

