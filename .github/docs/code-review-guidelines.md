# Code Review Guidelines

## Propósito

Los code reviews nos ayudan a mejorar la calidad, reducir bugs, compartir conocimiento y mantener el codebase sostenible.

Un review no se trata únicamente de encontrar errores. También debe confirmar que el cambio sea entendible, seguro, probado y alineado con los requerimientos del proyecto.

---

## Cuándo se requiere un review

Se requiere un Pull Request para todos los cambios que vayan a protected branches como:

* `main`
* `staging`
* `production`

No se permiten direct pushes a protected branches.

---

## Responsabilidades del reviewer

Al revisar un PR, verificar lo siguiente:

### 1. Requerimientos y alcance

* ¿El PR resuelve la tarea solicitada?
* ¿El cambio está alineado con los acceptance criteria?
* ¿El PR está enfocado o incluye cambios no relacionados?
* ¿Faltan edge cases?

### 2. Calidad del código

* ¿El código es fácil de entender?
* ¿Los nombres son claros y consistentes?
* ¿La solución es lo más simple posible frente a otras alternativas?
* ¿Hay código duplicado que debería reutilizarse?
* ¿El código está organizado en la layer/module/component correcta?

### 3. Funcionalidad

* ¿La lógica tiene sentido?
* ¿Esto podría romper un flujo existente?
* ¿Los casos de error se manejan correctamente?
* ¿Se aplican validaciones donde corresponde?
* ¿Se manejan valores vacíos, null, inválidos o inesperados?

### 4. Seguridad

* ¿Hay secrets, keys, tokens, passwords o connection strings expuestos?
* ¿Se validan correctamente los permisos del usuario?
* ¿Se valida el input del usuario?
* ¿Los authorization checks se aplican en el backend y no solo en el frontend?
* ¿El cambio evita queries inseguras o riesgos de injection?
* ¿El cambio sigue prácticas de desarrollo seguro OWASP?

### 5. Cambios de base de datos y datos

* ¿Las migrations o cambios de schema fueron revisados cuidadosamente?
* ¿Los datos existentes están protegidos?
* ¿El cambio podría causar pérdida de datos?
* ¿Se necesitan indexes para nuevas queries?
* ¿Las queries son suficientemente eficientes para el uso esperado?
* ¿Es posible hacer rollback si el cambio falla?

### 6. Cambios de API/backend

* ¿Los endpoints están protegidos con la authentication/authorization correcta?
* ¿Los request y response models son claros?
* ¿Los status codes son apropiados?
* ¿Los errores se manejan de forma consistente?
* ¿Los logs son útiles sin exponer datos sensibles?

### 7. Cambios de frontend

* ¿La UI cumple con el comportamiento/diseño esperado?
* ¿Se manejan los estados de loading, empty, error y success?
* ¿Los forms se validan antes del submission?
* ¿El cambio funciona en los screen sizes relevantes?
* ¿Los API errors se muestran claramente al usuario?

### 8. Testing

* ¿El autor explicó cómo fue probado el cambio?
* ¿Se incluyeron automated tests cuando era razonable?
* ¿Los flujos afectados fueron probados manualmente en QA/staging?
* ¿Los flujos críticos siguen funcionando?
* ¿El PR incluye screenshots o evidencia cuando es útil?

### 9. Performance y confiabilidad

* ¿Este cambio podría hacer que la app sea más lenta?
* ¿Se evitan API calls innecesarias?
* ¿Los archivos grandes, loops o queries se manejan de forma segura?
* ¿El cambio es resiliente ante fallos, retries o malas condiciones de red?

### 10. Mantenibilidad

* ¿Otro developer podrá entender esto en el futuro?
* ¿Se necesita documentación?
* ¿Los comentarios son útiles y no excesivos?
* ¿La implementación es consistente con el resto del proyecto?

---

## Responsabilidades del autor

Antes de solicitar un review, el autor del PR debe:

* Mantener el PR enfocado y de tamaño razonable
* Agregar una descripción clara del cambio
* Vincular el issue o task relacionado
* Explicar cómo fue probado
* Agregar screenshots para cambios de UI cuando sea útil
* Confirmar que la app build correctamente
* Confirmar que no hay errores evidentes en console o backend
* Mencionar cualquier riesgo, migration o deployment step

---

## Estilo del feedback en review

El feedback debe ser claro, respetuoso y específico.

Usar lenguaje como:

```txt
¿Podríamos simplificar esto haciendo...?
Creo que esto podría fallar cuando...
Esto se ve bien, pero sugeriría...
¿Hay alguna razón por la que estamos haciendo X en lugar de Y?
```
