# PR Template

## Resumen
¿Qué cambió?

## Related issue
Cuál # issue cierra?

## Tipo de cambio

* [ ] Bug fix
* [ ] New feature
* [ ] Refactor
* [ ] Documentation
* [ ] Configuration / DevOps

## ¿Cómo fue probado?
Describe cómose probó el cmabio.

* [ ] Tested locally
* [ ] Tested in QA/staging
* [ ] Main user flow tested
* [ ] No se encontraron errores en console/API
* [ ] No se encontró ninguna regression evidente

## Checklist

* [ ] El código pasa build correctamente
* [ ] Se agregaron o actualizaron tests, si era necesario
* [ ] Se incluyen migration scripts de bd, si era necesario
* [ ] No se subieron secrets ni credentials
* [ ] La documentación o los ejemplos de env fueron actualizados, si era necesario
* [ ] El reviewer sabe cómo validar este cambio

## Release notes

Describe cualquier información importante para producción.

## Risk level

* [ ] Low
* [ ] Medium
* [ ] High

## Rollback plan

¿Cómo se puede revertir este cambio si algo sale mal? Todo cambio a base de datos debe incluir rollback script. Si son solo cambios de código se podría hacer solo un rollback. Cambios a configuraciones de proveedores de infraestructura, correo, etc pueden requerir otras cosas
