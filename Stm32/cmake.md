# CMake (STM32)

Comandos de día a día para configurar, compilar y flashear proyectos STM32 con CMake presets.

## Configurar el preset

```bash
cmake --preset Debug
```

## Compilar (build)

Limpia el target antes de compilar:

```bash
cmake --build --preset Debug --target clean
```

## Previo a flashear por primera vez

Antes del primer flasheo hay que autorizar la placa:

1. **Autorizar en USBGuard** — ver [Programas/usbguard.md](../Programas/usbguard.md) (`usbguard list-devices` + `usbguard allow-device ID -p`).
2. **Dar permisos udev** a la placa:

```bash
sudo nano /etc/udev/rules.d/99-nucleo-f439zi.rules
```

Recargar las reglas para que tomen efecto sin reiniciar:

```bash
sudo udevadm control --reload-rules && sudo udevadm trigger
```

## Flash

```bash
STM32_Programmer_CLI -c port=SWD mode=UR -w build/Debug/Prueba.elf -v -rst
```

> Reemplazar `build/Debug/Prueba.elf` por la ruta y nombre del `.elf` generado en cada proyecto.

## Debug

_Pendiente: agregar comando/flujo de debug (ej. GDB + OpenOCD, Cortex-Debug en VS Code, o STM32CubeIDE)._