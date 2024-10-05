# Aplicación de Tarjeta de Crédito

Esta es una aplicación simple en Vue.js que simula un formulario de entrada de tarjeta de crédito, permitiendo a los usuarios ingresar dinámicamente la información de la tarjeta. La aplicación proporciona retroalimentación en tiempo real, formateando el número de la tarjeta a medida que los usuarios escriben y convirtiendo el título de la tarjeta a mayúsculas.

## Características

- **Formulario Dinámico**: Los usuarios pueden ingresar detalles de la tarjeta, incluyendo el título, la ruta de la imagen del chip, el número de la tarjeta, la fecha de expiración y el nombre del propietario.
- **Formateo en Tiempo Real**: El número de la tarjeta se formatea con espacios entre cada tres dígitos.
- **Título en Mayúsculas**: El título de la tarjeta se convierte automáticamente a mayúsculas a medida que el usuario escribe.
- **Manejo de Imágenes**: La aplicación utiliza imágenes para el chip y el tipo de tarjeta, que se cargan desde el directorio `public/assets`.

## Instalación

1. **Clona el repositorio**:
   ```bash
   git clone git@github.com:maaferna/DesafioM6BindingVue.git

Navega al directorio del proyecto:

```bash
cd my-credit-card-app
```

Instala las dependencias:

```bash
npm install
```
Inicia el servidor de desarrollo:

```bash
npm run dev
```
Abre tu navegador y ve a http://localhost:5173 (o la URL que aparece en tu terminal) para ver la aplicación.

Estructura del Proyecto


mi-proyecto/
├── public/
│   ├── assets/
│   │   ├── chip.png
│   │   └── visa.png
├── src/
│   ├── App.vue
│   └── main.js
├── index.html
└── vite.config.js

Tecnologías Utilizadas
Vue.js: Framework de JavaScript para construir interfaces de usuario.
Vite: Herramienta de construcción que proporciona una experiencia de desarrollo rápida.
CSS: Para el estilo de la aplicación.


Contribuciones
Si deseas contribuir a este proyecto, por favor, haz un fork del repositorio y envía un pull request con tus cambios.

Licencia
Este proyecto está licenciado bajo la Licencia MIT - consulta el archivo LICENSE para más detalles.


### Instrucciones para Crear `README.md`

1. **Crear el Archivo**:
   En el directorio raíz de tu proyecto, crea un nuevo archivo llamado `README.md`.

2. **Copiar y Pegar**:
   Copia la plantilla anterior en tu archivo `README.md`.

3. **Personalizar**:
   - Reemplaza `<tu-url-del-repositorio>` con la URL de tu repositorio en GitHub.
   - Actualiza cualquier sección que requiera más detalles específicos sobre tu proyecto.

### Pasos Finales

Una vez que hayas creado y personalizado tu `README.md`, asegúrate de hacer un commit en tu control de versiones:

```bash
git add README.md
git commit -m "Agregar archivo README"
git push
