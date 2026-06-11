# Sistema Inteligente de Auditoría de Costos y Compras para Droguerías 💊📊

Este repositorio contiene la solución desarrollada para el **Proyecto 1 del Reto AI Academy de Platzi: Multiplica 10x tu impacto profesional**. El sistema automatiza el análisis de ofertas comerciales de laboratorios farmacéuticos mediante ingeniería de prompts avanzada.

---

## 🛒 El Problema en la Gestión de Compras de Distribución

En el día a día de una droguería, la toma de decisiones de compras enfrenta tres fricciones críticas que impactan directamente el margen de ganancia:

1. **Estructuras de Descuentos Complejas:** Las farmacéuticas envían ofertas en USD con múltiples descuentos en cascada (Pronto pago, volumen, ofertas tipo 10+1, bonificaciones). Calcular el **Costo Neto Real** de forma manual consume tiempo y es propenso a errores.
2. **Saturación de Principios Activos (Variedad vs. Rotación):** Riesgo de sobre-estoquearse comprando marcas comerciales duplicadas para un mismo componente (ej. manejar 5 tipos de Acetaminofén) sin evaluar la rotabilidad real en almacén.
3. **Soporte de Decisiones:** La Encargada de Compras necesita visibilidad inmediata de qué ofertas representan una *Oportunidad de Margen* real sin perder el control del stock.

---

## 🏗️ Arquitectura del Sistema (Flujo Modular en 3 Pasos)

Para garantizar la precisión y evitar alucinaciones, el sistema utiliza la metodología **Chain of Thought (Cadena de Pensamiento)**, dividiendo la lógica en tres eslabones donde la salida de uno alimenta al siguiente.

### 📋 PASO 1: El Extractor y Analista de Descuentos
* **Rol:** Asistente Operativo de Compras Farmacéuticas.
* **Objetivo:** Limpiar el listado bruto de la farmacéutica, homologar los productos por principio activo/concentración y desglosar la estructura de descuentos comerciales en USD.

### 📊 PASO 2: El Calculador de Costo Neto Real y Auditor de Margen
* **Rol:** Analista Financiero de Costos para Droguería.
* **Objetivo:** Aplicar matemáticamente los descuentos en cascada o bonificaciones de forma sucesiva sobre el costo de lista, determinando el ahorro real y comparándolo con el histórico de nuestro sistema interno.

### 👩‍💼 PASO 3: El Consultor de Oportunidades (Soporte de Decisiones)
* **Rol:** Consultor Estratégico de Inventario Farmacéutico.
* **Objetivo:** Cruzar los días de stock actuales y la venta mensual con el nuevo costo neto real. Genera alertas de saturación de marcas y resalta oportunidades de inversión agresivas si el margen mejora drásticamente.

---

## ⚡ Versión Consolidada para Producción Diaria

Para eliminar la fricción de copiar y pegar múltiples bloques de texto, se compilaron las tres fases en un **Único Prompt de Ejecución Continua**. Al cargarlo en el asistente de IA, el sistema queda automatizado para procesar cualquier oferta de forma sucesiva.

🤖 SISTEMA DE AUDITORÍA DE COSTOS Y COMPRAS - DROGUERÍA

Rol: Analista Inteligente de Compras y Costos para Distribución Farmacéutica.
Instrucciones permanentes para la conversación:
Cada vez que te suministre la oferta en USD de un laboratorio farmacéutico, sus condiciones de descuento y el estado actual de mi inventario, debes procesar el flujo internamente y devolver de forma inmediata un análisis financiero estructurado en formato de Tabla Markdown para mi Excel.

La tabla debe calcular obligatoriamente:
1. Costo Neto Real (USD): El valor unitario final tras aplicar consecutivamente todos los descuentos (pronto pago, volumen, bonificaciones).
2. Variación %: Cuánto baja o sube el costo respecto a nuestro sistema interno.
3. Análisis de Oportunidad: Cruzar los días de stock (Stock / Venta Mensual * 30) con el descuento. Si el stock es bajo, sugiere la compra de reposición. Si el stock es alto pero el descuento mejora el costo en $>10\%$, catalogarlo como "Oportunidad de Margen". Si el principio activo ya tiene demasiada variedad en stock, alertar "Saturación de Componente".

Estructura de la Tabla de Salida:
| Principio Activo | Laboratorio / Producto | Costo Lista (USD) | Costo Neto Real (USD) | Variación Costo (%) | Días Stock | Recomendación Analítica |Al final de la tabla, genera un bloque breve titulado: "💡 Sugerencias Estratégicas para la Encargada de Compras".


🚀 Caso de Éxito (Demostración de Salida)
📥 Entrada Suministrada por el Usuario:

Laboratorio: PharmaVida
Oferta: Acetaminofén 500mg (Caja de 100 tab). Costo lista: $12.00. 
Condiciones: 10% descuento por volumen + 5% por pronto pago. 
Inventario actual en droguería: Stock: 150 cajas | Venta mensual: 300 cajas.
Marcas similares en stock: 4 marcas activas.
Costo anterior en sistema: $10.50 | Nuestro PVP actual a farmacias: $15.00

📤 Respuesta Automatizada del Sistema (Vista en Excel/Notion):

<img width="1280" height="72" alt="image" src="https://github.com/user-attachments/assets/290a1cab-b712-4ed8-a166-87f72288e05a" />


💡 Sugerencias Estratégicas para la Encargada de Compras:
Alerta de Variedad: Actualmente manejamos 4 marcas de Acetaminofén. Sin embargo, debido a que el stock actual solo cubre 15 días y el costo neto de PharmaVida ($10.26) mejora nuestro costo anterior ($10.50), se recomienda proceder con la compra de este lote para reponer inventario y expandir el margen de ganancia al venderlo a nuestro PVP actual ($15.00).

Desarrollado con 💙 para el Reto AI Academy de Platzi.

"Tecnologías y Metodologías Utilizadas"

> Ingeniería de Prompts (Prompt Engineering)

> Modelos de Lenguaje (LLMs) aplicados a negocios

> Optimización de la cadena de suministro farmacéutica
