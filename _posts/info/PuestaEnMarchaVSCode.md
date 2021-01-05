Estas instrucciones están hechas para usar Visual Studio Code como IDE de Python en Windows 10. <br>
Se puede descargar VSCode desde su [web](https://code.visualstudio.com/download).

## Repositorio en VSCode

**En VSCode**

1. Instalar la extensión "GitLab Workflow".
2. Clonar el repositorio.

        Cmd + Shift + P
        "Git: Clone"
        Enter
        "https://gitlab001.iit.comillas.edu/pdeotaola/Ejemplo_Optimizacion_Python-Pyomo"
        Enter
    	--> Elegir la carpeta de destino del repositorio
        
**En GitLab**

3. Ir a "Settings", "Access Tokens".
4. Escribir un nombre para el token y marcar las casillas "api" y "read_user" y crear el token con "Create personal access token".
5. Copiar el token para dárselo después a VSCode.

**En VSCode**

6. Darle le token de GitLab a VSCode.

        Cmd + Shift + P
        "GitLab: Set GitLab Personal Access Token"
        Enter
        "https://gitlab001.iit.comillas.edu"
        Enter
        --> pegar el token
        Enter
        
7. En la extensión de GitLab darle al engranaje y a "Configure extension Settings".
8. En "Gitlab: Instance Url" pegar "https://gitlab001.iit.comillas.edu".

## Puesta en marcha del proyecto en VSCode

1. Cambiar la terminal por defecto (solo va a funcionar bien la consola normal del cmd, la de powershell va a usar la instalación de python del sistema y no la del entorno virtual).

		Ctrl + Shift + P
		"Terminal: Select Default Shell"
		Enter
		--> seleccionar "Command Prompt"

2. Crear una nueva terminar que use el cmd.

		Ctrl + Shift + Ñ

3. Crear entorno virtual para el proyecto y en la notificación que dice que si quieres usar ese interprete de python darle a si.

		python -m venv .venv

4. Si no salió una notificación para cambiar el intérprete (o la has cerrado).

		Ctrl + Shift + P
		"Python: Select Interpreter"
		Enter
		--> seleccionar el del entorno virtual recién creado

5. Entrar en el entorno virtual para que el python que se use sea ese y no el del sistema.

		.\.venv\Scripts\activate

6. Actualizar el pip.

		pip install --upgrade pip

7. Instalar todos los paquetes que dice el fichero de requisitos

		pip install -r requirements.txt
		


**Extras** 
1. Para poder ejecutar el código por bloques hay que instalar jupyter. <br>
	El entorno virtual crecerá de 151mb a 250mb, peor es muy útil.

		pip install jupyter

2. Generar un fichero de requisitos que tenga la info de todos los paquetes instalados.

		pip freeze > requirements.txt

	Freeze muestra los paquetes instalados en orden alfabético en vez de en orden de instalación. Es recomendable usar freeze solo para comprobar la versión instalada, pero mantener el fichero *requirements.txt* de manera manual por orden de instalación, para evitar futuros errores de conflicto de dependencias.

		pip freeze

3. En caso de querer entrar en python desde el cmd escribir.

		python

4. Para salir de python.

		exit()

5. Si se quisiera salir del entono virtual.

		deactivate

