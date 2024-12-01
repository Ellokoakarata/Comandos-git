
# Guía de Comandos Git para Trabajar Correctamente y Solucionar Errores

## **1. Inicializar un repositorio**
```bash
git init
```

## **2. Crear una nueva rama principal (`main`)**
```bash
git branch -M main
```

## **3. Agregar archivos al staging area**
```bash
git add .
```

## **4. Realizar un commit**
```bash
git commit -m "Descripción del commit"
```

## **5. Configurar un repositorio remoto**
### Agregar el remoto:
```bash
git remote add origin https://github.com/usuario/repositorio.git
```

### Verificar los remotos:
```bash
git remote -v
```

### Actualizar la URL del remoto si es necesario:
```bash
git remote set-url origin https://github.com/usuario/repositorio-renombrado.git
```

### Eliminar un remoto si es incorrecto:
```bash
git remote remove origin
```

## **6. Enviar cambios al repositorio remoto**
```bash
git push -u origin main
```

## **7. Obtener cambios del remoto**
```bash
git pull origin main
```

## **8. Verificar el estado actual del repositorio**
```bash
git status
```

## **9. Solución de errores comunes**

### **Error: src refspec main does not match any**
- Asegúrate de haber realizado al menos un commit antes de hacer `git push`:
```bash
git add .
git commit -m "Primer commit"
git push -u origin main
```

### **Error: remote origin already exists**
- Solución: Actualiza o elimina el remoto existente:
```bash
git remote set-url origin https://github.com/usuario/repositorio.git
# o
git remote remove origin
git remote add origin https://github.com/usuario/repositorio.git
```

### **Error: Everything up-to-date**
- Esto indica que no hay cambios pendientes para enviar. Verifica tu estado local:
```bash
git status
```

### **Error: rejected because the remote contains work that you do not have locally**
- Realiza un pull para integrar los cambios del remoto antes de hacer push:
```bash
git pull origin main --rebase
git push
```

### **Error: branch 'main' set up to track 'origin/main'**
- Este no es un error, es una confirmación de que la rama local está vinculada correctamente con el remoto.

## **10. Revertir cambios locales**
### Restablecer el estado de los archivos al último commit:
```bash
git checkout -- .
```

### Deshacer el último commit (manteniendo los cambios locales):
```bash
git reset --soft HEAD~1
```

### Deshacer el último commit (eliminando los cambios locales):
```bash
git reset --hard HEAD~1
```

---

## **11. Comandos avanzados**
### Ver el historial de commits:
```bash
git log --oneline
```

### Ver diferencias entre el estado actual y el último commit:
```bash
git diff
```

### Crear y cambiar a una nueva rama:
```bash
git checkout -b nueva-rama
```

### Cambiar a una rama existente:
```bash
git checkout nombre-rama
```

### Fusionar ramas:
```bash
git merge nombre-rama
```

---

## **12. Buenas prácticas**
- Realiza commits pequeños y descriptivos.
- Siempre verifica el estado del repositorio antes de realizar operaciones críticas.
- Sincroniza regularmente los cambios con el remoto.
- Revisa los logs (`git log`) para entender la historia de cambios.

---

¡Con estos comandos, tienes todo lo necesario para trabajar correctamente con Git y solucionar errores comunes!
