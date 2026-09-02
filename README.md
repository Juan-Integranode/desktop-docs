# Atajos para Arch Linux

Colección personal de comandos, atajos y notas rápidas para Arch Linux y otros programas que voy documentando en el día a día. El contenido está separado en dos carpetas según el tipo de tema, y cada uno vive en su propio archivo `.md`.

## Índice

### QuickArch — atajos propios de Arch Linux

| Tema | Descripción |
| --- | --- |
| [Comprobación de hash](./QuickArch/hash.md) | Verificar integridad de archivos con MD5 y SHA256 |
| [Pacman](./QuickArch/pacman.md) | Comandos esenciales del gestor de paquetes de Arch |

### Programas — herramientas y software externo

| Tema | Descripción |
| --- | --- |
| [Ventoy](./Programas/ventoy.md) | Crear y usar un USB de arranque múltiple |
| [USBGuard](./Programas/usbguard.md) | Permitir, bloquear y gestionar dispositivos USB |

### Nordic — herramientas de Nordic Semiconductor

| Tema | Descripción |
| --- | --- |
| [nRF Connect for Desktop](./Nordic/nrfconnectdesktop.md) | Cómo abrir el AppImage |
| [West](./Nordic/west.md) | Comandos de west: update, build y flash |

### Stm32 — build, flash y debug de proyectos STM32
 
| Tema | Descripción |
| --- | --- |
| [CMake](./Stm32/cmake.md) | Presets, build, permisos udev y flash |

### GIT - flujo de trabajo

| Tema | Descripción |
| --- | --- |
| [git cheat sheet](./Github/github.md) | flujo github,linear,commits |

## Estructura del repo

```
.
├── README.md            # Este índice
├── QuickArch/
│   ├── hash.md           # MD5 / SHA256
│   └── pacman.md         # Atajos de pacman
├── Programas/
│   ├── ventoy.md          # Ventoy
│   └── usbguard.md        # USBGuard
│── Nordic/
│      ├── nrfconnectdesktop.md  # nRF Connect for Desktop
│       └── west.md            # Comandos de west
│ 
│── Github/
│      └── github.md       #git cheat sheet  
│      
└── Stm32/
    └── cmake.md           # CMake: build, udev y flash

``` 

## Convenciones

- **QuickArch/** agrupa atajos y comandos propios del sistema Arch Linux (pacman, systemd, particiones, etc.).
- **Programas/** agrupa documentación de herramientas y software externo que no es exclusivo de Arch (Ventoy, y lo que se vaya sumando).
- Cada archivo agrupa comandos de una misma herramienta o tema.
- Los comandos van siempre en bloques de código con el lenguaje especificado (` ```bash `).
- Los valores a reemplazar (hashes, versiones, dispositivos) se marcan en `MAYÚSCULAS_CON_GUION_BAJO`, por ejemplo `HASH_CONOCIDO` o `/dev/sdX`.

---

*Última actualización: ver historial de commits.*