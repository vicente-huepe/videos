# Guía de edición: anuncios de Reluce

Cómo editamos los anuncios de Reluce para TikTok y Reels. Úsala como punto de partida para cada video nuevo.

## Material de entrada

- **Video:** un clip vertical de 720×1280 ya sin textos incrustados (los avisos de abajo se sacan con un zoom leve de 5 a 10 %).
- **Voz:** una locución de ElevenLabs (voz Angela) con el guion, más el guion en texto.
- **Logo:** `reluce` en blanco con la estrella celeste `#0BA4B2`, sacado del PDF de marca.

## Reglas

1. **Sin pausas.** Entre frases de la voz quedan como máximo 0,05 s. Ningún silencio de más de 0,2 s salvo el cierre.
2. **Sin precios en pantalla ni en la voz.** El cierre invita a mirar la oferta en el link.
3. **Ofertas solo si son ciertas.** "Solo por hoy", "2x1", "compra 1 y te regalamos el segundo" o "regálale el otro a tu mejor amiga" se usan únicamente cuando esa promoción existe de verdad en la tienda ese día. Con los precios actuales (1 × $27.990, 2 × $41.990) la segunda unidad no es gratis, así que la frase por defecto es "Mira la oferta del pack de 2 en el link".
4. **Todo lo que dice la voz va escrito en pantalla**, en tramos de máximo 2 líneas que cambian justo con cada frase.
5. **Cada frase sobre su toma.** Se reordenan y ajustan las tomas para que lo que se ve calce con lo que se dice.
6. **Sin audio original.** Solo la voz, normalizada a -14 LUFS.
7. **No quitar etiquetas de IA** si el video original las trae.
8. **No reutilizar la voz ni el testimonio de otra creadora.** Si el video trae voz o subtítulos de otra persona, se genera una locución nueva. Los subtítulos incrustados que no se pueden recortar se borran cuadro por cuadro (letras blancas o celestes con borde negro, rellenadas con lo de alrededor) y los nuestros van justo encima, sin franja de fondo.

## Estilo de texto

- Montserrat SemiBold 64 px (56 a 58 px si una línea no cabe), blanco con sombra negra suave, sin borde.
- Celeste `#0BA4B2` solo en "reluce" y en "pack de 2".
- Tipo oración, "reluce" en minúscula.
- Centrado entre x 90 y x 950, con el texto terminando a 1.480 px (deja libres los 440 px de abajo y el borde derecho).
- Aparición y salida con fundido de 0,1 a 0,12 s.
- Cierre: logo de 440 px + "Tu casa, impecable".

## Proceso

1. Detectar las pausas de la voz (`silencedetect`) y asignar cada tramo a una frase del guion.
2. Detectar los cortes de escena del video (`select='gt(scene,0.25)'`) y ver un cuadro de cada toma.
3. Asignar tomas a frases y armar la línea de tiempo sin pausas.
4. Ajustar la velocidad de cada toma al largo de su frase. Si hay que ralentizar más de un 12 %, usar interpolación de movimiento (`minterpolate` con `mi_mode=mci`) para que no se entrecorte.
5. Renderizar en 1080×1920, 30 fps, H.264, AAC 192 kbps.
6. Revisar un cuadro de cada subtítulo y confirmar que no quedan silencios.

## Videos hechos

- `editados/reluce_cepillo_1080x1920.mp4`
- `editados/reluce_cr7_cepillo_1080x1920.mp4`
- `editados/reluce_video1_cepillo_1080x1920.mp4`
- `editados/reluce_video2_cepillo_1080x1920.mp4`
- `editados/reluce_tctewwmkeks4_1080x1920.mp4` (subtítulos antiguos borrados cuadro por cuadro; los nuestros terminan a 1.530 px para quedar encima de esa zona)
- `editados/reluce_video1_devolver_1080x1920.mp4` (hook "voy a tener que devolver este cepillo"; el pack de 2 sí tiene descuento real frente a 2 unidades sueltas)
