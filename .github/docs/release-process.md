# Release Process

## Días estándar de release

Los releases planificados a producción se realizan los:

* Martes por la mañana
* Jueves por la mañana

No se realizan releases planificados a producción los viernes, a menos que sean aprobados como hotfix.

## Release flow

feature branch → PR → staging → QA validation → release PR → main → production

## Requisitos para producción

Antes de hacer merge a main:

* PR aprobado
* CI/CD passed
* QA tested
* Release notes incluidas
* Rollback plan incluido

## Hotfix process

Los hotfixes pueden liberarse fuera de la ventana estándar de release cuando producción está afectada.

Los hotfixes deben seguir usando un Pull Request, a menos que se apruebe una excepción.
