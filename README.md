# CS2_2DDEMOVIEWER

ATM (alternate) project fokus pada 2D viewer dari [cs-demo-manager](https://github.com/akiver/cs-demo-manager) oleh AkiVer (MIT License).

## Isi

`upstream/` berisi 45 file hasil pull langsung dari upstream (HEAD, Sep 2026),
tanpa modifikasi, sebagai referensi implementasi 2D viewer:

- Koordinat world → radar: `upstream/src/ui/maps/get-scaled-coordinate-x.ts`,
  `upstream/src/ui/maps/get-scaled-coordinate-y.ts`
- Tipe map: `upstream/src/common/types/map.ts`
- Radar level (upper/lower): `upstream/src/ui/maps/radar-level.ts`
- Main loop: `upstream/src/ui/match/viewer-2d/viewer-2d.tsx` (dual canvas, rAF)
- Render pemain: `upstream/src/ui/match/viewer-2d/drawing/use-draw-players.ts`
- Zoom/pan: `upstream/src/ui/hooks/use-interactive-map-canvas.ts`
- Timeline scrubber: `upstream/src/ui/match/viewer-2d/playback-bar/timeline.tsx`

## Formula inti

```ts
scaledX = ((xFromDemo - map.posX) / map.scale) * imageSize / map.radarSize;
scaledY = ((map.posY - yFromDemo) / map.scale) * imageSize / map.radarSize; // Y inverted
```

## Atribusi

Seluruh file di `upstream/` adalah karya AkiVer dan kontributor cs-demo-manager,
dilisensikan di bawah MIT License (lihat `LICENSE`). File-file lain di repo ini
menyusul sebagai implementasi mandiri berbasis referensi tersebut.
