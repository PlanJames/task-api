# 📝 Task API - Backend con FastAPI

Una API RESTful "moderna" para gestionar tareas personales, desarrollada con FastAPI, autenticacion JWT, SQLAlchemy y SQLite.

---

## 🚀 Tecnologias utilizadas

- **FastAPI**: framework moderno para APIs.
- **SQLite**: base de datos ligera.
- **SQLAlchemy**: ORM para interactuar con la base de datos.
- **JWT (JSON Web Tokens)**: autenticacion segura.
- **Docker** y **Docker Compose**: despliegue fácil.
- **Swagger UI**: documentacion automatica de la API.
- **SlowAPI**: proteccion contra abuso de peticiones (rate limiting).

---

## ⚙️ Instalacion local

```bash
git clone https://github.com/PlanJames/task-api.git
cd task-api
python -m venv env
source env/bin/activate  # En Windows: .\env\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

Accede a la documentacion automatica en:
[http://localhost:8000/docs](http://localhost:8000/docs)

---

## 🐳 Instalación con Docker

```bash
docker-compose up --build
```

---

## 🔐 Endpoints principales

### 🔸 Auth
- `POST /auth/register`: Crea usuarios
- `POST /auth/login`: Obtiene token JWT
- `POST /auth/refresh`: Renova token

### 🔸 Tasks (requiere token JWT)
- `GET /tasks/`: Ve tareas (con filtros opcionales)
- `POST /tasks/`: Crea nuevas tareas
- `PUT /tasks/{id}`: Edita una tarea
- `PATCH /tasks/{id}/complete`: Marca como completada
- `DELETE /tasks/{id}`: Elimina una tarea

---

## 📦 Ejemplo de uso con filtros

```http
GET /tasks/?completed=true
GET /tasks/?from_date=2025-05-01&to_date=2025-05-15
```

---

## 🛡️ Seguridad y limites

- Autenticación con JWT
- Rate limit: 5 requests por minuto al listar tareas
- Manejo de errores centralizado


---

## 📌 Pendiente o mejoras a implementar

- 🌐 Soporte para PostgreSQL
- 🧪 Tests automaticos
- 🔄 Refresh tokens con expiración extendida
- 🌍 Despliegue en Render o Railway

---

## ✨ Autor

[@jose](https://github.com/PlanJames)
