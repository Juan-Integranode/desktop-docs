# Atajos para Arch linux

## Comprobacion de HASH 

### Md5

#### Obtener hash md5 de un archivo 
```bash
md5sum archivo.ext
```
#### Comparar el hash con un archivo  
```bash
echo "HASH_CONOCIDO  archivo.ext" | md5sum -c -
```
### SHA256

#### Obtener hash md5 de un archivo 
```bash
sha256sum archivo.ext
```
#### Comparar el hash con un archivo  
```bash
echo "HASH_CONOCIDO  archivo.ext" | sha256sum -c -
```
