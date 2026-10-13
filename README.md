# PeraCo Fase 3 — GitHub Pages + catálogo público seguro

## Incluye
- `index.html`: interfaz PeraCo preparada para cargar solo la vista `catalog_public` de Supabase.
- `peraco_catalog_public.sql`: crea la vista de solo lectura con SKU, nombre comercial, unidad, categoría y precio de venta. No incluye proveedores, restaurantes, costos ni pedidos.

## Pasos
1. En Supabase → SQL Editor, ejecuta `peraco_catalog_public.sql`.
2. En Supabase → Project Settings → API, copia Project URL y la publishable key (o anon key legacy). Nunca uses `service_role` ni una secret key en HTML.
3. Abre `index.html` en un editor de texto y localiza `PERACO_SUPABASE_URL` y `PERACO_SUPABASE_ANON_KEY`. Pega los valores entre las comillas simples.
4. Sube `index.html`, `.nojekyll` y `README.md` a la raíz del repositorio GitHub Pages. Puedes subir también el SQL como referencia, pero no es necesario para publicar.
5. En GitHub → Settings → Pages, selecciona `main` y `/ (root)`.
6. Abre la URL pública y verifica que los productos provienen de Supabase.

## Privacidad y límites de esta fase
- El HTML solo consulta `catalog_public`, que contiene únicamente datos comerciales públicos.
- No contiene credenciales secretas. La clave publishable/anon no es un secreto; su seguridad depende de los permisos y la vista limitada.
- No se exponen tablas privadas directamente a usuarios anónimos.
- Esta fase conecta el catálogo, NO crea pedidos compartidos ni automatiza WhatsApp. Los pedidos del prototipo siguen siendo locales y el flujo de WhatsApp requiere configuración adicional.
- Antes de registrar datos reales, probar RLS y políticas de autorización con cuentas separadas.
