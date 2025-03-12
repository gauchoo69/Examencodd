## Pasos examen 2º EVALUACIÓN

# **Documentación del proceso de desarrollo y fusión de ramas**

## **1. Creación de la rama readme**
**Para documentar los pasos seguidos en el desarrollo, se crea una rama especial:

***
git checkout -b readme**

Se añade un archivo `Readme.md` donde se registran los comandos y justificaciones de cada decisión.

## **2. Creación y fusión de ramas de desarrollo**
El proyecto se divide en varias ramas:

- datos: Contiene la clase de conexión a la base de datos.
- interface: Contiene la parte gráfica de la aplicación.
- main: Solo acepta commits etiquetados para cada release.

Cada una de estas ramas se desarrolla y se fusiona a `main` siguiendo estos pasos:


- git checkout main
- git merge datos
- git merge interface

Si hay conflictos, se resuelven desde la interfaz de IntelliJ IDEA o manualmente en los archivos afectados.

## **3. Revisión del código antes de la fusión final**
Antes de finalizar la fusión, se revisa el código de la rama interface y se detecta que el último commit contiene código que no debe incluirse. Para evitarlo:


git revert <ID_DEL_COMMIT>

o, si aún no se ha fusionado:


git reset --hard HEAD~1

Esto deshace el último commit y evita incluir cambios no deseados.
hola

## **4. Etiquetado de la versión y creación de la release**
Una vez finalizada la fusión, se etiqueta el último commit como v1.0:

o, si aún no se ha fusionado:


git reset --hard HEAD~1

Esto deshace el último commit y evita incluir cambios no deseados.


git tag v1.0
git push origin v1.0

Esto permite generar una **release** en GitHub a partir de esta versión estable.

## **5. Buenas prácticas evaluadas**
Se considerarán los siguientes aspectos en la evaluación del trabajo:

Uso de **issues** en GitHub y su cierre con commits.  
 Coherencia y claridad en los **comentarios** de los commits.  
Uso correcto de **Markdown** en este archivo.  
Explicación clara de las decisiones tomadas en el desarrollo.  
Completar correctamente los campos en **issues, pull requests y releases**.  

