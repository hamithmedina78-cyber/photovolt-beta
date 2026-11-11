# Audio grabado de PHOTOVOLT

El juego trae música y efectos **propios** en MP3, compuestos y sintetizados por `scripts/make-audio.mjs` (sin muestras de terceros). Para regenerarlos: `npm run audio`.

Para cambiarlos por grabaciones:

1. Copia los archivos en esta carpeta:
   - Efectos: `sfx/<nombre>.ogg` y `sfx/<nombre>.mp3`.
   - Música: `music/<zona>.ogg` y `music/<zona>.mp3`.
   Pon los dos formatos: OGG para Chrome/Android y MP3 para Safari/iOS.
2. Anótalos en `manifest.json`, por ejemplo:

```json
{
  "sfx": { "drill": ["sfx/drill.ogg", "sfx/drill.mp3"], "cash": ["sfx/cash.ogg", "sfx/cash.mp3"] },
  "music": { "obra": ["music/obra.ogg", "music/obra.mp3"] }
}
```

Lo que no esté en el manifiesto se sigue sintetizando.

**Efectos** (nombre → cuándo suena): `pop` botón · `click` · `screw` atornillar · `clunk` golpe/colgar · `strip` pelar/soplar · `zap` chispazo · `ok` éxito · `cash` caja registradora · `bad` error · `drill` taladro · `drive` camioneta · `ratchet` matraca · `torque` clic del torquímetro · `seal` sellador · `stamp` sello de la UVIE.

**Música** (zona): `menu`, `oficina`, `obra`, `empresa`. Se repite sin corte: exporta el ciclo exacto.

Recomendaciones:
- Efectos: menos de 1 s y 44.1 kHz mono, normalizados a −3 dB.
- Música: 1 a 2 minutos, −14 LUFS.
- Usa solo sonidos con licencia que permita venderlos dentro de un juego (CC0 o comprados) y guarda el comprobante.
