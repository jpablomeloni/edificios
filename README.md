# Links cortos de Cuentas del Edificio

Páginas de redirección para GitHub Pages. Cada carpeta es un edificio y su `index.html` manda al link largo de la aplicación (Apps Script, con el token del edificio).

```
/                → portada genérica ("usá el link de tu edificio")
/admin/          → acceso de administración (URL de la app sin token)
/reymartin/      → Edificio Rey Martin III
/<identificador>/→ cada edificio nuevo
/404.html        → link inexistente
```

## Puesta en marcha (una vez)

1. Crear un repositorio **público** llamado `edificios` (GitHub Pages gratis exige repo público).
2. Subir el contenido de esta carpeta, incluido `.nojekyll`.
3. **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. A los 1–2 minutos queda en `https://<usuario>.github.io/edificios/`.

## Agregar o actualizar un edificio

1. En la app, pestaña **Edificios** → **Página de redirección (GitHub)** del edificio.
2. Crear en el repo la carpeta con el identificador (ej. `reymartin/`) y adentro `index.html` con ese contenido (botón **Descargar** o **Copiar**).
3. Commit. El link corto queda `https://<usuario>.github.io/edificios/<identificador>`.
4. En la app, **Editar** el edificio y pegar ese link en **Link corto**: desde ahí "Copiar acceso" manda el link corto.

Si se genera un **link nuevo** para un edificio (por ejemplo porque se filtró), repetir los pasos 1–3: la URL corta no cambia para nadie.

## Importante

- El repo es público: cualquiera puede ver los tokens de los edificios. La seguridad está en la clave de cada unidad y en el bloqueo de 5 intentos / 15 minutos, no en el link.
- Si en algún momento se quiere que los links sean privados, usar dominio propio + reglas de redirección de Cloudflare. La app no cambia: solo se actualiza el "Link corto" de cada edificio.
- Si se cambia la implementación de Apps Script por una **nueva** (en vez de "Nueva versión" de la misma), cambia la URL `/exec`: hay que regenerar todas las páginas y actualizar `admin/index.html`.
