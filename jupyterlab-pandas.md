# Guía para instalar Jupyter Lab y Pandas en Windows

---

## 1. (Opcional) Crear y activar un entorno virtual

Se recomiendo usar un entorno virtual para aislar la instalación de Jupyter Lab y Pandas del Python global.

1. **Abrir el Símbolo del sistema (CMD)**  
   - Presiona la tecla **Windows**, escribe `cmd` y presiona **Enter**.

2. **Crear carpeta para tu entorno**  
   ```bat
   mkdir C:\Proyectos\entorno_jupyter_pandas
   cd C:\Proyectos\entorno_jupyter_pandas
   ```

3. **Crear el entorno virtual con `virtualenv`**  
   ```bat
   virtualenv venv_jupyter
   ```

4. **Activar el entorno virtual**  
   - En **CMD**:
     ```bat
     venv_jupyter\Scripts\activate
     ```

   Cuando el entorno esté activo, verás `(venv_jupyter)` al inicio del prompt:
   ```
   (venv_jupyter) C:\Proyectos\entorno_jupyter_pandas>
   ```

---

## 2. Instalar Jupyter Lab

Con el entorno virtual activo (o en tu Python global si decides no usar entorno virtual):

1. **Actualizar pip**  
   ```bat
   pip install --upgrade pip
   ```

2. **Instalar Jupyter Lab**  
   ```bat
   pip install jupyterlab
   ```

3. **Verificar la instalación**  
   ```bat
   jupyter-lab --version
   ```
   Deberías ver algo como:
   ```
   3.11.4
   ```

4. **Iniciar Jupyter Lab**  
   ```bat
   jupyter-lab
   ```
   Esto abrirá una pestaña en tu navegador con la interfaz de Jupyter Lab. Si no se abre automáticamente, copia la URL que muestra la consola (por ejemplo, `http://localhost:8888/lab?token=…`) y pégala en tu navegador.

---

## 3. Instalar Pandas

1. **Instalar Pandas con pip**  
   Con el entorno activo, ejecuta:
   ```bat
   pip install pandas
   ```

2. **Verificar la instalación de Pandas**  
   ```bat
   python -c "import pandas as pd; print(pd.__version__)"
   ```
   Esto imprimirá la versión instalada de Pandas, por ejemplo:
   ```
   2.0.1
   ```

---

## 4. Uso básico

1. **Crear un Notebook en Jupyter Lab**  
   - Dentro de Jupyter Lab, haz clic en “+” (o en menú *File › New › Notebook › Python 3*) para crear un nuevo notebook.

2. **Importar Pandas en un Notebook**  
   En la primera celda, escribe:
   ```python
   import pandas as pd
   # Crear un DataFrame de ejemplo
   df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
   print(df)
   ```
   Ejecuta la celda con **Shift+Enter** y verás el DataFrame impreso.

---

## 5. Solución de problemas comunes

1. **Error al ejecutar `jupyter-lab`**  
   - Asegúrate de haber activado el entorno virtual correcto:  
     ```bat
     venv_jupyter\Scripts\activate
     ```
   - Verifica que Jupyter Lab está en tu PATH:
     ```bat
     where jupyter-lab
     ```
   - Si el puerto 8888 está ocupado:
     ```bat
     jupyter-lab --port=8889
     ```

2. **Error al instalar Pandas**  
   - Asegúrate de tener pip actualizado:
     ```bat
     pip install --upgrade pip
     ```
   - Si hay conflicto de versiones o permisos:
     - Ejecuta CMD como Administrador.
     - Instala dentro de un entorno virtual activo.

3. **El navegador no se abre automáticamente**  
   - Copia la URL que aparece en la consola (p. ej., `http://localhost:8888/lab?token=…`) y pégala manualmente en tu navegador.
   - Si quieres forzar un navegador específico:
     ```bat
     jupyter-lab --browser="C:/Program Files/Google/Chrome/Application/chrome.exe %s"
     ```

---

* Información generada con fines académicos.
* Información generada con GenIA, supervisada

---
**René Elizalde - @reroes**
