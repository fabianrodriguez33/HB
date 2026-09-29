# Landing page Renöva+ — Instrucciones para Claude Code

Crea desde cero una landing page de una sola página para **Renöva+** en `D:\HB`. La carpeta está vacía salvo la subcarpeta `referencias`. Solo HTML + CSS (más un mini script JS opcional para el año del footer). Sin frameworks ni build.

## 1. Estructura de carpetas
Crea todo lo siguiente (no existe nada aún):
```
D:\HB
├── referencias\            → YA EXISTE, contiene logo.png (no modificar ni borrar)
├── netlify.toml            → [build] publish = "public"
├── README.md
└── public
    ├── index.html
    ├── styles.css
    └── img\logo.png        → COPIA de D:\HB\referencias\logo.png
```
Antes de empezar, lista `D:\HB\referencias` y localiza el logo (`logo.png`; si el nombre o la subcarpeta difieren, busca cualquier .png/.svg/.webp de logo dentro de `D:\HB`). Es la **única imagen disponible**. Todo lo demás (producto, berries, clientes) se hace con CSS/SVG.

## 2. Datos del producto (usar tal cual)
- Nombre: **Renöva+** — colágeno premium en polvo, sabor **berries**.
- **11.4 g de colágeno doblemente hidrolizado con biopéptidos activos** por toma (porción de 15 g de polvo).
- Envase 315 g · 21 porciones.
- Ingredientes a destacar: Colágeno, CoQ10, Biotina, Resveratrol, Magnesio, L-cisteína, Zinc.
- Preparación: 1 medida en 200 ml de agua fría, una vez al día, a la misma hora.
- Público: adultos (sobre todo mujeres 30–55) con cansancio, molestias articulares, piel apagada, cabello y uñas frágiles.
- Mercado: **Perú**. Español peruano neutro (tuteo), `lang="es-PE"`.
- **WhatsApp: +51 968 110 422** → `https://wa.me/51968110422?text=` + mensaje codificado: "¡Hola! Quiero hacer un pedido de Renöva+".
- No publicar precios.

## 3. Reglas de contenido (importante)
- Comparativa: NO atribuir "10 g" a la OMS (no hay recomendación oficial verificada). Usar: **"Los estudios con colágeno hidrolizado usan entre 2.5 y 10 g al día"** frente a **"Renöva+ aporta 11.4 g por toma"**. Dos barras horizontales (la de Renöva+ más larga, magenta con detalle lima).
- Lenguaje prudente: "contribuye", "apoya", "ayuda a". Nada de "cura", "elimina" ni promesas médicas. Resultados: "constancia de 4 a 8 semanas; varían según cada persona".
- Testimonios: 3 tarjetas de ejemplo (nombre + inicial), con nota discreta: "Testimonios de ejemplo — reemplazar por reseñas reales" y comentario `<!-- REEMPLAZAR con reseñas reales -->`. Sin estrellas de "verificado".
- Footer: "Este producto es un suplemento alimentario, no es un medicamento. Consulta a tu médico si estás embarazada, en lactancia o tomas medicación."

## 4. Dirección visual (único, NO genérico de IA)
Concepto: **"Suero de frutos rojos sobre terciopelo"** — oscuro, cálido y editorial, como etiqueta de perfumería.

Paleta en `:root`:
- Fondo `#120A10` (ciruela casi negro), superficie `#1C1119`
- Magenta berry `#D6246E` (principal), hover `#FF5FA2`
- Verde lima `#C6F135` (solo micro-acentos)
- Crema colágeno `#F4E8DC` (texto), secundario `#B9A5AE`

Tipografía: **Fraunces** (títulos, itálica en palabras clave) + **Manrope** (texto), Google Fonts con `preconnect` y `display=swap`.

Rasgos distintivos:
- Hero asimétrico con un **"11.4" gigante** en Fraunces, parcialmente recortado, en magenta.
- Pote del producto dibujado en **CSS/SVG puro** (etiqueta "Renöva+ · berries") rodeado de gotas orgánicas irregulares.
- Grano sutil (SVG noise inline, opacidad ~4%).
- Una sección de fondo **crema invertida** (ingredientes) con separadores curvos.
- Beneficios en bento asimétrico (tamaños distintos, numerados 01–04).
- Ingredientes como lista editorial tipo "carta": nombre grande en Fraunces + función + línea punteada.
- Pain points como texto tipo diario íntimo, frases cortas, no tarjetas idénticas.
- Prohibido: degradados morado→azul, emojis como íconos, íconos de librerías genéricas, sombras suaves repetidas, cliché ("revolucionario", "lleva tu vida al siguiente nivel").
- Animaciones solo con CSS, respetando `prefers-reduced-motion`.

## 5. Imágenes
- Único archivo real: el logo. Copiarlo a `public/img/logo.png` y usarlo en navbar (altura 36–44 px, `alt="Renöva+"`, con `width`/`height`), footer y favicon. No deformarlo; si tiene fondo blanco, avísame al final.
- Nada de imágenes externas ni archivos inexistentes. Testimonios con avatares circulares con la inicial (CSS).
- Al final sugiere qué fotos reales añadir después (pote, mezcla en vaso, clientes).

## 6. Secciones (en este orden)
1. **Navbar**: logo + botón "Pedir por WhatsApp".
2. **Hero**: H1 "**11.4 g** de colágeno doblemente hidrolizado con biopéptidos activos"; subtítulo con sabor berries; botón principal WhatsApp; 3 datos (21 porciones · 315 g · sabor berries); pote CSS/SVG.
3. **Pain points**: "¿Te suena familiar?" — cansancio que no se va, articulaciones que se quejan, piel apagada (+ cabello y uñas frágiles). Cierre: "No tienes que resignarte."
4. **Comparativa**: barras estudios (2.5–10 g) vs Renöva+ 11.4 g, con nota de doble hidrólisis = mejor absorción.
5. **Beneficios**: Movilidad, Energía, Piel, Cabello.
6. **Ingredientes**: Colágeno (doble hidrólisis, biopéptidos), CoQ10 (energía celular), Biotina (cabello, piel y uñas), Resveratrol (antioxidante), Magnesio (músculos, disminuye cansancio), L-cisteína (queratina), Zinc (piel sana, sistema inmune).
7. **Testimonios** (ver sección 3).
8. **Banda CTA** con botón WhatsApp.
9. **FAQ** con `<details>/<summary>` (sin JS), marcador "+" que rota: cómo se toma; seguridad/advertencias; cuándo se notan resultados; qué es doblemente hidrolizado; contiene azúcar ("consulta la etiqueta del envase"); cómo pedir (WhatsApp: cantidad, ubicación, pago y entrega).
10. **Footer**: logo, aviso legal, año dinámico.
11. **Sticky CTA**: botón fijo inferior "Pedir por WhatsApp", visible en móvil y escritorio, con `padding-bottom` en el body.

## 7. Técnico
- Botones WhatsApp: `<a href="https://wa.me/51968110422?text=..." target="_blank" rel="noopener">`.
- Mobile-first, breakpoints 560 / 860 / 1000 px, sin scroll horizontal a 360 px.
- Accesibilidad: contraste AA, `:focus-visible`, jerarquía h1→h2→h3.
- SEO: `<title>`, meta description, Open Graph.
- CSS ordenado con variables, < 30 KB.

## 8. Netlify
`netlify.toml`:
```
[build]
  publish = "public"
```
Desplegar es opcional (solo para link público): `netlify deploy --prod --dir=public`. Para probar local basta abrir `public/index.html`.

## 9. Al terminar
Prueba a 360, 768 y 1280 px, verifica los enlaces de WhatsApp y resume lo pendiente (fotos reales, testimonios reales, confirmar azúcar en etiqueta).
