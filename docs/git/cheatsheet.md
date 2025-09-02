# 🚀 Git Cheat Sheet - Referencia Rápida

## 📋 Configuración Inicial

```bash
git config --global user.name "Tu Nombre"              # Configurar nombre
git config --global user.email "email@example.com"     # Configurar email
git config --global core.editor "code --wait"          # Editor por defecto
git config --list                                      # Ver configuración
```

## 🏁 Iniciar un Proyecto

```bash
git init                                   # Inicializar repositorio nuevo
git clone [url]                           # Clonar repositorio existente
git clone [url] [nombre-carpeta]          # Clonar con nombre específico
```

## 📝 Cambios Básicos

```bash
git status                                 # Ver estado actual
git status -s                              # Estado resumido

git add [archivo]                          # Agregar archivo específico
git add .                                  # Agregar todos los cambios
git add *.js                              # Agregar por patrón
git add -p                                # Agregar interactivamente

git commit -m "mensaje"                    # Commit con mensaje
git commit -am "mensaje"                   # Add + commit (solo tracked)
git commit --amend                        # Modificar último commit
```

## 🔍 Inspección y Comparación

```bash
git log                                    # Ver historial
git log --oneline                         # Historial resumido
git log --graph --all                     # Historial con gráfico
git log -p -2                             # Ver últimos 2 commits con cambios
git log --since="2 weeks ago"             # Commits de las últimas 2 semanas

git diff                                   # Cambios no staged
git diff --staged                          # Cambios en staging
git diff [branch1]..[branch2]             # Diferencias entre ramas
git diff HEAD~2                           # Comparar con 2 commits atrás

git show [commit]                          # Ver un commit específico
git blame [archivo]                        # Ver quién modificó cada línea
```

## 🌿 Ramas (Branches)

```bash
git branch                                 # Listar ramas locales
git branch -a                              # Listar todas las ramas
git branch [nombre]                        # Crear rama
git branch -d [nombre]                     # Eliminar rama (mergeada)
git branch -D [nombre]                     # Forzar eliminación de rama

git checkout [rama]                        # Cambiar a rama
git checkout -b [rama]                     # Crear y cambiar a rama
git switch [rama]                          # Cambiar rama (nuevo comando)
git switch -c [rama]                       # Crear y cambiar (nuevo comando)

git merge [rama]                           # Fusionar rama actual con otra
git merge --abort                          # Abortar merge en conflicto
```

## ↩️ Deshacer Cambios

```bash
git restore [archivo]                      # Descartar cambios (working)
git restore --staged [archivo]             # Unstage archivo
git checkout -- [archivo]                  # Descartar cambios (antiguo)

git reset [archivo]                        # Unstage archivo
git reset --soft HEAD~1                    # Deshacer commit (mantener cambios)
git reset --mixed HEAD~1                   # Deshacer commit y unstage
git reset --hard HEAD~1                    # Deshacer commit y cambios

git revert [commit]                        # Revertir commit (crear nuevo)
git clean -fd                              # Eliminar archivos no tracked
```

## 📡 Remotos

```bash
git remote -v                              # Ver remotos
git remote add [nombre] [url]             # Agregar remoto
git remote remove [nombre]                 # Eliminar remoto
git remote rename [viejo] [nuevo]          # Renombrar remoto

git fetch [remoto]                         # Descargar cambios
git fetch --all                            # Descargar de todos los remotos

git pull                                   # Fetch + merge
git pull --rebase                          # Fetch + rebase
git pull [remoto] [rama]                   # Pull específico

git push                                   # Subir cambios
git push [remoto] [rama]                   # Push específico
git push -u origin [rama]                  # Push y establecer upstream
git push --force                           # Forzar push (¡cuidado!)
git push --tags                            # Subir tags
```

## 🏷️ Tags

```bash
git tag                                    # Listar tags
git tag [nombre]                           # Crear tag ligero
git tag -a [nombre] -m "mensaje"          # Crear tag anotado
git tag -d [nombre]                        # Eliminar tag local
git push origin --delete [tag]             # Eliminar tag remoto
git show [tag]                             # Ver información del tag
```

## 💾 Stash (Guardado Temporal)

```bash
git stash                                  # Guardar cambios temporalmente
git stash save "mensaje"                   # Stash con descripción
git stash list                             # Ver stashes
git stash pop                              # Aplicar y eliminar último stash
git stash apply                            # Aplicar sin eliminar
git stash apply stash@{2}                  # Aplicar stash específico
git stash drop                             # Eliminar último stash
git stash clear                            # Eliminar todos los stashes
```

## 🔄 Rebase

```bash
git rebase [rama]                          # Rebase con otra rama
git rebase -i HEAD~3                       # Rebase interactivo últimos 3
git rebase --continue                      # Continuar después de resolver
git rebase --abort                         # Abortar rebase
```

## 🍒 Cherry-pick

```bash
git cherry-pick [commit]                   # Aplicar commit específico
git cherry-pick [commit1] [commit2]        # Múltiples commits
git cherry-pick --continue                 # Continuar después de conflicto
git cherry-pick --abort                    # Abortar cherry-pick
```

## 📊 Información Útil

```bash
git shortlog -sn                           # Contribuidores por commits
git log --pretty=format:"%h - %an, %ar : %s"  # Formato personalizado
git log --author="nombre"                  # Commits de un autor
git log --grep="texto"                     # Buscar en mensajes
git log -S "texto"                         # Buscar en cambios de código

git reflog                                 # Historial de referencias
git ls-files                               # Archivos tracked
git cat-file -p [hash]                     # Ver contenido de objeto
```

## 🆘 Comandos de Emergencia

```bash
# "Deshice algo que no debía"
git reflog                                 # Ver todo lo que has hecho
git reset --hard [hash-del-reflog]        # Volver a ese punto

# "Necesito cambiar el último commit"
git commit --amend -m "nuevo mensaje"      # Cambiar mensaje
git add [archivo]                          # Agregar archivo olvidado
git commit --amend --no-edit              # Agregar sin cambiar mensaje

# "Estoy en medio de un merge complicado"
git merge --abort                          # Cancelar merge

# "Quiero empezar de nuevo con un archivo"
git checkout HEAD -- [archivo]             # Restaurar archivo

# "Cometí cambios en la rama equivocada"
git stash                                  # Guardar cambios
git checkout [rama-correcta]              # Cambiar rama
git stash pop                              # Recuperar cambios

# "Quiero deshacer un push"
git revert [commit]                        # Crear commit que deshace
# O si nadie más ha pulled:
git reset --hard HEAD~1                    # Deshacer localmente
git push --force                           # Forzar push
```

## 🎯 Alias Útiles (Agregar a ~/.gitconfig)

```bash
[alias]
    st = status -s
    co = checkout
    br = branch
    cm = commit
    df = diff
    lg = log --oneline --graph --all
    last = log -1 HEAD
    unstage = reset HEAD --
    undo = reset --soft HEAD~1
    amend = commit --amend --no-edit
    who = shortlog -sn
    contrib = ! "git log --pretty=format:'%an' | sort | uniq -c | sort -rn"
```

## 🚦 Flujo de Trabajo Típico

```bash
# 1. Actualizar tu rama
git pull origin main

# 2. Crear rama para feature
git checkout -b feature/nueva-funcionalidad

# 3. Hacer cambios y commits
git add .
git commit -m "feat: agregar nueva funcionalidad"

# 4. Mantener rama actualizada
git fetch origin
git rebase origin/main

# 5. Subir rama
git push -u origin feature/nueva-funcionalidad

# 6. Crear Pull Request (en GitHub/GitLab)

# 7. Después del merge, limpiar
git checkout main
git pull origin main
git branch -d feature/nueva-funcionalidad
```

## 📝 Plantilla de Mensaje de Commit

```
<tipo>(<alcance>): <asunto>

<cuerpo>

<pie>

# Tipos: feat, fix, docs, style, refactor, test, chore
# Ejemplo:
# feat(auth): agregar autenticación con JWT
#
# Implementar sistema completo de autenticación usando
# tokens JWT con refresh tokens.
#
# Closes #123
```

## 🎨 Símbolos para Commits (Gitmoji)

```
🎨 :art:                # Mejorar estructura/formato
⚡️ :zap:                # Mejorar performance
🔥 :fire:               # Eliminar código/archivos
🐛 :bug:                # Corregir bug
🚑 :ambulance:          # Hotfix crítico
✨ :sparkles:           # Nueva funcionalidad
📝 :memo:               # Documentación
🚀 :rocket:             # Deploy
💄 :lipstick:           # UI/estilos
🎉 :tada:               # Inicio de proyecto
✅ :white_check_mark:   # Agregar tests
🔒 :lock:               # Seguridad
🔖 :bookmark:           # Versiones/tags
🚧 :construction:       # Trabajo en progreso
⬆️ :arrow_up:           # Actualizar dependencias
⬇️ :arrow_down:         # Downgrade dependencias
♻️ :recycle:            # Refactorizar
```

---

## 💡 Tips Rápidos

1. **Siempre** haz `git status` antes de cualquier operación importante
2. **Commits pequeños y frecuentes** > commits grandes
3. **Pull antes de push** para evitar conflictos
4. **Usa ramas** para cualquier cambio no trivial
5. **Lee los mensajes de error** - Git suele sugerir la solución
6. **Practica en un repo de prueba** antes de usar comandos peligrosos
7. **Configura .gitignore** desde el inicio del proyecto
8. **Escribe buenos mensajes de commit** - tu yo futuro te lo agradecerá

---

*🔗 Para más detalles, consulta la [guía completa](./README.md) o ejecuta `git help [comando]`*