# studio

Mapa de direcciones de España: [MapLibre GL JS](https://maplibre.org/) +
[OpenFreeMap](https://openfreemap.org) (tiles, estilo `liberty`) sobre
el [servicio de direcciones](https://github.com/ygModesto/localizaciones)
(SQLite+FTS5+R-Tree en AWS Lambda, datos de CartoCiudad/IGN).

Página estática, sin build step — `index.html` es todo. Se sirve tal
cual con GitHub Pages.

## Funciones

- Buscar calle por texto (ordena por cercanía al centro visible del mapa).
- Elegir una calle → lista de números de portal → marcador exacto.
- 🎯 "Cerca de mí" — geolocalización del navegador + direcciones más próximas.

## Desarrollo local

```bash
python3 -m http.server 8080
# abrir http://localhost:8080
```

No hace falta nada más: todas las dependencias (MapLibre GL JS) se
cargan desde CDN, y el mapa llama directamente al API del servicio de
direcciones (CORS abierto, endpoint público de solo lectura).
