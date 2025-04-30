
# 🚀 Guía completa para principiantes de Git, GitHub y exploración de archivos en Git Bash

---

## 💻 1. Instalación de Git en Windows

1. **Descarga**  
   - Visita [https://git-scm.com/download/win](https://git-scm.com/download/win)  
   - Descarga el instalador (32 o 64 bits) según tu sistema.

2. **Proceso de instalación**  
   - Ejecuta el archivo `.exe` descargado.  
   - En **Select Components**, mantén las opciones por defecto (Git Bash, Git GUI).  
   - En **Adjusting your PATH**, selecciona **Git from the command line and also from 3rd-party software**.  
   - En **SSH executable**, elige **Use bundled OpenSSH**.  
   - En **HTTPS transport backend**, selecciona **Use the OpenSSL library**.  
   - En **Configuring the line ending conversions**, marca **Checkout Windows-style, commit Unix-style line endings**.  
   - Acepta el resto de opciones predeterminadas y finaliza la instalación.

3. **Verificación**  
   ```bash
   git --version
   ```  
   Deberías ver algo como `git version 2.x.x`.

---

## ⚙️ 2. Configuración inicial y editor por defecto

1. **Definir identidad de usuario**  
   ```bash
   git config --global user.name "Tu Nombre"
   git config --global user.email "tu@correo.com"
   ```

2. **Elegir editor por defecto**  
   ```bash
   git config --global core.editor "code --wait"
   ```
   
   Sustituye `code --wait` por el comando de tu editor si usas otro.
   (`code --wait` es para Visual Studio Code).

4. **Crear alias útiles**  
   ```bash
   git config --global alias.st status
   git config --global alias.co checkout
   git config --global alias.ci commit
   git config --global alias.br branch
   ```

5. **Comprobar configuración**  
   ```bash
   git config --list
   ```

---

## 📁 3. Exploración de archivos en Git Bash

- **Listar archivos**  
  ```bash
  ls
  ```
  Lista simple de archivos.
   
   ```bash
  ls -la
  ```
  Lista de archivos detallada, con directorios ocultos y propiedades. 
- **Navegar entre carpetas**  
  ```bash
  cd ruta/a/carpeta
  ```
  Ir a la ruta de una carpeta.
  ```bash
  cd ..
  ```
  Retrocede un nivel en el directorio. 
  ```bash
  cd ~
  ```
  Ir al directorio raíz. 
- **Mostrar ruta actual**  
  ```bash
  pwd
  ```
- **Crear y eliminar**  
  ```bash
  mkdir proyecto
  touch archivo.txt
  ```
  Crear un nuevo directorio `mkdir` o archivo `touch`. 
  ```bash
  rm archivo.txt
  rm -r carpeta
  ```
  Eliminar un archivo `rm` o carpeta con su contenido `rm -r`.
- **Copiar y mover**  
  ```bash
  cp origen destino
  mv origen destino
  ```
- **Visualizar contenido**  
   ```bash
   cat archivo.txt
   ```
   Muestra el contenido completo del archivo en terminal.

   ```bash
   less archivo.txt
   ```
   Visualizador interactivo para navegar por el archivo.

   ```bash
   head -n 10 archivo.txt
   ```
   Muestra únicamente las primeras 10 líneas del archivo.

   ```bash
   tail -n 10 archivo.txt
   ```
   Muestra únicamente las últimas 10 líneas del archivo.

---

## 🔄 4. Flujo de trabajo básico de Git (sólo rama **main**)

1. **Inicializar repositorio**  
   ```bash
   git init
   ```

2. **Ver estado del repositorio**  
   ```bash
   git status
   ```

3. **Añadir cambios al área de staging**  
   ```bash
   git add archivo1 archivo2
   git add .
   ```

4. **Registrar un commit**  
   ```bash
   git commit -m "Mensaje breve y descriptivo"
   ```

5. **Consultar el historial de commits**  
   ```bash
   git log 
   ```

6. **Modificar o deshacer commits anteriores**
   ```bash
   git reset --soft HEAD~1
   ```
   Elimina el último commit sin deshacer los cambios en el documento.
   
   ```bash
   git reset --hard HEAD~1
   ```
   Elimina el último commit y los cambios en el documento.
   
   ```bash
   git revert <sha-del-commit>
    ```
   Deshacer los cambios introducidos por un commit específico, creando un nuevo commit que invierte esos cambios.
   
   ```bash
   git commit --amend --author="Nuevo Nombre <nuevo@correo.com>"
    ```
   Modifica los datos del autor del commit, en este caso, el nombre y el correo. 
   

---

## ☁️ 5. Crear un repositorio local y subirlo a GitHub

1. **Prepara tu proyecto**  
   ```bash
   mkdir mi-proyecto
   cd mi-proyecto
   ```

2. **Inicializa el repositorio**  
   ```bash
   git init
   ```

3. **Primer commit**  
   ```bash
   git add .
   git commit -m "Primer commit: estructura inicial"
   ```

4. **Crear el repositorio en GitHub**  
   - En GitHub haz clic en **New repository**.  
   - Asigna un nombre y no selecciones README ni .gitignore.

5. **Vincular el repositorio remoto**  
   ```bash
   git remote add origin https://github.com/usuario/mi-proyecto.git
   git remote -v
   ```

6. **Enviar los cambios y establecer upstream**  
   ```bash
   git push -u origin main
   ```
   Esto es completamente necesario en el primer push. 

7. **Sincronización habitual**  
   ```bash
   git push
   ```
   Envía los commits al repositorio. 
   ```bash
   git pull
     ```
   Extrae los cambios del repositorio online y los superpone al directorio local.
   ```bash
   git fetch
   ```
   Muestra los cambios hecho en el repositorio sin guardar nada, es sólo una revisión. 

---

## 📥 6. Clonar un repositorio existente y trabajar sobre él

1. **Obtener la URL del repositorio**  
   Copia la URL HTTPS o SSH desde GitHub.

2. **Clonar el repositorio**  
   ```bash
   git clone https://github.com/usuario/repositorio.git
   cd repositorio
   ```

3. **Verificar la rama principal**  
   ```bash
   git branch
   ```

4. **Realizar cambios y commits**  
   ```bash
   git add .
   git commit -m "Descripción de los cambios"
   ```

5. **Enviar cambios al remoto**  
   ```bash
   git push
   ```

6. **Sincronizar con el remoto**  
   ```bash
   git pull
   ```

---

## ✅ 7. Buenas prácticas y recomendaciones

   - Commits atómicos.  
   - Mensajes claros y en imperativo.  
   - Uso de `.gitignore`.  
   - Protección de la rama `main`.  
   - Sincronización frecuente con `pull --rebase`.

---
## 💡8. Utilidades Adicionales

   - [Documentación de Git](https://git-scm.com/doc)
   - [Vídeo Guía Recomendado](https://www.youtube.com/watch?v=mBYSUUnMt9M)

---
