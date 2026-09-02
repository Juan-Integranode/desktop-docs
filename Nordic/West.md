# West

Herramienta de línea de comandos de Zephyr/nRF Connect SDK para gestionar el workspace, compilar y flashear proyectos.

## Ver versión instalada

```bash
west --version
```

## Actualizar módulos del workspace

Sincroniza los repositorios/submódulos del proyecto según `west.yml`:

```bash
west update
```

## Compilar el proyecto (limpiando build previo)

`-p always` fuerza a borrar y regenerar la carpeta `build/` antes de compilar — útil para evitar builds corruptos por caché:

```bash
west build -p always -b nrf9151dk/nrf9151/ns
```

> Reemplazar `nrf9151dk/nrf9151/ns` por la placa/target correspondiente si se trabaja con otro modelo.

## Flashear el dispositivo

Sube el binario compilado a la placa conectada:

```bash
west flash
```

## Flujo típico

1. `west update` — traer cambios del workspace (solo si cambiaron dependencias/manifest).
2. `west build -p always -b nrf9151dk/nrf9151/ns` — compilar desde cero.
3. `west flash` — grabar el firmware en la placa.