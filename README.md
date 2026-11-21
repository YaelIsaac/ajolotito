# Ajolotito hambriento · Notificaciones locales en Flutter con TDD

**Materia:** Desarrollo de Aplicaciones Móviles
**Alumno:** González López Yael Isaac
**Fecha:** 20 de noviembre de 2026

## Descripción

Mascota virtual (un ajolote) que da hambre con el tiempo y avisa con notificaciones locales cuando tiene hambre, cuando está famélico y con una sorpresa diaria. La saciedad no se guarda como un número que baja con un temporizador: se guarda desde cuándo y cuánto comió, y se calcula, así que funciona aunque la app esté cerrada. Los avisos respetan horas de silencio (22:00 a 8:00), usan canales que el usuario puede apagar por separado, tienen ids fijos para reemplazar y cancelar sin duplicados, y validan el payload al tocarlos. El permiso se pide en contexto, con una explicación propia antes del diálogo del sistema, y si el usuario lo niega no se le insiste. Todo se desarrolló con TDD, aislando el plugin detrás de una interfaz para probar sin teléfono.

## Estructura del proyecto

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas de casos (éxito y fallo)

## Pruebas de la mascota (16) · test/mascota_test.dart

Pruebas: saciedad calculada en el tiempo, que nunca baja de 0, estados de ánimo, alimentar y cuándo llega al hambre o al estado crítico.

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (empieza en 100 y baja 10 puntos por hora)

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas de política y payload (12) · test/politica_payload_test.dart

Pruebas: horas de silencio, mover un aviso fuera del silencio y payload seguro (destinos válidos, texto raro o malicioso no rompe la app).

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (de 22 a 7:59 hay silencio)

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas del planificador (13) · test/planificador_test.dart

Pruebas: qué avisos programar y a qué hora (hambre, crítico y sorpresas), sin caer en silencio, sin avisos en el pasado y con ids fijos.

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (día normal: hambre 16:00, sorpresa 18:00, crítico 18:30)

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas del permiso (6) · test/permiso_test.dart

Pruebas: tres estados (sin preguntar, concedido y denegado), no pedir dos veces y ofrecer Ajustes si se negó.

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (al inicio nunca hemos preguntado)

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas del servicio (14) · test/servicio_test.dart

Pruebas: guardar y recuperar al ajolote, sincronizar avisos en segundo plano, cancelar al alimentar, preferencias por categoría y destino al abrir desde una notificación.

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (la primera vez crea al ajolote y lo guarda)

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas del ViewModel (10) · test/vm_test.dart

Pruebas: no pedir permiso al arrancar, activar avisos en contexto, alimentar, tocar una notificación y botón de acción.

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (al iniciar NO pide permiso)

<!-- PEGA AQUÍ LA CAPTURA -->

## Pruebas de pantalla (3) · test/pantalla_test.dart

Pruebas: el ajolote feliz con el botón de avisos, dar de comer sube la saciedad y el diálogo propio antes del permiso.

### Éxito (todas en verde)

<!-- PEGA AQUÍ LA CAPTURA -->

### Fallo (muestra al ajolote feliz y el botón para activar avisos)

<!-- PEGA AQUÍ LA CAPTURA -->

## Todas las pruebas en verde (74)

<!-- PEGA AQUÍ LA CAPTURA -->

## Evidencia de la aplicación

### Pantalla del ajolote

<!-- PEGA AQUÍ LA CAPTURA -->

### Explicación propia antes de pedir el permiso

<!-- PEGA AQUÍ LA CAPTURA -->

### Notificación recibida

<!-- PEGA AQUÍ LA CAPTURA -->

## Conclusión

Con TDD las notificaciones dejaron de ser algo que "solo se prueba en el teléfono": el plugin quedó detrás de una interfaz y toda la lógica (cuándo avisar, horas de silencio, ids fijos, payload seguro y permiso en tres estados) se probó en segundos con falsos. Las capturas de fallo demuestran que las pruebas sí detectan errores. Calcular la saciedad en lugar de guardarla hace que el ajolote funcione aunque la app esté cerrada, y respetar el permiso y el silencio hace que los avisos ayuden en lugar de molestar.
