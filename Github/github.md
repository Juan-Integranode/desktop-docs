
# IntegraNode Git Cheat Sheet
 
Flujo de trabajo oficial: **Linear → GitHub**
 
## Setup inicial (única vez)
 
**Paso 1:** descargar el repo (clone) o inicializarlo si arrancás con código local.
 
**Paso 2:** configurar tu identidad corporativa siempre antes de commitear.
 
**Opción A — Bajar repo existente (recomendado)**
 
```bash
git clone https://github.com/integra-node/repo.git
cd repo
```
 
**Opción B — Iniciar desde código local**
 
```bash
git init
git remote add origin https://github.com/integra-node/repo.git
```
 
**⚠️ Crítico: configurar identidad (correr en ambos casos)**
 
```bash
git config user.name "Tu Nombre"
git config user.email "tu.nombre@integranode.com"
```
 
---
 
## Flujo diario (Linear)
 
**1. Copiar rama desde Linear**
 
Botón "Copy branch name" o `Ctrl/Cmd + Shift + .`
 
```bash
git switch -c NOMBRE_DE_RAMA
```
 
**2. Agregar archivos permitidos** (revisar `.gitignore`)
 
```bash
git add .
```
 
**3. Commit** (ver reglas en la sección siguiente)
 
```bash
git commit -m "..."
```
 
**4. Subir a GitHub** (la primera vez en esa rama)
 
```bash
git push -u origin NOMBRE_DE_RAMA
```
 
---
 
## Convención de commits
 
```text
tipo: [ID] descripción
```
 
Ejemplo: `chore: [INT1-122] config inicial`
 
| Emoji | Tipo | Uso |
| --- | --- | --- |
| ✨ | `feat:` | Nueva funcionalidad (ej. sensor) |
| 🐛 | `fix:` | Arreglo de bug / error |
| 🔧 | `chore:` | Mantenimiento (`.gitignore`, config) |
| ♻️ | `refactor:` | Mejora de código interno |
 
---
 
## Definition of Done (DoD)
 
**🚨 Regla de oro (STM32):** verificar con `git status` que la carpeta `build/` y los binarios **no** se estén subiendo.
 
**Validar autoría local**
 
```bash
git config --list --local
```
 
**Validar rama actual**
 
```bash
git branch --show-current
```
 
**Ver info del último commit**
 
```bash
git log -1
```
 
---
 
## Configuración SSH (GitHub)
 
**1. Generar nueva clave SSH**
 
Crea un par de llaves usando criptografía Ed25519 con tu correo corporativo:
 
```bash
ssh-keygen -t ed25519 -C "tu.nombre@integranode.com"
```
 
**2. Obtener clave pública para GitHub**
 
Copiar la salida completa y pegarla en los ajustes de llave SSH de la cuenta de GitHub:
 
```bash
cat /root/.ssh/id_ed25519.pub
```
 
> Si estás en tu terminal local, fuera del contenedor, usá: `cat ~/.ssh/id_ed25519.pub`
 
iniciar agente 

```bash
eval "$(ssh-agent -s)"
```

Agregar clave publica a la memoria 
```bash
ssh-add ~/.ssh/id_ed25519_github
```

---
 
## 🚨 Salvavidas / Modificar historial
 
**Modificar el último commit (amend)**
 
Agrega archivos olvidados con `git add` o corrige el mensaje del último commit:
 
```bash
git commit --amend
```
 
**Sacar un archivo del último commit**
 
Remueve un archivo agregado por error sin borrar su contenido local:
 
```bash
git reset HEAD~1 ruta/al/archivo
```
 
Para revertir de *staging* antes de commitear:
 
```bash
git restore --staged archivo
```
 
**Forzar push (tras modificar historial)**
 
Obligatorio para subir cambios tras un `amend` en una rama que ya está en GitHub:
 
```bash
git push --force
```
 
Alternativa segura:
 
```bash
git push --force-with-lease
```
 
---
