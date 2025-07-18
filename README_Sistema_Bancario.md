# HyperBank - Sistema Bancario

Sistema bancario desarrollado en Java con JavaFX que permite gestionar cuentas, transferencias y contactos de forma segura.

## 🚀 Características

- **Autenticación segura** con credenciales encriptadas
- **Gestión de contactos** para transferencias rápidas
- **Transferencias tradicionales** por correo electrónico
- **Transferencias por llaves** (sistema de llaves públicas)
- **Interfaz gráfica moderna** con JavaFX
- **Almacenamiento seguro** de datos en archivos CSV

## 📋 Requisitos

- Java 17 o superior
- Maven 3.6 o superior
- Cuenta de Gmail con verificación en dos pasos habilitada

## 🔧 Instalación

### 1. Clonar el repositorio
```bash
git clone <url-del-repositorio>
cd HyperBank
```

### 2. Configurar credenciales de email
**IMPORTANTE**: Antes de ejecutar la aplicación, debes configurar las credenciales de email.

#### Opción A: Usar script (Recomendado)
```bash
# Windows
configurar_email.bat

# Linux/Mac
./configurar_email.sh
```

#### Opción B: Comando manual
```bash
mvn compile exec:java -Dexec.mainClass="org.example.hyperbank.utils.EmailConfigSetup"
```

### 3. Ejecutar la aplicación
```bash
mvn javafx:run
```

## 🔐 Configuración de Credenciales

Para que el sistema de envío de correos funcione, necesitas configurar las credenciales de Gmail:

1. **Habilitar verificación en dos pasos** en tu cuenta de Google
2. **Generar contraseña de aplicación**:
   - Ve a https://myaccount.google.com/
   - Seguridad → Contraseñas de aplicación
   - Selecciona "Correo" y tu sistema operativo
   - Copia la contraseña de 16 caracteres
3. **Ejecutar la herramienta de configuración** (ver pasos de instalación)

## 📁 Estructura del Proyecto

```
HyperBank/
├── src/main/java/org/example/hyperbank/
│   ├── controller/          # Controladores de JavaFX
│   ├── core/               # Lógica de negocio
│   ├── registro/           # Sistema de registro
│   ├── utils/              # Utilidades (email, credenciales)
│   └── verificacion/       # Sistema de verificación
├── src/main/resources/     # Archivos FXML y recursos
├── src/test/              # Pruebas unitarias
└── README_CREDENCIALES.md # Guía detallada de configuración
```

## 🔒 Seguridad

- **Credenciales encriptadas**: Las credenciales de email se almacenan usando hash SHA-256 con salt
- **Archivos protegidos**: Los archivos de configuración están en `.gitignore`
- **Validación de datos**: Todos los inputs son validados antes de procesarse

## 🧪 Pruebas

```bash
mvn test
```

## 📝 Archivos de Datos

El sistema utiliza los siguientes archivos CSV para almacenar datos:
- `usuarios.csv` - Información de usuarios registrados
- `contactos.csv` - Lista de contactos por usuario
- `llaves.csv` - Llaves públicas para transferencias seguras

**Nota**: Estos archivos se crean automáticamente al usar la aplicación.

## 🚨 Solución de Problemas

### Error de credenciales de email
- Verifica que hayas ejecutado `EmailConfigSetup`
- Confirma que la contraseña de aplicación sea correcta
- Asegúrate de que la verificación en dos pasos esté habilitada

### Error de compilación
- Verifica que tengas Java 17+ instalado
- Confirma que Maven esté en el PATH

## 📄 Licencia

Este proyecto es para fines educativos.

## 🤝 Contribución

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request 
