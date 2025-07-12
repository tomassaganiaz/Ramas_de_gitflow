# Ramas_de_gitflow
Crear todos los grupo de la estructura GitFlow

1. Main (también puede llamarse master)
Función: Rama principal. Contiene código estable y listo para producción.

Estructura: main

2. Develop
Función: Rama de desarrollo. Aquí se integran las funcionalidades completadas antes de pasarlas a producción.

Estructura: develop

3. feature/*
Función: Desarrollo de nuevas funcionalidades.

Base: Se ramifican desde develop y se integran nuevamente a develop.

Estructura: feature/nombre-funcionalidad

Ejemplos:

feature/login-usuario

feature/agregar-carrito


4. release/*
Función: Preparar una versión lista para producción. Se corrigen bugs menores, ajustes finales.

Base: Se crea desde develop y se fusiona en main y develop.

Estructura: release/version

Ejemplos:

release/1.0.0

release/2.1.3

5. hotfix/*
Función: Corregir errores críticos en producción.

Base: Se crea desde main y se fusiona tanto a main como a develop.

Estructura: hotfix/nombre-fix

Ejemplos:

hotfix/fix-login

hotfix/error-carga

6. bugfix/* (opcional, no es estándar GitFlow pero es usado en algunos equipos)
Función: Corregir errores menores o no críticos durante el desarrollo (a diferencia de hotfix que es para producción).

Base: Desde develop y vuelve a develop.

Estructura: bugfix/descripcion

Ejemplo: bugfix/validacion-email
______________________________________________
main
│
├─ hotfix/*     ← producción urgente
│
├─ develop
│   ├─ feature/*  ← nuevas funcionalidades
│   ├─ bugfix/*   ← correcciones menores
│   └─ release/*  ← versiones estables
______________________________________________
¿Cómo usar cada rama?

 1. ✅ main
. Contiene solo el código estable en producción.

. No se trabaja directamente aquí (excepto cuando se hace merge de release o hotfix).
______________________________________________________________________________________
Bash

git checkout main
git merge release/1.0.0      # Al terminar una release
git merge hotfix/fix-login   # Al corregir algo crítico en producción
______________________________________________________________________________________
2. ✅ develop
. Rama principal de desarrollo, donde se integran todas las funcionalidades antes de lanzar una versión.

. De aquí salen los feature, bugfix y release.
______________________________________________________________________________________
Bash

git checkout develop
git merge feature/nueva-funcionalidad
git merge bugfix/arreglo-menor
______________________________________________________________________________________
3. ✅ feature/*
. Para nuevas funcionalidades.

. Se crea desde develop y se vuelve a fusionar en develop.
______________________________________________________________________________________
Bash

git checkout develop
git checkout -b feature/login-usuario    # Crear una nueva funcionalidad

# ...hacés commits...

git checkout develop
git merge feature/login-usuario         # Una vez terminada
git branch -d feature/login-usuario     # Eliminás si ya no se usa
_____________________________________________________________________________________
4. ✅ release/*
. Para preparar una nueva versión de producción (corregís bugs, ajustes menores).

. Se crea desde develop, y se fusiona tanto en main como en develop.
____________________________________________________________________________________
Bash

git checkout develop
git checkout -b release/1.0.0            # Nueva release

# ...ajustás detalles, versión, README, etc...

git checkout main
git merge release/1.0.0                 # Lo pasás a producción

git checkout develop
git merge release/1.0.0                 # También se integra a desarrollo

git branch -d release/1.0.0
__________________________________________________________________________________
5. ✅ hotfix/*
. Para solucionar errores críticos directamente en producción.

. Se crea desde main, y se fusiona tanto en main como en develop.
___________________________________________________________________________________
Bash

git checkout main
git checkout -b hotfix/fix-error-crash

# ...corregís el error...

git commit -am "Fix error crash"
git checkout main
git merge hotfix/fix-error-crash

git checkout develop
git merge hotfix/fix-error-crash

git branch -d hotfix/fix-error-crash
_____________________________________________________________________________________
6. ✅ bugfix/* (opcional)
. Para arreglos menores que no afectan producción directamente.

. Igual a feature, pero para bugs pequeños.
______________________________________________________________________________________
Bash

git checkout develop
git checkout -b bugfix/validacion-email

# ...corregís...

git checkout develop
git merge bugfix/validacion-email
git branch -d bugfix/validacion-email
______________________________________________________________________________________


