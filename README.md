# Sistema de Gestión de Inventario

Aplicación de gestión de inventario desarrollada con Flutter y una API REST creada con Node.js, Express y SQLite. Este repositorio también documenta el proceso académico de distribución de la aplicación Android mediante Firebase App Distribution.

## Funcionalidades

- Consultar el listado de productos.
- Ver los detalles de un producto.
- Registrar, editar y eliminar productos.
- Validar los datos antes de guardarlos.
- Evitar códigos de producto duplicados.
- Consultar estadísticas generales del inventario.
- Almacenar la información en SQLite.

## Tecnologías utilizadas

**Frontend**
- Flutter y Dart.
- Dio para solicitudes HTTP.
- go_router para navegación.
- flutter_dotenv para configurar la URL de la API.

**Backend**
- Node.js.
- Express.
- SQLite mediante better-sqlite3.

**Distribución**
- Firebase App Distribution.
- Archivos APK en formato release.
- Grupo de verificadores `QA_Clase`.

## Estructura del proyecto

```text
talle1-apk/
├── backend/
├── frontend/
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

## Requisitos previos

- Node.js y npm.
- Flutter y Dart.
- Android Studio o dispositivo Android.
- Acceso al backend desde el dispositivo de prueba.

## Instalación y ejecución

### Backend

Desde la raíz del repositorio:

```bash
cd backend
npm install
npm start
```

El servidor utiliza el puerto 3000.

### Frontend

En otra terminal:

```bash
cd frontend
flutter pub get
```

Crear un archivo `.env` a partir de `.env.example` y configurar la dirección de la API según el entorno.

Para un emulador Android:

```env
API_URL=http://10.0.2.2:3000/api
```

Para un dispositivo físico, utilizar la dirección IP local del computador donde se ejecuta el backend, siempre que ambos dispositivos estén conectados a una red que permita la comunicación.

Ejecutar la aplicación:

```bash
flutter run
```

## Distribución con Firebase App Distribution

Para este taller se utilizó Firebase App Distribution para publicar y distribuir versiones APK de la aplicación Android.

**Proyecto Firebase:** `inventario-flutter-a36cd`

**Identificador de aplicación Android:** `com.saramalaver.inventario`

**Grupo de verificadores:** `QA_Clase`

**Correo del verificador registrado:** `dduran@uceva.edu.co`

### Generación del APK

Desde la carpeta `frontend`:

```bash
flutter pub get
flutter clean
flutter build apk --release
```

El archivo generado se encuentra en:

```text
build/app/outputs/flutter-apk/app-release.apk
```

### Versionamiento y publicaciones

| Versión | Build | Descripción |
|---|---:|---|
| 1.0.0 | 1 | Primera publicación de la aplicación para pruebas. |
| 1.0.1 | 2 | Ajuste de la conexión con el servidor para pruebas desde dispositivos Android físicos. |

La versión se actualiza en `frontend/pubspec.yaml`, utilizando el formato `version: versión+build`.

### Proceso de distribución

1. Generar el APK en modo release.
2. Ingresar a Firebase Console.
3. Abrir App Distribution.
4. Cargar el APK generado.
5. Seleccionar el grupo `QA_Clase`.
6. Agregar las notas de la versión.
7. Distribuir la publicación.
8. Compartir el vínculo de instalación con los verificadores.
9. Instalar la aplicación y comprobar su funcionamiento.

### Pruebas de calidad (QA)

Se realizaron pruebas de instalación y funcionamiento en un dispositivo Android físico.

- Recepción de la invitación de Firebase.
- Instalación de la primera versión.
- Apertura de la aplicación.
- Verificación de la conexión con el backend.
- Publicación e instalación de la actualización 1.0.1.
- Comprobación del funcionamiento después de actualizar.

## Notas de versión

**Versión 1.0.0 (Build 1)**

Primera publicación de la aplicación Inventario para pruebas de instalación y funcionamiento.

**Versión 1.0.1 (Build 2)**

Se ajustó la dirección de conexión con el servidor para permitir el acceso desde dispositivos Android físicos conectados a la misma red local del backend.

## Consideraciones de configuración

- Los archivos `.env` contienen configuración local y no deben subirse al repositorio.
- La base de datos SQLite local se genera en el entorno de ejecución.
- El servidor debe permanecer activo y accesible para que la aplicación pueda consultar el inventario.
- La dirección IP local utilizada durante las pruebas depende de la red donde se encuentre el computador.

## Enlaces de instalación

- **Versión 1.0.0 (Build 1):** [Instalar desde Firebase App Distribution](https://appdistribution.firebase.google.com/testerapps/1:927727331242:android:7a09e2005475a2f1c5edd3/releases/1nvq7pnl6tt68?utm_source=firebase-console)
- **Versión 1.0.1 (Build 2):** Pendiente de agregar el enlace de distribución.

Los enlaces están destinados a los verificadores autorizados en Firebase App Distribution.

## Autoría

Proyecto académico de Ingeniería de Sistemas.