# Proyecto Northwind PostgreSQL - Modificado

Este repositorio contiene una versión modificada de la base de datos Northwind para PostgreSQL, desarrollada como proyecto de curso con nuevas funcionalidades y mejoras.

## 📋 Descripción del Proyecto

Este proyecto consiste en la modificación de la base de datos Northwind, una base de datos de ejemplo comúnmente utilizada para prácticas de SQL. El objetivo es personalizar la tabla products, poblarla con nuevos registros y generar una copia de seguridad de la base de datos modificada.

### ✨  Modificaciones realizadas

En este proyecto he realizado las siguientes modificaciones a la base de datos Northwind original:

Tabla products:

Añadí una nueva columna llamada expiration_date para registrar la fecha de caducidad de cada producto.

Cambié el tipo de la columna discontinued de integer a boolean para mejorar la legibilidad y el manejo de valores lógicos.

Poblé la tabla con múltiples registros nuevos, representando productos variados (aceite, café, té, vino, quesos, etc.) con datos realistas y completos.

Gestión de product_id:

Asigné manualmente los valores de product_id en las inserciones, asegurando que no se repitan y respetando la integridad de la clave primaria.

Backup de la base de datos:

Realicé un volcado (pg_dump) de la base de datos modificada para preservar los cambios y facilitar la restauración o migración.
## 🛠️ Tecnologías

- **PostgreSQL** 12+ 
- **pgAdmin** (opcional)
- **SQL Dump** para instalación rápidA
- **Github**

## 📁 Estructura del Repositorio

```
northwind-modificado/
├── README_original                          # Este archivo
├── northwind_modificado.sql           # ⭐ DUMP COMPLETO DE LA BD
├── img/
└── screenshots/
    ├── diagrama_er.png                # Diagrama actualizado
    └── consultas_ejemplo.png          # Capturas de pantalla
```

## 🚀 Instalación Rápida

### Prerrequisitos
- PostgreSQL 12 o superior
- Cliente psql o pgAdmin

### Instalación en 3 pasos

1. **Clonar repositorio**
```bash
git clone https://github.com/mouhamadou272/northwind-modificado
cd northwind-modificado
```

2. **Crear base de datos**
```bash
createdb northwind_modificado
```

3. **Restaurar dump completo**
```bash
psql -d northwind_curso -f northwind_modificado.sql
```

¡Y listo! La base de datos estará completamente configurada con datos de ejemplo.


## 🔍 Funcionalidades Principales

### 1. Control de Stock Inteligente
```sql
-- Ver productos con stock bajo
SELECT * FROM productos_stock_bajo;
```

### 2. Análisis de Ventas
```sql
-- Ventas por mes con métricas
SELECT * FROM ventas_mensuales 
WHERE mes >= '2024-01-01';
```

### 3. Sistema de Descuentos
```sql
-- Calcular descuento por volumen
SELECT calcular_descuento_volumen(1, 75) as descuento_aplicado;
```

### 4. Top Productos
```sql
-- Productos más vendidos
SELECT * FROM top_productos_vendidos LIMIT 10;
```

## 📊 Nuevas Tablas Añadidas

- `subcategories` - Categorías jerárquicas
- `volume_discounts` - Descuentos por cantidad
- `product_audit` - Auditoría de cambios
- `stock_alerts` - Alertas de inventario

## 📈 Vistas Creadas

- `productos_stock_bajo` - Control de inventario
- `ventas_mensuales` - Análisis temporal
- `top_productos_vendidos` - Ranking de productos
- `analisis_clientes` - Segmentación de clientes



## 📋 Especificaciones Técnicas

- **Versión PostgreSQL**: 17.5
- **Tamaño del dump**: ~500KB
- **Total tablas**: 17 (13 originales + 4 nuevas)
- **Total vistas**: 4
- **Total funciones**: 3

## 👨‍🎓 Información Académica

- **Curso**: Bases de Datos Avanzadas
- **Institución**: [Urko]
- **Autor**: [Mouhamdou Bachir Seck ]
- **Fecha**: junio 2025

