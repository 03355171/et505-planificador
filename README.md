# Planificador de materiales Guevara Sanchez

## Autor y propósito
- **Autor:** Mark Alexis Guevara Sanchez, estudiante de la Universidad Nacional Intercultural Fabiola Salazar Leguía de Bagua. ET505 · Semana 7 · Trabajo individual.
- **Sistema:** «Planificador de materiales Guevara Sanchez», primera versión de mi propio planificador de materiales educativos.
- **Actividad educativa (ficticia):** «Feria de las emociones», taller de convivencia escolar para 30 estudiantes ficticios de 1.º de secundaria, en 6 grupos de 5.
- **Qué hace:** organiza un pedido ficticio de material (material, cantidad, precio), calcula el total en céntimos enteros y comprueba que no supere el presupuesto del taller. Es una simulación: no hay compras, envíos ni base de datos.

## Cómo ejecutarlo
1. Extraiga el ZIP y conserve juntos `index.html`, `styles.css`, `app.js` y `README.md`.
2. Abra `index.html` en Chrome o Edge.
3. Para modificar: edite `app.js`, guarde con Ctrl + S y recargue con Ctrl + R.

## Organización de archivos
| Archivo | Responsabilidad |
|---|---|
| `index.html` | Pantalla: campos, botones, mensaje y zona del último pedido válido. |
| `styles.css` | Apariencia (sin cambios respecto de la plantilla). |
| `app.js` | **Datos y reglas** (objeto `limites`, `calcularTotal`, `validarPedido`; no usan `document`) y **pantalla** (`leerPedido` y las acciones de los botones). |
| `README.md` | Propósito, ejecución, personalización, pruebas y ayuda recibida. |

El objeto `pedido` agrupa `{material, cantidad, precio}`. El objeto `limites` agrupa `{presupuestoCentimos, maxCantidad, maxPrecio}`.

## Los tres cambios en app.js
1. **TODO 1 · `calcularTotal(pedido)`:** `return pedido.cantidad * Math.round(pedido.precio * 100);` Devuelve el total en céntimos enteros (S/ 5.00 × 10 = 5000 céntimos).
2. **TODO 2 · `validarPedido(pedido)`:** si el total supera `limites.presupuestoCentimos` devuelve «El total supera el presupuesto.»; si cumple devuelve `""`. Un total igual al presupuesto es válido.
3. **TODO 3 · botón Comprobar pedido:** `const error = validarPedido(pedido);` Usa la misma función que Confirmar simulación; hay una sola regla para los dos botones.

## Personalización
- **Nombre propio:** «Planificador de materiales Guevara Sanchez», en `<title>` y `<h1>`: conservé la base «Planificador de materiales» y le agregué mi apellido.
- **Actividad y material:** Feria de las emociones; ejemplo de material: papelógrafos.
- **Presupuesto propio:** **S/ 180.00 = 18000 céntimos** (`limites.presupuestoCentimos = 18000`). El texto visible de `index.html` dice S/ 180.00; ambos coinciden.
- **Justificación:** 6 grupos × S/ 30.00 por grupo = S/ 180.00. Está entre S/ 50 y S/ 300, es múltiplo de S/ 10 y es distinto de S/ 150.
- Se mantienen `maxCantidad:30` y `maxPrecio:50`.

## Pruebas con el presupuesto propio (S/ 180.00)
| # | Entrada | Esperado | Obtenido |
|---|---------|----------|----------|
| 1 | papelógrafos, 10 u., S/ 5.00 | Válido; total S/ 50.00 y saldo S/ 130.00 | Comprobar: «Pedido válido…». Confirmar: ficha con Total S/ 50.00 y Saldo S/ 130.00 |
| 2 | cantidad 2.5 / material vacío | Error, sin ficha nueva | «Cantidad: entero entre 1 y 30.» / «Escriba un material de al menos 3 caracteres.» (ambos botones) |
| 3 | papelógrafos, 10 u., S/ 18.00 | Total = presupuesto: válido, saldo S/ 0.00 | Comprobar: válido. Confirmar: Total S/ 180.00, Saldo S/ 0.00 |
| 4 | papelógrafos, 10 u., S/ 18.01 | Error por superar el presupuesto | «El total supera el presupuesto.» (ambos botones) |
| 5 | Confirmar válido (10 u., S/ 5.00), luego inválido (10 u., S/ 18.01), luego Limpiar | El error conserva la ficha; Limpiar la borra | Tras el error siguió la ficha de S/ 50.00; Limpiar la ocultó |

Capturas y detalle en el informe PDF.

## Mi aporte y ayuda recibida
- **Aporte:** completé los tres TODO, elegí y justifiqué el presupuesto de S/ 180.00, personalicé nombre, actividad y material, y registré las cinco pruebas.
- **Fallo detectado:** con la plantilla original, Comprobar mostraba «Complete TODO 3 en Comprobar.» y Confirmar mostraba «Complete TODO 1 en calcularTotal.». Después de completar los pendientes esos avisos desaparecieron.
- **Ayuda recibida:** usé el asistente de IA Claude (Anthropic) como apoyo para resolver algunas dudas y organizar el trabajo. Después yo, revisé el código y realicé pruebas para comprobar que funcionara correctamente.

## Repositorio y sitio web
Repositorio: [pegar aquí el enlace de mi repositorio]
Sitio publicado: [pegar aquí el enlace que GitHub Pages muestre]

Para publicar: Settings > Pages > Deploy from a branch > main > /(root) > Save. Use solo datos ficticios; no suba claves ni documentos personales.
