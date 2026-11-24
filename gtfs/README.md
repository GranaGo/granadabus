# Carpeta de datos GTFS de Granada

Coloca aquí los archivos GTFS (`.zip` o archivos `.txt` extraídos) según el modo de transporte:

- `gtfs/urbano/` → Bus Urbano de Granada (ALSA / Rober)
- `gtfs/interurbano/` → Bus Interurbano de la Junta de Andalucía / CTAGR (puede contener toda Andalucía; el script filtrará **solo Granada** automáticamente)
- `gtfs/metro/` → Metro de Granada

Cuando hagas `git push` con los archivos actualizados, GitHub Actions ejecutará automáticamente `node scripts/process-gtfs.mjs`, filtrará únicamente las paradas, líneas, recorridos y horarios de Granada, regenerará `public/data/network.json` y `public/data/schedules.json`, y desplegará la nueva versión de la PWA sin intervención manual.

Para probarlo en local:
```bash
npm run gtfs:build
```
