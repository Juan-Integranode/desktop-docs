## Pacman

### Instalar un paquete

```bash
sudo pacman -S paquete
```

### Eliminar un paquete

```bash
sudo pacman -R paquete
```

### Eliminar un paquete y sus dependencias no usadas

```bash
sudo pacman -Rns paquete
```

### Actualizar todo el sistema

```bash
sudo pacman -Syu
```

### Sincronizar la base de datos de paquetes (sin actualizar)

```bash
sudo pacman -Sy
```

### Buscar un paquete en los repositorios

```bash
pacman -Ss nombre
```

### Buscar un paquete ya instalado

```bash
pacman -Qs nombre
```

### Ver información de un paquete

```bash
pacman -Si paquete
```

### Ver información de un paquete instalado

```bash
pacman -Qi paquete
```

### Listar todos los paquetes instalados

```bash
pacman -Q
```

### Listar paquetes instalados manualmente (no como dependencia)

```bash
pacman -Qe
```

### Listar paquetes huérfanos (instalados como dependencia y ya no usados)

```bash
pacman -Qdt
```

### Eliminar todos los paquetes huérfanos

```bash
sudo pacman -Rns $(pacman -Qtdq)
```

### Ver qué paquete provee un archivo

```bash
pacman -Qo /ruta/al/archivo
```

### Ver qué archivos instaló un paquete

```bash
pacman -Ql paquete
```

### Limpiar la caché de paquetes descargados

```bash
sudo pacman -Sc
```

### Limpiar toda la caché (incluso versiones actuales)

```bash
sudo pacman -Scc
```

### Instalar un paquete local (.pkg.tar.zst)

```bash
sudo pacman -U paquete.pkg.tar.zst
```

### Ver el log de pacman

```bash
cat /var/log/pacman.log