# Portal del empleado · Garcia de Pou (demo)

Web estática (GitHub Pages) con los datos, usuarios y fotos en Supabase (plan gratuito), igual que la web de recambios.

- `index.html` — el portal (el mismo de la demo compartida de Claude).
- `supa-shim.js` — conexión con Supabase (acceso con correo y contraseña). Basado en el de recambios.
- `config.js` — dirección y clave pública del proyecto de Supabase **del portal**.
- `schema.sql` — estructura de la base de datos (pegar en Supabase → SQL Editor → Run).

## Puesta en marcha
1. **Supabase**: crea un proyecto nuevo solo para el portal (no uses el de recambios).
   SQL Editor → pega `schema.sql` → Run. Storage: el script crea el espacio de archivos.
2. **Usuarios**: Authentication → Users → Add user (correo y contraseña, marcar "Auto Confirm User").
   Para la demo puede bastar un usuario común que compartes con quien vaya a probarla.
   Si quieres que alguien sea administrador, añade su correo en la tabla `admins`.
3. **config.js**: Project Settings → API → copia "Project URL" y la clave "publishable" y pégalas.
4. **GitHub**: crea el repositorio `portal-empleado` en la organización `recambios-fabrica`, sube estos archivos
   y en Settings → Pages elige "Deploy from a branch", rama `main`, carpeta `/ (root)`.
   La dirección será `https://recambios-fabrica.github.io/portal-empleado/`.
5. **Supabase → Authentication → URL Configuration**: añade esa dirección en "Redirect URLs"
   (para el enlace de «¿Has olvidado la contraseña?»).
6. Entra por primera vez y pulsa **Cargar datos de ejemplo**.

## Cómo se entra
Primero con el correo y la contraseña de Supabase (acceso a la web). Después, dentro del portal,
con un usuario de prueba: empleado 04821, RRHH 90001 o comité 90002 (PIN 1234).

## Importante
Es una **demo con datos ficticios**. Todos los usuarios de Supabase pueden leer y escribir todos los datos,
y los PIN de prueba están a la vista. No metas datos reales del personal: para eso está la aplicación
con servidor (Flask) del paquete `portal_garcia_de_pou_v18.zip`.
