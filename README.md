# Calculadora de presupuesto — Cobertura audiovisual

Herramienta web (sin backend) para armar cotizaciones de cobertura audiovisual de eventos corporativos: roles en terreno, post-producción, costos operativos, imprevistos, margen de utilidad de sociedad, IVA y reparto de ingresos entre Danny, Reiner y colaboradores externos.

## Uso local

Abre `index.html` directamente en el navegador (doble clic, o arrástralo a una pestaña de Chrome). No requiere instalación ni servidor.

## Cómo funciona

1. **Datos del proyecto** — cliente, tipo de empresa, tipo de evento, fecha.
2. **Configuración de tarifas** — ajusta las tarifas por rol/entregable, el % de imprevistos, el % de margen y el % de reparto entre Danny y Reiner. Se guarda en el navegador (`localStorage`), no requiere volver a escribirlas cada vez.
3. **Paquetes rápidos** — botones que precargan un set típico de roles y entregables (Foto, Video, Mixto, Redes en Vivo, Aftermovie); todo queda editable después.
4. **Bloques 1-3** — roles en terreno, post-producción y costos operativos, cada uno como tabla editable con filas que se agregan o quitan.
5. **Resumen y total** — imprevistos y margen se calculan automáticamente sobre los bloques anteriores; el total se muestra neto, con IVA (19%) y total a facturar.
6. **Reparto de ingresos** — a cada persona se le paga primero su rol ejecutado (columna "Ejecutado por"); lo que queda del margen de utilidad se reparte según el % configurado (50/50 por defecto entre Danny y Reiner). Los colaboradores externos solo cobran su rol.
7. **Generar hoja de presupuesto para el cliente** — arma una vista limpia (sin el desglose interno de reparto) y abre el diálogo de impresión del navegador. Desde ahí se puede guardar como PDF ("Guardar como PDF" en el destino de impresión) o imprimir directo.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub (puede ser privado) y sube `index.html` y este `README.md` a la raíz.
2. En el repositorio: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, rama `main`, carpeta `/root`. Guarda.
3. GitHub entrega una URL tipo `https://tu-usuario.github.io/nombre-repo/` — esa es la calculadora en línea, accesible desde cualquier navegador.
4. Cada cambio que subas a `main` se refleja automáticamente en esa URL en uno o dos minutos.

No hay base de datos ni servidor: todo el cálculo ocurre en el navegador de quien lo abre. Las tarifas configuradas se guardan solo en el navegador donde se editaron — si Danny y Reiner usan computadores distintos, cada uno debe configurar sus tarifas una vez en su propio navegador (o pueden acordar mantener los valores por defecto del código, que ya reflejan lo definido).

## Próximos pasos posibles (no incluidos en esta versión)

- Historial de cotizaciones guardadas (mini dashboard con lista de cotizaciones pasadas).
- Exportación directa a PDF con diseño de marca (sin pasar por el diálogo de impresión).
- Sincronizar tarifas entre navegadores (requeriría una base de datos simple, por ejemplo con GitHub como backend vía un archivo JSON versionado, o un servicio como Supabase/Firebase).
