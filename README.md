# Ley de Ohm en Realidad Aumentada

Sitio web (un solo archivo, `index.html`) que muestra un circuito simple —batería, cables, resistencia y bombillo— colocado sobre una superficie real usando la cámara del teléfono.

## Física

- I = V / (R + R_b), con R_b = 10 Ω (filamento del bombillo).
- Voltaje: slider continuo de **3 V a 12 V**.
- Resistencia: slider continuo de **10 Ω a 200 Ω** → corriente entre ~14 mA y 600 mA.
- La **velocidad de los electrones es proporcional a la corriente** (v ∝ I). La cantidad de electrones en el cable no cambia, como en un metal real (I = n·q·v·A).
- El brillo del bombillo depende de la potencia P = I²·R_b.
- La resistencia muestra su código de colores real y la batería lleva impreso el voltaje elegido.
- Los electrones circulan del polo − al polo + (sentido real).

## Permisos

Al abrir el sitio aparece una pantalla que pide permiso para la **cámara** y los **sensores de movimiento**:
- **iPhone/iPad (Safari):** se piden `DeviceOrientationEvent.requestPermission()` y `DeviceMotionEvent.requestPermission()` además de la cámara.
- **Android (Chrome):** se pide la cámara; los sensores se verifican con la API de permisos.

## Modos de RA

- **Android con ARCore (Chrome):** WebXR con detección real de superficies (hit-test).
- **iOS y navegadores sin WebXR:** vídeo de la cámara + giroscopio; la superficie se estima a partir de la inclinación del teléfono.

## Publicarlo (requiere HTTPS)

La cámara solo funciona en `https://`. La forma más simple es GitHub Pages:
1. En el repositorio: **Settings → Pages → Source: Deploy from a branch**, elige la rama y la carpeta `/ (root)`.
2. Abre en el teléfono `https://<usuario>.github.io/<repositorio>/`.
