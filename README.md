# Asistencia · Orientadores

Sistema de registro de asistencia con firma digital para reuniones de coordinación territorial de orientadores. Accesible desde cualquier dispositivo móvil escaneando un QR.

---

## Uso

### Coordinador/a (ordenador)

1. Abre [asistencia.rumbotools.com](https://asistencia.rumbotools.com) e introduce la contraseña
2. Rellena los datos de la reunión y pulsa **Iniciar reunión**

**Fase 1 · Asistencia**
Proyecta el QR. Los orientadores lo escanean con su móvil y registran su presencia. Cuando todos hayan llegado, pulsa **Cerrar asistencia**. Si alguien no puede escanear, usa **Añadir asistente manualmente**.

**Fase 2 · Firma**
Aparece un nuevo QR. Los orientadores lo escanean, buscan su nombre y firman con el dedo. Solo pueden firmar quienes registraron presencia en la fase anterior.

**Fase 3 · Acta**
Pulsa **Generar acta PDF** para descargar el documento con la lista completa y las firmas. Al terminar, pulsa **Nueva reunión** para limpiar los datos.

### Orientadores (móvil)

**Fase 1:** Escanear QR → rellenar nombre, apellidos, centro y agrupación → pulsar **Asistencia**

**Fase 2:** Escanear QR → escribir las primeras letras del nombre → seleccionar de la lista → firmar con el dedo → pulsar **Firmar**

---

## Seguridad

- **QR rotatorio:** el código cambia cada 5 segundos y caduca en 45. Una foto del QR queda inutilizable casi de inmediato.
- **Un solo uso por dispositivo:** cada móvil solo puede registrar presencia una vez por sesión.
- **Firma de un solo uso:** al seleccionar un nombre para firmar queda bloqueado para otros dispositivos.
- **Sesión diaria:** la contraseña del panel debe introducirse cada día.
- **Cierre manual:** al pulsar "Cerrar asistencia" el QR de presencia queda invalidado.

---

## Privacidad y protección de datos

Los datos recogidos son: nombre, apellidos, centro, agrupación y firma manuscrita digitalizada.

- Los datos se recogen exclusivamente para acreditar la asistencia a la reunión.
- La firma se almacena cifrada con AES-256 y nunca se transmite en texto plano.
- Los datos se eliminan al iniciar una nueva reunión mediante el botón **Nueva reunión**.
- No se ceden datos a terceros ni se usan con ninguna otra finalidad.
- El almacenamiento se realiza en servidores de Supabase en la región de París (UE), bajo legislación europea de protección de datos.
- Los orientadores son informados del tratamiento de sus datos y prestan consentimiento explícito antes de registrarse.

---

## Cambiar la contraseña

1. Ve a [emn178.github.io/online-tools/sha256.html](https://emn178.github.io/online-tools/sha256.html)
2. Escribe la nueva contraseña y copia el hash generado
3. Abre `index.html`, localiza la línea `const PASS_HASH` y sustituye el hash
4. Sube el archivo a GitHub

---

## Archivos

| Archivo | Descripción |
|---|---|
| `index.html` | Aplicación completa |
| `README.md` | Este documento |
