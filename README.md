# ComPay Website (Astro)

Landing page para promocionar **ComPay**, un sistema de gestión de órdenes con ticket (número + nombre), estados de preparación/entrega, roles (admin/cashier/producer) y pantalla TV (menú + llamados).

## Requisitos

- Node.js **>= 22.12.0**

## Comandos

```sh
npm install
npm run dev
```

Abrirá el servidor en `http://localhost:4321`.

Las capturas públicas de la landing viven en `public/images/compay/` y se referencian como `/images/compay/…` en `src/components/Welcome.astro`.

## Si `npm install` falla en macOS con `esbuild` (spawnSync ... Unknown system error -88)

1) Reinstalación limpia:

```sh
rm -rf node_modules package-lock.json
npm install
```

2) Si sigue fallando, desbloquear binarios descargados por macOS y reconstruir:

```sh
xattr -dr com.apple.quarantine node_modules/@esbuild node_modules/esbuild 2>/dev/null || true
sudo codesign --force --sign - node_modules/@esbuild/darwin-arm64/bin/esbuild
npm rebuild esbuild
```
# promotion_compay_web
