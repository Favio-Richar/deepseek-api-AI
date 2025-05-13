🧠 Informe del Proyecto – DeepSeek API
📌 Nombre del proyecto
DeepSeek API – Integración de IA con Django REST Framework + Docker

👨‍💻 Desarrollado por
Favio Jiménez Barrenechea

Estudiante de Ingeniería Informática

Curso: Desarrollo Web / Servicios API REST

GitHub: Favio-Richar

🎯 Objetivo del proyecto
Construir una API REST usando Django que permita enviar mensajes (prompt) a una inteligencia artificial (IA DeepSeek), recibir una respuesta generada automáticamente, y hacer pruebas mediante Postman. Todo se ejecuta dentro de un contenedor Docker para facilitar la portabilidad y despliegue.

🧱 Tecnologías utilizadas
Python 3.11

Django 5.2.1

Django REST Framework

Docker + Docker Compose

Postman (para pruebas)

IA externa (DeepSeek)

📁 Estructura del proyecto
Copiar
Editar
deepseek-api-AI/
├── chat/
│   ├── services/
│   │   └── deep_seek_service.py
│   ├── views/
│   │   ├── viewTest.py
│   │   └── viewDeepseek.py
│   └── urls.py
├── ia_django_assistant/
│   ├── settings.py
│   └── urls.py
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── manage.py
└── README.md
🔧 Comandos usados (paso a paso)
📁 Crear carpetas y archivos del proyecto
bash
Copiar
Editar
mkdir -p chat/services
mkdir -p chat/views
touch chat/services/deep_seek_service.py
touch chat/views/viewTest.py
touch chat/views/viewDeepseek.py
🐳 Crear y levantar contenedor con Docker
bash
Copiar
Editar
sudo docker compose up --build -d
⚙️ Aplicar migraciones de Django
bash
Copiar
Editar
sudo docker exec -it deepseek-container python manage.py migrate
🧪 Probar en Postman
Endpoint GET /api/test/
Verifica que el servidor responda correctamente

URL:

bash
Copiar
Editar
http://localhost:8000/api/test/
Respuesta esperada:

json
Copiar
Editar
{
  "message": "El endpoint de prueba funciona correctamente 🎉"
}
Endpoint POST /api/deepseek/
Envía un mensaje a la IA y recibe respuesta

URL:

bash
Copiar
Editar
http://localhost:8000/api/deepseek/
Cuerpo (raw JSON):

json
Copiar
Editar
{
  "message": "¿Qué es Python?"
}
Respuesta esperada:

json
Copiar
Editar
{
  "respuesta": "Python es un lenguaje de programación..."
}
📤 Subida a GitHub
bash
Copiar
Editar
git add README.md .
git commit -m "Proyecto DeepSeek API funcional con Django y Docker"
git push origin main
✅ Estado del proyecto
✔ API funcional
✔ Docker operando correctamente
✔ IA integrada y respondiendo
✔ Probado con Postman
✔ Código limpio y organizado
