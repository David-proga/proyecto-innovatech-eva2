Evaluacion 2 - Contenerización y CI/CD

Proyecto de ejemplo para la evaluación: contenedorización de `frontend` y `backend`, persistencia con `postgres`, y pipelines CI/CD con GitHub Actions que construyen, publican en Docker Hub y despliegan a instancias EC2.

Resumen rápido:
- Frontend: Vite + React, multi-stage Dockerfile, servido por nginx en puerto 8080 (mapeado a 80).
- Backend: Node + Express, PostgreSQL como servicio, multi-stage Dockerfile, expone puerto 3000.
- `docker-compose.yml`: levanta `db`, `backend` y `frontend` para pruebas locales. Usa volumen nombrado para persistencia.
- Workflows: `.github/workflows/deploy.yml` en cada subrepo. Trigger: `push` a rama `deploy`.

Siguientes pasos (resumen):
1. Revisar los archivos bajo `frontend/` y `backend/`.
2. Configurar secretos en GitHub (DOCKERHUB, EC2 SSH, credenciales Postgres).
3. Crear claves SSH y añadir la pública en `~/.ssh/authorized_keys` de las EC2.
4. Hacer `git push` a cada repositorio (rama `deploy`) para disparar pipelines.

Ver los archivos creados en las carpetas `frontend/` y `backend/`.
