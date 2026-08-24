# cubicapp-legal

Las dos páginas públicas que Google Play exige para **CubicApp**:

| Página | URL |
|---|---|
| Política de tratamiento de datos | https://cqo-ia.github.io/cubicapp-legal/ |
| Eliminación de datos | https://cqo-ia.github.io/cubicapp-legal/eliminar.html |

## No se editan a mano

Salen de `src/data/privacy.ts`, en el repositorio de la app, que es el mismo
texto que CubicApp le muestra al usuario y sobre el que él autoriza. Para
cambiarlas se edita allá y se vuelve a generar:

```bash
CUBICAPP_REGISTRY_URL='<la URL de Apps Script>' \
node scripts/google/generar-paginas-legales.mjs
```

Editarlas aquí haría que el texto publicado y el autorizado dejaran de
coincidir, y ante la **Ley 1581 de 2012** el que vale es el que el usuario
autorizó dentro de la app.

## Por qué este repositorio existe

La política vivía en la aplicación web de Apps Script, y **Play rechaza esa
URL**: `script.google.com/macros/s/…/exec` responde con un redirect a
`googleusercontent.com` y la consola contesta «No se puede usar esta URL como
vínculo para la política de privacidad».

El formulario que de verdad borra los datos sigue en Apps Script —necesita
escribir en la hoja y mandar el código de confirmación—; esta es la puerta
pública que Play exige e indexa, y lleva allá.

---

CQO-IA · Bucaramanga, Colombia
