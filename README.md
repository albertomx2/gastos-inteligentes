# Proyecto de gastos automatizado con IA local y Telegram

Automatiza el registro y análisis de tus gastos personales o compartidos mediante mensajes de Telegram. Todo funciona **en local**, sin conexión con bancos ni servicios de terceros, y con **IA ligera (Phi de Microsoft)** para generar recomendaciones de ahorro.

---

## 🚀 Características principales

- Envío de mensajes desde el móvil por Telegram
- Detección automática de:
  - Persona (`"Soy Alberto..."`)
  - Tipo de operación (`Gasto` / `Ingreso`)
  - Monto y descripción
- Registro por usuario en su propio Excel
- Análisis inteligente con IA (modelo Phi local)
- Visualización de datos (gráficas o resúmenes)
- Funciona 100% en local (con Docker)

---

## 🧱 Estructura del proyecto

gastos-inteligentes/
├── docker/ # Configuración Docker de n8n
│ └── docker-compose.yml
├── scripts/ # Scripts de procesamiento y análisis
│ ├── procesador_mensajes.py
│ └── analisis_phi.py
├── datos/ # Archivos Excel por usuario
│ ├── alberto.xlsx
│ └── maria.xlsx
├── prompts/ # Prompts reutilizables para IA
│ └── ejemplo.txt
├── README.md
└── .gitignore


---

## 🛠️ Instalación (Linux)

1. Clona el repositorio:

git clone https://github.com/albertomx2/gastos-inteligentes.git
cd gastos-inteligentes

2. Configura Docker y ejecuta n8n:

cd docker
docker-compose up -d

3. Crea un bot de Telegram con @BotFather y copia el token

4. Abre n8n en el navegador (http://localhost:5678) y:

     ◉ Crea un flujo que escuche tu bot de Telegram

     ◉ Extraiga datos del mensaje

     ◉ Registre los datos en un archivo Excel

5. Instala Ollama para usar el modelo Phi localmente:

curl -fsSL https://ollama.com/install.sh | sh
ollama run phi


🤖 Ejemplo de mensajes válidos

Soy Alberto: gasté 17.40 en gasolinera
Soy María: ingreso 80 por clases

📄 Licencia
Este proyecto está publicado bajo la licencia MIT.

✨ Créditos
Desarrollado por Alberto Martínez (@albertomx2)
