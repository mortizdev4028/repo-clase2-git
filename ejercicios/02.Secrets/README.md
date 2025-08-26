# 🧪 Ejercicio 02: Variables y secretos

Este ejercicio te ayudará a crear y ejecutar tu primer workflow

---

## 🎯 Objetivo

- Crear un workflow basico
- Ejecutar tu workflow
- Visualizacion de logs

---

## Pasos
### 1.  Utiliza el repositorio creado en el Ejercicio 1

### 2.  Crear un secreto en GitHub `(Settings → Secrets → New repository secret)` llamado MI_SECRETO`

### 3. Crea el `workflow` llamado `02_variables_secretos.yml` con el contenido:
```yaml copy
name: Uso de Variables y Secretos
on:
  push:
    branches:
      - main
jobs:
  mostrar-secretos:
    runs-on: ubuntu-latest
    steps:
      - name: Mostrar variable de entorno
        run: echo "Variable de entorno: ${{ env.MI_VARIABLE }}"
        env:
          MI_VARIABLE: "ValorDeEjemplo"
      
      - name: Mensaje con secreto
        run: echo "Secreto guardado correctamente"
        env:
          SECRETO: ${{ secrets.MI_SECRETO }}
```
### 4. Haz `commit` y `Push` (sin olvidar `add`). **Nota: los secretos nunca se imprimen en los logs**
