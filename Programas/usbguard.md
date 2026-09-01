# USBGuard

Ayuda a proteger la computadora contra dispositivos USB maliciosos mediante listas blancas y negras basadas en los atributos del dispositivo (ID, serial, nombre, hash).

## Ver dispositivos conectados

Lista los dispositivos USB detectados actualmente, con su `id` y demás atributos:

```bash
usbguard list-devices
```

## Ver reglas activas

Muestra las reglas cargadas (equivalente a inspeccionar `/etc/usbguard/rules.conf` en caliente):

```bash
usbguard list-rules
```

## Permitir un dispositivo (temporal)

Autoriza el dispositivo mientras dure la sesión actual del daemon. Se pierde al reiniciar el servicio.

```bash
usbguard allow-device ID
```

## Permitir un dispositivo (permanente)

Autoriza el dispositivo y lo agrega como regla persistente en `rules.conf`:

```bash
usbguard allow-device ID -p
```

## Bloquear un dispositivo

Bloquea el dispositivo sin rechazarlo activamente (queda "a la espera"):

```bash
usbguard block-device ID
```

## Rechazar un dispositivo

Rechaza el dispositivo de forma explícita (expulsa la conexión):

```bash
usbguard reject-device ID
```

> El `ID` se obtiene de la primera columna de `usbguard list-devices`, por ejemplo `1`, `2`, etc. (es un identificador de sesión, no el `id 0781:55a3` del dispositivo).

## Agregar un dispositivo manualmente a la lista blanca

Editar el archivo de reglas:

```bash
sudo nano /etc/usbguard/rules.conf
```

Agregar una línea con los datos del dispositivo (los obtenés de `list-devices`), por ejemplo:

```text
allow id 0781:55a3 serial "NUMERO_DE_SERIE" name "SanDisk 3.2Gen1" hash "HASH_DEL_DISPOSITIVO"
```

## Quitar un dispositivo de la lista blanca

Editar `rules.conf` y borrar (o comentar con `#`) la línea correspondiente a ese dispositivo:

```bash
sudo nano /etc/usbguard/rules.conf
```

## Recargar las reglas sin reiniciar el equipo

Después de editar `rules.conf` a mano, reiniciar el servicio para que tome los cambios:

```bash
sudo systemctl restart usbguard.service
```

## Flujo típico al conectar una placa nueva

1. Conectar el dispositivo (queda bloqueado por defecto si la política es `block`).
2. Ver su `ID` de sesión: `usbguard list-devices`
3. Probarlo primero de forma temporal: `usbguard allow-device ID`
4. Si funciona bien y se va a usar seguido, hacerlo permanente: `usbguard allow-device ID -p`