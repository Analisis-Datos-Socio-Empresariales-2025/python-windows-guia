# python-windows-guia

# Guía para instalar Python y usar `virtualenv` en Windows

---

## 1. Instalación de Python en Windows

### 1.1 Descargar Python

1. **Ir a la página oficial**  
   Abre tu navegador y visita:  
   [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)

   ![image](https://github.com/user-attachments/assets/2a0fe2f8-111e-48cb-aba9-f05a628b97e4)

   ![image](https://github.com/user-attachments/assets/850fe5f7-835e-49ae-bf76-8eff0f82d3c3)



3. **Seleccionar la versión de Python**  
   - Haz clic en “Download Python 3.x.x” (la versión más reciente).  
   - En la sección “Windows Installer”, elige la opción correspondiente a tu arquitectura:
     - **Windows 64-bit** (la mayoría de equipos modernos).  
     - **Windows 32-bit** (si tu sistema es de 32 bits).

4. **Descargar el instalador**  
   Descarga el archivo `.exe` sugerido (por ejemplo, `python-3.12.0-amd64.exe` para 64 bits).
   ![image](https://github.com/user-attachments/assets/b5455744-2d3b-4c24-a34a-c1d3192b7f66)


---

### 1.2 Instalar Python

1. **Ejecutar el instalador**  
   Haz doble clic en el `.exe` descargado para iniciar la instalación.
   

3. **Marcar “Add Python to PATH”**  
   - **MUY IMPORTANTE:** Antes de hacer clic en “Install Now”, marca la casilla **“Add Python 3.x to PATH”**.  
   - Esto permitirá invocar `python` y `pip` desde cualquier terminal sin rutas adicionales.
  
   ![image](https://github.com/user-attachments/assets/fa76d537-952e-4515-91a5-e95d467fced8)


4. **Instalar Python**  
   Haz clic en **“Install Now”** y espera a que finalice el proceso.

5. **Cerrar el instalador**  
   Cuando veas “Setup was successful”, haz clic en **“Close”**.

---

### 1.3 Verificar la instalación

1. **Abrir el Símbolo del sistema (CMD)**  
   - Presiona la tecla **Windows**, escribe `cmd` y presiona **Enter**.

![image](https://github.com/user-attachments/assets/7646bf31-c34a-4023-80cb-b996b133637a)


2. **Comprobar la versión de Python**  
   ```bat
   python --version
   ```
   Deberías ver algo como:
   ```
   Python 3.11.0
   ```

3. **Comprobar la versión de pip**  
   ```bat
   pip --version
   ```
   Ejemplo de salida:
   ```
   pip 23.x.x from C:\Users\<Usuario>\AppData\Local\Programs\Python\Python3x\lib\site-packages\pip (python 3.x)
   ```
   ![image](https://github.com/user-attachments/assets/41cb60eb-1860-470f-87cb-8802b1e5325a)


---

## 2. Instalación y uso de `virtualenv` en Windows

`virtualenv` permite crear entornos virtuales aislados para cada proyecto de Python, evitando conflictos de versiones de paquetes.

### 2.1 Instalar `virtualenv`

1. **Instalar con pip**  
   Con Python ya instalado, abre CMD y ejecuta:
   ```bat
   pip install virtualenv
   ```

2. **Verificar la instalación**  
   ```bat
   virtualenv --version
   ```
   Deberías obtener una línea con la versión, por ejemplo:
   ```
   20.0.35
   ```

---

### 2.2 Crear un entorno virtual

1. **Crear carpeta para el proyecto**  
   ```bat
   mkdir C:\Proyectos\MiProyecto
   cd C:\Proyectos\MiProyecto
   ```

2. **Crear el entorno virtual**  
   ```bat
   virtualenv venv
   ```
   Esto crea la carpeta `C:\Proyectos\MiProyecto\venv\` con su propia copia de Python.

---

### 2.3 Activar el entorno virtual

1. **En CMD**  
   ```bat
   venv\Scripts\activate
   ```
   - El prompt cambiará y mostrará `(venv)` al inicio:
     ```
     (venv) C:\Proyectos\MiProyecto>
     ```

---

### 2.4 Instalar paquetes dentro del entorno virtual

1. **Instalar un paquete (ej. `requests`)**  
   Con el entorno activado:
   ```bat
   pip install requests
   ```
   El paquete se instalará solo en `venv\Lib\site-packages`.

2. **Verificar paquetes instalados**  
   ```bat
   pip list
   ```
   Deberías ver algo como:
   ```
   Package    Version
   ---------- -------
   requests   2.26.0
   ```

---

### 2.5 Desactivar el entorno virtual

1. **Salir del entorno**  
   ```bat
   deactivate
   ```
   El prompt volverá a su forma normal (sin `(venv)`), y `python`/`pip` apuntarán al Python global.

---

## 3. Resumen de comandos importantes

| Acción                                    | Comando                                                         |
|-------------------------------------------|-----------------------------------------------------------------|
| Verificar instalación de Python           | `python --version`                                              |
| Verificar instalación de pip              | `pip --version`                                                 |
| Instalar `virtualenv`                     | `pip install virtualenv`                                        |
| Crear un entorno virtual                  | `virtualenv venv`                                               |
| Activar el entorno (CMD)                  | `venv\Scripts\activate`                                         |
| Instalar paquetes en el entorno           | `pip install <paquete>`                                         |
| Verificar paquetes instalados             | `pip list`                                                      |
| Desactivar el entorno virtual             | `deactivate`                                                    |

---

## 4. Solución de problemas comunes

1. **“'python' no se reconoce como un comando”**  
   - Verifica que marcaste “Add Python to PATH” durante la instalación.  
   - Si no lo hiciste, vuelve a ejecutar el instalador de Python y marca esa casilla.

2. **“'pip' no se reconoce como un comando”**  
   - Asegúrate de haber agregado Python a PATH.  
   - Alternativamente, prueba:
     ```bat
     python -m pip --version
     ```
     Si funciona, usa `python -m pip install <paquete>`.

3. **Permisos insuficientes**  
   - Si al instalar paquetes en el Python global obtienes “Permission denied”, abre CMD como Administrador o instala los paquetes dentro de un entorno virtual.

4. **Conflictos de versiones**  
   - Si trabajas con varios proyectos que requieren distintas versiones de un mismo paquete, usa entornos virtuales separados para cada uno y evita instalar paquetes globalmente.

---

* Información generada con fines académicos.
* Información generada con GenIA, supervisada
