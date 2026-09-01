## Ventoy

Convierte cualquier USB en un sistema de arranque múltiple. Permite almacenar varias ISOs (según el espacio del pendrive) y usarlas para instalar distintos sistemas operativos en cualquier equipo. Se descarga desde la [página oficial](https://www.ventoy.net) y se recomienda comprobar el SHA256 antes de usarlo.

### Descomprimir el paquete descargado

```bash
tar -xvzf ventoy-VERSION-linux.tar.gz
cd ventoy-VERSION
```

### Instalar Ventoy vía interfaz web

```bash
./VentoyWeb.sh
```

Abrir en el navegador: `http://127.0.0.1:24680`



### Uso

Tras instalar, se crean dos particiones. Los archivos `.iso` deben copiarse dentro de la partición **Ventoy** (la grande, formateada como exFAT). No hace falta reformatear para agregar o quitar ISOs. 
```