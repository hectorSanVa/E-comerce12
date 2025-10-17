# MoviStore - E-commerce App

## 📱 Proyecto de E-commerce para Universidad Autónoma de Chiapas

**MoviStore** es una aplicación de e-commerce desarrollada con React Native/Expo para el frontend móvil y Node.js/Express para el backend API REST, conectada a una base de datos PostgreSQL.

## 🏗️ Arquitectura del Sistema

### **Frontend Móvil**
- **React Native** con **Expo**
- **JavaScript** multiplataforma (iOS/Android)
- **Consumo de API REST** mediante HTTP/HTTPS
- **Interfaz nativa** para ambos sistemas operativos

### **Backend API REST**
- **Node.js** + **Express.js**
- **PostgreSQL** como base de datos
- **JWT** para autenticación y autorización
- **Multer** para gestión de imágenes
- **CORS** para comunicación con app móvil

### **Base de Datos**
- **PostgreSQL** con esquema relacional
- **Transacciones** para integridad de datos
- **Índices** para optimización de rendimiento
- **Función transaccional** `create_order`

## 📋 Funcionalidades Implementadas

### **Para Clientes:**
- ✅ **Catálogo de productos** con imágenes
- ✅ **Carrito de compras** 
- ✅ **Proceso de checkout**
- ✅ **Gestión de perfil** de usuario

### **Para Administradores:**
- ✅ **CRUD de productos** con imágenes
- ✅ **CRUD de categorías**
- ✅ **Gestión de inventario** por sucursal
- ✅ **Control de stock** automático
- ✅ **Gestión de usuarios**
- ✅ **Proceso de órdenes** completo

## 🚀 Instalación y Configuración

### **Prerrequisitos:**
- Node.js (v16 o superior)
- PostgreSQL (v12 o superior)
- Git

### **1. Clonar el repositorio:**
```bash
git clone https://github.com/hectorSanVa/E-comerce12.git
cd E-comerce12
```

### **2. Configurar Base de Datos:**
```sql
-- Crear base de datos
CREATE DATABASE movistore_db;

-- Ejecutar esquema
\i movistore_schema.sql

-- Insertar datos de ejemplo
\i movistore_seed.sql
```

### **3. Configurar Backend:**
```bash
cd backend
npm install
cp env.example .env
# Editar .env con tus credenciales de PostgreSQL
npm run dev
```

### **4. Configurar App Móvil:**
```bash
cd MoviStoreApp
npm install
npx expo start
```

## 📁 Estructura del Proyecto

```
Ecommerce1y2/
├── backend/                 # API REST
│   ├── config/
│   │   └── db.js          # Conexión PostgreSQL
│   ├── middleware/
│   │   └── auth.js        # JWT middleware
│   ├── routes/
│   │   ├── auth.js        # Autenticación
│   │   ├── products.js    # CRUD productos
│   │   ├── categories.js  # CRUD categorías
│   │   ├── images.js      # Upload imágenes
│   │   ├── users.js       # Gestión usuarios
│   │   ├── orders.js      # Proceso órdenes
│   │   └── stores.js      # Gestión tiendas
│   ├── uploads/           # Almacenamiento imágenes
│   ├── server.js          # Servidor principal
│   └── package.json       # Dependencias
├── MoviStoreApp/          # App móvil React Native
├── movistore_schema.sql   # Esquema de base de datos
├── movistore_seed.sql     # Datos de ejemplo
└── README.md             # Este archivo
```

## 🔧 API Endpoints

### **Públicos:**
- `GET /api/health` - Estado del API
- `GET /api/products` - Listar productos
- `GET /api/categories` - Listar categorías
- `GET /api/stores` - Listar tiendas

### **Autenticación:**
- `POST /api/auth/register` - Registro de usuarios
- `POST /api/auth/login` - Login con JWT
- `GET /api/auth/profile` - Perfil del usuario

### **CRUD Productos (Admin):**
- `POST /api/products` - Crear producto
- `PUT /api/products/:id` - Actualizar producto
- `DELETE /api/products/:id` - Eliminar producto

### **CRUD Categorías (Admin):**
- `POST /api/categories` - Crear categoría
- `PUT /api/categories/:id` - Actualizar categoría
- `DELETE /api/categories/:id` - Eliminar categoría

### **Upload de Imágenes (Admin):**
- `POST /api/images/product/:id` - Subir imagen
- `GET /api/images/product/:id` - Obtener imágenes
- `DELETE /api/images/:id` - Eliminar imagen

## 🧪 Pruebas

### **Backend API:**
```bash
# Estado del API
curl http://localhost:3000/api/health

# Listar productos
curl http://localhost:3000/api/products

# Listar categorías
curl http://localhost:3000/api/categories
```

### **App Móvil:**
```bash
# Iniciar servidor de desarrollo
npx expo start

# Escanear QR con Expo Go
# o usar emulador/simulador
```

## 📊 Base de Datos

### **Tablas principales:**
- `users` - Usuarios del sistema
- `categories` - Categorías de productos
- `stores` - Sucursales de la tienda
- `products` - Catálogo de productos
- `product_images` - Imágenes de productos
- `product_stock` - Stock por sucursal
- `orders` - Órdenes de compra
- `order_items` - Items de cada orden
- `stock_movements` - Auditoría de stock

### **Función transaccional:**
```sql
SELECT create_order(user_id, store_id, json_items);
```

## 🔐 Seguridad

- **JWT** para autenticación
- **Roles** (cliente/administrador)
- **Validación** de datos de entrada
- **Helmet** para headers de seguridad
- **CORS** configurado
- **Hash** de contraseñas con bcrypt

## 👨‍💻 Desarrollador

**Hector** - Universidad Autónoma de Chiapas  
**Facultad de Negocios Campus IV**  
**Programación WEB y Móviles - Séptimo Semestre**

## 📄 Licencia

Este proyecto es desarrollado para fines académicos en la Universidad Autónoma de Chiapas.

---

**MoviStore** - E-commerce App con React Native, Node.js y PostgreSQL
