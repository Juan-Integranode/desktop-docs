# Atajos para Arch Linux
 
Colección personal de comandos, atajos y notas rápidas para Arch Linux y otros programas que voy documentando en el día a día. El contenido está separado en dos carpetas según el tipo de tema, y cada uno vive en su propio archivo `.md`.
 
## Índice
 
### QuickArch — atajos propios de Arch Linux
 
| Tema | Descripción |
| --- | --- |
| [Comprobación de hash](./QuickArch/Hash.md) | Verificar integridad de archivos con MD5 y SHA256 |
| [Pacman](./QuickArch/Pacman.md) | Comandos esenciales del gestor de paquetes de Arch |
 
### Programas — herramientas y software externo
 
| Tema | Descripción |
| --- | --- |
| [Ventoy](./Programas/Ventoy.md) | Crear y usar un USB de arranque múltiple |
 
## Estructura del repo
 
```
.
├── README.md            # Este índice
├── QuickArch/
│   ├── hash.md           # MD5 / SHA256
│   └── pacman.md         # Atajos de pacman
└── Programas/
    └── ventoy.md          # Ventoy
```
 
## Convenciones
 
- **QuickArch/** agrupa atajos y comandos propios del sistema Arch Linux (pacman, systemd, particiones, etc.).
- **Programas/** agrupa documentación de herramientas y software externo que no es exclusivo de Arch (Ventoy, y lo que se vaya sumando).
- Cada archivo agrupa comandos de una misma herramienta o tema.
- Los comandos van siempre en bloques de código con el lenguaje especificado (` ```bash `).
- Los valores a reemplazar (hashes, versiones, dispositivos) se marcan en `MAYÚSCULAS_CON_GUION_BAJO`, por ejemplo `HASH_CONOCIDO` o `/dev/sdX`.