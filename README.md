# Ajolotito hambriento · Notificaciones locales en Flutter con TDD

**Materia:** Desarrollo de Aplicaciones Móviles
**Alumno:** González López Yael Isaac
**Fecha:** 20 de noviembre de 2026


## Estructura del proyecto

<img width="100" height="259" alt="image" src="https://github.com/user-attachments/assets/b10ba789-b2a1-41c6-acfa-eb19e6316818" />

## Pruebas de casos (éxito y fallo)

## Pruebas de la mascota (16) · test/mascota_test.dart

Pruebas: saciedad calculada en el tiempo, que nunca baja de 0, estados de ánimo, alimentar y cuándo llega al hambre o al estado crítico.

### Éxito (todas en verde)

<img width="403" height="386" alt="image" src="https://github.com/user-attachments/assets/e112d38f-ce57-48b2-9250-a4f506f5036f" />

### Fallo (empieza en 100 y baja 10 puntos por hora)

<img width="404" height="295" alt="image" src="https://github.com/user-attachments/assets/c941a621-8081-4918-81fa-62b210350ae4" />

## Pruebas de política y payload (12) · test/politica_payload_test.dart

Pruebas: horas de silencio, mover un aviso fuera del silencio y payload seguro (destinos válidos, texto raro o malicioso no rompe la app).

### Éxito (todas en verde)

<img width="399" height="341" alt="image" src="https://github.com/user-attachments/assets/aee67512-ae99-4c1e-9097-43c6e279d9d3" />

### Fallo (de 22 a 7:59 hay silencio)

<img width="404" height="264" alt="image" src="https://github.com/user-attachments/assets/ec23adc1-add5-46ac-871b-ddf7670e07ac" />

## Pruebas del planificador (13) · test/planificador_test.dart

Pruebas: qué avisos programar y a qué hora (hambre, crítico y sorpresas), sin caer en silencio, sin avisos en el pasado y con ids fijos.

### Éxito (todas en verde)

<img width="403" height="334" alt="image" src="https://github.com/user-attachments/assets/db6d7859-4a91-472f-b0ef-d45318ed921a" />

### Fallo (día normal: hambre 16:00, sorpresa 18:00, crítico 18:30)

<img width="401" height="326" alt="image" src="https://github.com/user-attachments/assets/e4d642b7-6edd-4055-934a-d70b9d040e23" />

## Pruebas del permiso (6) · test/permiso_test.dart

Pruebas: tres estados (sin preguntar, concedido y denegado), no pedir dos veces y ofrecer Ajustes si se negó.

### Éxito (todas en verde)

<img width="400" height="230" alt="image" src="https://github.com/user-attachments/assets/5dab2612-a287-4301-bb66-d1400bc62db5" />

### Fallo (al inicio nunca hemos preguntado)

<img width="402" height="233" alt="image" src="https://github.com/user-attachments/assets/0279807b-2bca-4e11-b123-e4b8132d550a" />

## Pruebas del servicio (14) · test/servicio_test.dart

Pruebas: guardar y recuperar al ajolote, sincronizar avisos en segundo plano, cancelar al alimentar, preferencias por categoría y destino al abrir desde una notificación.

### Éxito (todas en verde)

<img width="400" height="404" alt="image" src="https://github.com/user-attachments/assets/a8dc3538-1155-434c-afcf-9ebd6fadbfef" />

### Fallo (la primera vez crea al ajolote y lo guarda)

<img width="401" height="331" alt="image" src="https://github.com/user-attachments/assets/371a7b5d-473b-46d2-b2b8-507f2ccba9c8" />

## Pruebas del ViewModel (10) · test/vm_test.dart

Pruebas: no pedir permiso al arrancar, activar avisos en contexto, alimentar, tocar una notificación y botón de acción.

### Éxito (todas en verde)

<img width="400" height="358" alt="image" src="https://github.com/user-attachments/assets/78aa5cfa-e72e-4635-8573-51294520118a" />

### Fallo (al iniciar NO pide permiso)

<img width="402" height="276" alt="image" src="https://github.com/user-attachments/assets/ac40331b-6ed2-47d5-be0a-bb4ea3d3acaa" />

## Pruebas de pantalla (3) · test/pantalla_test.dart

Pruebas: el ajolote feliz con el botón de avisos, dar de comer sube la saciedad y el diálogo propio antes del permiso.

### Éxito (todas en verde)

<img width="401" height="268" alt="image" src="https://github.com/user-attachments/assets/91b348c8-fdff-4bd3-8a57-eb1e8ccd4328" />

### Fallo (muestra al ajolote feliz y el botón para activar avisos)

<img width="398" height="364" alt="image" src="https://github.com/user-attachments/assets/ed3ca338-dbff-4557-847f-44085c0e3bb0" />

## Todas las pruebas en verde (74)

<img width="283" height="50" alt="image" src="https://github.com/user-attachments/assets/7f17f227-fd76-4e92-aca0-f17cfb6b07fb" />

## Evidencia de la aplicación

### Pantalla del ajolote

<img width="300" height="650" alt="WhatsApp Image 2026-11-21 at 00 13 43" src="https://github.com/user-attachments/assets/1373260c-6213-42b4-b382-bc80b1d8545f" />

### Explicación propia antes de pedir el permiso

<img width="300" height="650" alt="WhatsApp Image 2026-11-21 at 00 13 43 (1)" src="https://github.com/user-attachments/assets/fa99734b-0d5a-4d1a-809f-81ffc53fb5f8" />

### Notificación recibida

<img width="300" height="650" alt="WhatsApp Image 2026-11-21 at 00 13 43 (2)" src="https://github.com/user-attachments/assets/3bf46e69-cfd5-4f6a-a2ce-e9354c5a4f29" />
