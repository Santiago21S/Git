
# Guía de Git y GitHub

Esta guía contiene los comandos fundamentales para el flujo de trabajo en desarrollo de software, ideal para organizar en herramientas de gestión de notas.

---

## 1. Configuración Inicial
Antes de empezar, configura tu identidad para que los commits queden registrados correctamente.

```bash
# Configurar nombre de usuario
git config --global user.name "Tu Nombre"

# Configurar correo electrónico
git config --global user.email "tu@email.com"

# Verificar la configuración actual
git config --list
```

---

## 2. Iniciar y Clonar Proyectos
```bash
# Inicializar un repositorio local en la carpeta actual
git init

# Clonar un repositorio remoto desde GitHub
git clone [https://github.com/usuario/nombre-del-repo.git](https://github.com/usuario/nombre-del-repo.git)
```

---

## 3. Flujo de Trabajo Diario
El ciclo estándar para registrar cambios en tu código.

```bash
# Ver el estado de tus archivos (modificados, nuevos, staged)
git status

# Preparar un único archivo
git add archivo.py

# Preparar todos los archivos modificados
git add .

# Registrar los cambios localmente con un mensaje descriptivo
git commit -m "feat: implementar hashing de contraseñas"

# Modificar el mensaje del último commit realizado
git commit --amend -m "Nuevo mensaje corregido"
```

---

## 4. Gestión de Ramas
Fundamental para el trabajo colaborativo y la implementación de nuevas funcionalidades.

```bash
# Listar todas las ramas locales
git branch

# Crear una nueva rama para una tarea específica
git branch nombre-de-la-rama

# Cambiar a una rama existente
git checkout nombre-de-la-rama

# Crear una nueva rama y cambiarse a ella inmediatamente
git checkout -b nueva-funcionalidad

# Borrar una rama local (después de fusionarla)
git branch -d nombre-de-la-rama
```

---

## 5. Sincronización con GitHub
```bash
# Enviar tus cambios locales a la rama remota en GitHub
git push origin nombre-de-la-rama

# Traer y fusionar los últimos cambios del servidor al local
git pull origin nombre-de-la-rama

# Ver la dirección del repositorio remoto configurado
git remote -v
```

---

## 6. Fusión y Resolución de Conflictos
Para integrar el código de una rama en otra (ej. de tu rama a `main`).

```bash
# 1. Cambiar a la rama que recibirá los cambios
git checkout main

# 2. Fusionar la rama de trabajo
git merge nombre-de-la-rama
```
*Si hay conflictos, Git marcará los archivos. Debes editarlos, elegir el código correcto, hacer `git add` y `git commit`.*

---

## 7. Utilidades y Deshacer Cambios
```bash
# Ver el historial de commits simplificado
git log --oneline

# Guardar cambios temporalmente sin hacer commit (limpia el workspace)
git stash

# Recuperar los cambios guardados en el stash
git stash pop

# Deshacer cambios locales en un archivo no trackeado
git checkout -- nombre-archivo

# Volver al commit anterior borrando los cambios actuales
git reset --hard HEAD~1
```

---

## 💡 Tips de Flujo Colaborativo
1. **Mantente actualizado:** Antes de empezar a programar cada día, haz un `git pull` para evitar conflictos futuros.
2. **Commits atómicos:** Haz commits pequeños y frecuentes que resuelvan una sola cosa.
3. **Nombres de ramas:** Usa prefijos como `feat/` (funcionalidad), `fix/` (corrección) o `docs/` (documentación).
