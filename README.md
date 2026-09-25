# Asistencia · Orientadores

Sistema de registro de asistencia a reuniones de coordinación territorial de orientadores. Funciona en dos fases: primero los orientadores registran su presencia escaneando un QR rotatorio, y después firman desde su móvil con un segundo QR.

---

## Cómo usarlo

### La coordinadora (desde el ordenador)

1. Abre [https://santiagocapo.github.io/asistencia/](https://santiagocapo.github.io/asistencia/)
2. Introduce la contraseña
3. Rellena los datos de la reunión y pulsa **Iniciar reunión**

**Fase 1 — Asistencia**
- Se proyecta un QR que cambia automáticamente cada 5 segundos
- Los orientadores lo escanean con su móvil y rellenan sus datos
- Se pueden añadir asistentes manualmente con el botón **Añadir manualmente**
- Cuando todos hayan llegado, pulsa **Cerrar asistencia**

**Fase 2 — Firma**
- Aparece un nuevo QR fijo que puedes mostrar en pantalla o enviar por el grupo de WhatsApp
- Solo pueden firmar quienes registraron su presencia en la Fase 1
- Cada nombre solo puede usarse una vez para firmar

**Fase 3 — Acta**
- Pulsa **Generar acta PDF** para descargar el documento con la lista y las firmas
- Al terminar, pulsa **Nueva reunión** para limpiar todo

---

### Los orientadores (desde el móvil)

**Fase 1:**
1. Escanear el QR proyectado en la sala
2. Rellenar nombre, apellidos, centro y agrupación
3. Pulsar **Asistencia**

**Fase 2:**
1. Escanear el nuevo QR (proyectado o recibido por WhatsApp)
2. Escribir las primeras letras del nombre y seleccionarlo de la lista
3. Firmar con el dedo
4. Pulsar **Firmar**

---

## Seguridad

- **QR rotatorio:** el código cambia cada 5 segundos y caduca en 15. Una foto del QR deja de funcionar casi de inmediato.
- **Un solo uso por dispositivo:** cada móvil solo puede registrar presencia una vez por sesión.
- **Firma de un solo uso por nombre:** una vez seleccionado un nombre para firmar, queda bloqueado para otros dispositivos.
- **Sesión ligada al día:** la contraseña de coordinadora debe introducirse cada día.
- **Cierre manual:** al pulsar "Cerrar asistencia", el QR de presencia queda invalidado aunque alguien lo tenga guardado.

---

## Contraseña de acceso

La contraseña por defecto es **`admin`**.

Para cambiarla:
1. Ve a [https://emn178.github.io/online-tools/sha256.html](https://emn178.github.io/online-tools/sha256.html)
2. Escribe tu nueva contraseña y copia el hash generado
3. Abre `index.html` con el Bloc de notas
4. Busca la línea `const PASS_HASH = '...'` y sustituye el hash
5. Guarda y sube el archivo a GitHub

---

## Archivos

| Archivo | Descripción |
|---|---|
| `index.html` | Aplicación completa (coordinadora + móvil fase 1 + móvil fase 2) |
| `README.md` | Este documento |

---

## Notas técnicas

- Los datos se almacenan en [JSONBin.io](https://jsonbin.io) (bin privado, acceso solo con API key)
- El QR rotatorio usa TOTP (el mismo algoritmo del doble factor de autenticación) implementado con la API nativa del navegador, sin librerías externas
- No se requiere instalación ni servidor propio
- Funciona desde cualquier navegador y cualquier red (WiFi corporativa, datos móviles, WiFi abierta)
