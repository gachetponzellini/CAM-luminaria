# CAM luminarias — Presupuestador (Mockup)

Esta es una **maqueta funcional** del sistema de presupuestos para CAM luminarias.
No es la versión final: sirve para que **veas y toques** cómo funcionaría antes de
construir el producto real. Los **precios son de demostración**.

---

## ▶ Cómo abrirlo

1. Abrí la carpeta `CAM`.
2. Hacé **doble clic en `index.html`** (se abre en tu navegador: Chrome o Edge).
3. Listo. Funciona **sin internet** — todo está dentro de la carpeta.

> Para enviárselo a alguien, comprimí la carpeta `CAM` en un `.zip` y mandala completa
> (tiene que viajar junto a la subcarpeta `vendor`, que son las librerías que generan el
> PDF y el Excel).

---

## ¿Qué podés probar?

- **Cargar la cabecera:** cliente, teléfono, obra, vendedor, fecha y N° de presupuesto.
- **Buscar productos** en el catálogo (por código o descripción) y **filtrar por proveedor**.
- **Buscar productos por nombre** en un catálogo grande tipo galería.
- **Agregar productos** como un **carrito** (botón "+ Agregar"), con cantidades +/−.
- Definir el **markup del vendedor** (%): los precios de las listas son de **costo**, y el markup
  arma el precio de venta. Editable, se aplica sobre el costo. *(solo lo ve el vendedor)*
- **Elegir forma de pago** (efectivo −15%, transferencia −10% o lista) — el % lo **ajusta el vendedor**.
- Cargar **adelanto / seña** y ver el **saldo** automáticamente.
- Botón **"Cargar ejemplo"** para ver todo lleno de una.

### Precio en las tarjetas = COSTO
En el catálogo, cada tarjeta muestra el **precio de costo** (lo que te sale a vos). El
**markup** NO cambia las tarjetas: solo se aplica en el **carrito** para armar el precio
de venta del presupuesto. Así siempre tenés a la vista cuánto te cuesta cada cosa.

### ⬇ Exportar (descarga de 1 clic) — 4 opciones
La pantalla es tu herramienta interna (siempre ves costos, markup y ganancia). Lo que
cambia es **qué exportás**, según si es para el cliente o para vos:

- **PDF cliente:** presupuesto tipo *brochure* con portada CAM, **precios de venta**, sin
  marcas ni costos. Es lo que le mandás al cliente.
- **PDF interno:** mismo presupuesto pero con **costos, markup y ganancia** — para vos.
- **Excel cliente:** planilla simplificada (descripción, cantidad, precio, totales), sin marcas ni costos.
- **Excel interno:** planilla detallada (referencia marca+código, proveedor, costo, markup,
  precio de venta, totales y ganancia).

---

## Cómo se calcula el precio

Los precios de las listas son de **costo**. El **markup del vendedor** arma el precio de venta:

```
costo  = precio de lista del proveedor (con tu descuento de compra)
venta  = costo + markup del vendedor (%)
```

Después:
```
Subtotal neto  → + IVA (21%, configurable)  → Total c/IVA
              → − descuento por forma de pago  → Total a pagar
              → − adelanto/seña  → Saldo
```

Ejemplo con un producto IDEA (costo $145.600) y markup 100%:
`145.600 × 2,00 = 291.200` (precio de venta, sin IVA).

---

## Datos de muestra usados

- **IDEA:** productos con **códigos reales** de la lista N°95 (ej. `90.AB44.824150.01`),
  con sus atributos técnicos (W, temperatura de color, CRI, IP, voltaje, control).
- **CAM (fabricación propia):** cargados a mano, sin proveedor, con margen propio.
- **Artelum:** tercer proveedor, para mostrar la lógica multi-proveedor.

Los **valores de precio son inventados (demo)**. En el sistema real, los precios se cargan
subiendo el archivo del proveedor (Excel/PDF) y se actualizan todos juntos.

---

## Lo que NO incluye este mockup (queda para la versión real)

- **Importador automático** de listas de precios (PDF/Excel del proveedor).
- **Fotos / fichas técnicas** reales de cada producto (acá hay placeholders).
- **Facturación con ARCA** (segunda etapa del proyecto).
- **Guardado / historial** de presupuestos en la nube y usuarios.
- **Link interactivo** de solo lectura para mandarle al cliente.

---

## Archivos de la carpeta

```
CAM/
├─ index.html        ← la maqueta (abrí este archivo)
├─ README.md         ← este documento
└─ vendor/           ← librerías para PDF y Excel (no tocar)
   ├─ jspdf.umd.min.js
   ├─ jspdf.plugin.autotable.min.js
   └─ xlsx.full.min.js
```

> Documentación completa del proyecto (requisitos, decisiones, proveedores) en la wiki
> `CAM-BRAIN` (carpeta hermana).
