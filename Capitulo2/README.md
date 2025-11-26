# Capítulo 2 — Using the Python Interpreter

## 2.1 Invocando el intérprete
El intérprete de Python suele instalarse en rutas como `/usr/local/bin/python3.14`.  
En Unix basta con tener esa ruta en el PATH para iniciarlo escribiendo:


En Windows se puede iniciar con `python3.14`, o usando `py` si está instalado el lanzador.

Para salir del intérprete:
- Control-D en Unix  
- Control-Z en Windows  
- O ejecutar `quit()`  

Si el sistema soporta GNU Readline, el intérprete permite edición interactiva, historial y autocompletado.  
Si al presionar **Control-P** suena un beep, la edición de línea está disponible.

El intérprete funciona de dos maneras:
- **Modo interactivo:** cuando se ejecuta desde un terminal.  
- **Modo script:** cuando se le pasa un archivo o recibe entrada estándar desde un archivo.

También se puede ejecutar código directamente con:
- `python -c "comando"` para ejecutar una instrucción.  
- `python -m módulo` para ejecutar un módulo como script.  
- `python -i script.py` para entrar al modo interactivo después de correr un script.

## 2.1.1 Paso de argumentos
Los argumentos dados al ejecutar un script se almacenan en `sys.argv`.  
Reglas importantes:
- `sys.argv[0]` es el nombre del script.  
- Si no hay script, `sys.argv[0]` es una cadena vacía.  
- Con `-c comando`, `sys.argv[0] = "-c"`.  
- Con `-m módulo`, `sys.argv[0]` es el nombre completo del módulo.  
- Los argumentos después de `-c` o `-m` no los consume Python; quedan en `sys.argv`.

## 2.1.2 Modo interactivo
Cuando Python lee desde un terminal entra en modo interactivo.  
Muestra dos tipos de prompt:
- `>>>` para la línea principal.  
- `...` para líneas de continuación.

Ejemplo de un bloque multilínea:

```python
the_world_is_flat = True
if the_world_is_flat:
    print("Be careful not to fall off!")
``` 