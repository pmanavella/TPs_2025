# Decisiones del Proyecto

## Tarea 1: Configurar identidad y repositorio
- Se hizo un fork al repositorio original, lo consideré más conveniente para tener los permisos completos en mi copia y poder actualizar los cambios.
- Se clonó el repositorio original.
- Se configuró el usuario con nombre y correo electrónico.
- Se creó el archivo `decisiones.md` y se realizó la primera confirmación (commit), sobre el cual estoy escribiendo ahora mismo.
- Se sincronizó con el repositorio original (upstream) para traer los últimos cambios del repositorio original mediante los comandos:
    - `git fetch upstream`
    - `git merge upstream/main`

## Tarea 2: Desarrollar una funcionalidad
- Se creó una nueva rama, usé el formato `feature/... ` para que sea lo más descriptivo posible.
    - `git checkout -b feature/nueva-funcionalidad`
- Se realizaron dos commits atómicos:
    - "Agrego archivo inicial de la nueva funcionalidad"
    - "Agrego segunda parte de la funcionalidad"
- Se subió la rama al fork:
    - `git push origin feature/nueva-funcionalidad`

## Tarea 3: Corrección de error (hotfix)
- Se vuelve a la rama main:
    - `git checkout main`
- Se creó la rama hotfix para simular el error:
    - `git checkout -b hotfix/error-simulacion`
- Se simula un error en `funcionalidad.txt`:
    - `echo "Error simulado para prueba hotfix" >> funcionalidad.txt`
- Se corrige el error quitando la línea:
    - `sed -i '' '/Error simulado para prueba hotfix/d' funcionalidad.txt`
- Se sube hotfix al fork:
    - `git push origin hotfix/error-simulacion`

## Tarea 4: Hacer Pull Request y aceptarlo
- Se sube la rama de desarrollo al fork:
    - `git checkout feature/nueva-funcionalidad`
    - `git push origin feature/nueva-funcionalidad`
- Dentro de GitHub:
    - Se accede al banner “Compare & pull request” para la rama recién subida.
    - Se elige base: `main` y compare: `feature/nueva-funcionalidad`.
    - Se asigna el título: **Integración de nueva funcionalidad**, se escribe la descripción y se hace clic en **Create pull request**.
- Se revisa que las ramas estén actualizadas:
    - `git checkout main`
    - `git pull origin main`

## Tarea 5: Crear la versión etiquetada
- Se creó el tag **v1.0** para marcar una versión estable del proyecto mediante:
```
git tag -a v1.0 -m "Versión estable 1.0"
git push origin v1.0
```

**Convenciones utilizadas:**
- Utilicé el prefijo **v** antes del número de versión, siguiendo la convención común en control de versiones para indicar que se trata de una *versión*.
- El número **1.0** indica la primera versión estable del proyecto.
  - `1` indica que es la primera versión estable (cambios significativos desde el desarrollo inicial).
  - `0` indica que no hay revisiones menores todavía.

**Razón de la convención:**
- Se eligió **v1.0** porque representa el primer estado del proyecto listo para uso estable.
- Esta práctica permite mantener un historial claro, identificar versiones y facilitar actualizaciones o correcciones futuras.

