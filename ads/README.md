# Anuncios de Take Your Pills

La app lee `ads.json` de esta carpeta (GitHub Pages). **Para cambiar los anuncios
no hace falta publicar una versión nueva de la app**: edita este archivo o sube
otra imagen, haz commit, y la app lo mostrará en menos de una hora (al abrirse).

## Formato

```json
{
  "version": 1,
  "ads": [
    {
      "id": "farmacia-san-jose-oct",
      "active": true,
      "title": "Farmacia San José",
      "subtitle": "Domicilios gratis en Chapinero",
      "image": "https://alejandr0pg.github.io/takeyourpills-legal/ads/farmacia.jpg",
      "link": "https://farmaciasanjose.example",
      "start": "2026-10-01",
      "end": "2026-11-01",
      "weight": 2
    }
  ]
}
```

| Campo | Obligatorio | Qué hace |
|---|---|---|
| `id` | sí | Identificador único. |
| `image` | sí | URL **https** de la imagen. Cuadrada (mínimo 240×240, ideal 480×480) si hay `title`; banner 3:1 (por ejemplo 1200×400) si no hay `title`. |
| `link` | sí | Página **https** del anunciante, o `app://anunciate` para abrir el formulario «Anúnciate con nosotros». |
| `title`, `subtitle` | no | Texto de la tarjeta. Sin `title`, el anuncio se muestra como banner de imagen. |
| `start`, `end` | no | Fechas (AAAA-MM-DD). Se muestra desde `start` y hasta antes de `end`. |
| `weight` | no | Probabilidad relativa si hay varios anuncios activos (por defecto 1). |
| `active` | no | `false` para pausarlo sin borrarlo. |

## Reglas

- Cada tarjeta muestra siempre la etiqueta «Publicidad».
- No aceptar anuncios engañosos ni de medicamentos que requieran receta.
- Imágenes ligeras (menos de 200 KB), sin texto diminuto: la audiencia es mayor.
- Si el JSON tiene un error, la app sigue mostrando el último anuncio válido.
