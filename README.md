# Expo Firebase Login App

Aplicación móvil básica con Expo, Firebase Authentication y dos pantallas: Login y Saludo.

## Estructura del proyecto

```
src/
├── app/                    # Rutas (Expo Router)
│   ├── _layout.js          # Layout raíz + AuthProvider
│   ├── index.js            # Pantalla Login
│   └── (authenticated)/
│       ├── _layout.js      # Layout rutas protegidas
│       ├── index.js        # Redirige a saludo
│       └── saludo.js       # Pantalla de saludo
├── components/
│   └── forms/
│       └── LoginForm.js    # Formulario de login
├── config/
│   └── firebase.js         # Configuración Firebase
├── context/
│   └── AuthContext.js      # Context de autenticación
├── lib/
│   └── auth.js             # loginWithEmail, logout
└── hooks/
    └── useAuth.js          # Hook useAuth()
```

## Configuración de Firebase

1. Crea un proyecto en [Firebase Console](https://console.firebase.google.com)
2. Añade una app web y copia la configuración
3. En Authentication > Sign-in method, activa **Email/Password**
4. Abre `src/config/firebase.js` y reemplaza los valores de `firebaseConfig`:

```javascript
const firebaseConfig = {
  apiKey: 'TU_API_KEY',
  authDomain: 'TU_PROJECT_ID.firebaseapp.com',
  projectId: 'TU_PROJECT_ID',
  storageBucket: 'TU_PROJECT_ID.appspot.com',
  messagingSenderId: 'TU_SENDER_ID',
  appId: 'TU_APP_ID',
};
```

5. Crea un usuario de prueba en Firebase Console (Authentication > Users > Add user) con email y contraseña.

## Ejecutar la aplicación

```bash
npm start
```

Luego escanea el código QR con Expo Go en tu dispositivo, o presiona `a` para Android / `w` para web.
