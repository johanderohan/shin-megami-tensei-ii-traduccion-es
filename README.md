# Shin Megami Tensei II — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/playstation/shin-megami-tensei-ii)**.

Traducción al **español de España** de *Shin Megami Tensei II* (真・女神転生Ⅱ, PlayStation, 2002),
la versión de PlayStation del RPG de Atlus de 1994. Décadas después de la Gran Destrucción,
Tokio es TOKYO Millennium, una ciudad cerrada gobernada por la Iglesia Mesiánica; un luchador del
Coliseo sin memoria descubre que su destino está en juego entre la Ley y el Caos. Esta versión
nunca salió de Japón.

La traducción se distribuye como **parche**. No incluye el juego: necesitas tu propia copia
japonesa (Rev 1) para aplicarlo.

## Estado

Última versión: **[v1.0](../../releases/tag/v1.0)**.

| Parte | Estado |
|---|---|
| Guion de la historia, pueblos y personajes | 2.052 mensajes traducidos |
| Conversación y negociación con demonios | 1.829 textos traducidos |
| Combate | 274 mensajes traducidos |
| Menús, ayudas, tiendas, casino, estado y tarjeta de memoria | Traducidos |
| Demonios, razas, objetos, magias, lugares y bebidas | Traducidos (glosario de 1.114 nombres) |
| Vídeos (introducción y fin de partida) | Texto en castellano |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Revisión durante una partida | Parcial (ver abajo) |

Detalles técnicos:

- Traducción hecha **desde el japonés**, con biblia de términos y una revisión editorial
  independiente de fidelidad y naturalidad.
- Letras españolas dibujadas a partir de la propia fuente del juego, con el mismo color, sombra
  y anchura variable que el resto del texto.
- El texto de la introducción y del fin de partida se ha vuelto a componer en castellano con la
  fuente del juego.
- Bancos de diálogo ampliados hasta el máximo que admite el juego para que quepa el castellano.

Se quedan como en el original:

- El logotipo y los rótulos gráficos en inglés que forman parte de la imagen del juego
  («PRESS ANY BUTTON», «NEW GAME», «COMP», «STATUS», «FULL MOON», «YES/NO»…).
- Los menús y rótulos que el original ya escribe en inglés (HP, MP, EXP, LEVEL…) y los estados
  alterados (POISON, PALYZE, STONE…).
- La mecánica del juego: no se añade ninguna mejora respecto al original.

### Comprobaciones y trabajo pendiente

Se ha jugado en emulador desde una partida nueva. Se han comprobado:

- La pantalla de título, el vídeo de introducción y el despertar en el gimnasio de Okamoto.
- El menú del gimnasio, la tarjeta de memoria (guardar partida, con los nombres de lugar en
  castellano) y el entrenamiento en el espacio virtual.
- Un combate (aparición de enemigos, órdenes, ataque y daño), el menú de campo, la pantalla de
  estado y la de equipo.
- El vídeo de fin de partida, decodificándolo.

El texto de todo el juego se ha comprobado automáticamente: controles, anchura de línea en
píxeles, líneas por ventana y caracteres. La imagen construida se ha contrastado mensaje a mensaje
con el texto traducido. El parche se ha aplicado sobre el BIN japonés original y el resultado se
ha comparado byte a byte con la imagen probada.

**No se ha jugado una partida completa de principio a fin** ni se ha probado en consola real. La
negociación con demonios, las tiendas, el casino, la Catedral de las Sombras y los tramos
avanzados del guion no se han recorrido dentro de una partida (sus textos se han revisado en los
datos del disco, incluidas las combinaciones de fragmentos de la negociación). La traducción y su
revisión se han hecho con asistencia de IA, sin revisores humanos independientes. Si encuentras un
error, abre una incidencia con una captura.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de **Shin Megami Tensei II (Japón), Rev 1**, SLPM-86924, en formato BIN/CUE
   de una sola pista.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Shin Megami Tensei II (Japan) (Rev 1).bin` |
   | Tamaño | 222.694.416 bytes |
   | MD5 | `5082e5b110f05d55440a44e01aa10cc9` |

   ```bash
   md5sum "Shin Megami Tensei II (Japan) (Rev 1).bin"                 # Linux
   md5 "Shin Megami Tensei II (Japan) (Rev 1).bin"                    # macOS
   CertUtil -hashfile "Shin Megami Tensei II (Japan) (Rev 1).bin" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto. La primera edición (sin Rev 1)
   no sirve.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Shin Megami Tensei II (Japan) (Rev 1).bin" parche.xdelta "Shin Megami Tensei II (ES).bin"`
5. Comprueba que el BIN resultante mide 222.694.416 bytes y tiene el MD5
   **`57dfdc4aafe32252d3ced554d8d92be2`** (v1.0).
6. Crea un CUE para el nuevo BIN, por ejemplo `Shin Megami Tensei II (ES).cue`:

   ```
   FILE "Shin Megami Tensei II (ES).bin" BINARY
     TRACK 01 MODE2/2352
       INDEX 01 00:00:00
   ```

7. Carga el CUE en tu emulador y empieza una partida nueva.

Aplica cada versión sobre el **BIN japonés original**, no sobre una copia ya traducida.

## Créditos

- Traducción al castellano, biblia, fuente española y construcción: johanderohan.
- La parte técnica se basa en el proyecto de código abierto
  [smt2-psx-translation](https://github.com/Roman215/smt2-psx-translation) de Roman (licencia MIT,
  © 2026 Roman), traducción al inglés de esta misma revisión: compresión de los bancos de texto,
  anchura variable, reubicación de textos, arreglos de cuelgues y recomposición de vídeos. De ese
  proyecto se ha usado el código, no su traducción inglesa.
- Codificador de vídeo: [psxavenc](https://github.com/WonderfulToolchain/psxavenc).

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
Atlus ni Sega. Aquí no se distribuye el juego ni ninguna parte de él: solo un parche que
modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
