# juguitos-cloud

Estructura de datos para sincronización vía GitHub Contents API.

```
juguitos-cloud/
  branches/
    SUC-{ID}/
      index.json          // {branchId, branchName, lastSync}
      stock.json          // { [supplyId]: units }
      orders_YYYYMM.json  // [ órdenes del mes ]
      moves_YYYYMM.json   // [ movimientos de inventario del mes ]
```
- Mes actual: **202511**
- Agrega más sucursales creando `branches/SUC-<NUEVA>/` con los 4 archivos.

## Convenciones
- `branchId` es estable (no cambia si renombra la sucursal).
- `lastSync` ISO (lo escribe la app al terminar un sync).
- `orders_YYYYMM.json` y `moves_YYYYMM.json` se particionan por mes.

## Subir este template
1. Crea un repo privado vacío en GitHub (p. ej. `juguitos-cloud`).
2. `git init` dentro de esta carpeta, agrega remoto y haz el primer push:
   ```bash
   git init
   git add .
   git commit -m "chore: seed repo structure"
   git branch -M main
   git remote add origin <URL-DEL-REPO>
   git push -u origin main
   ```
