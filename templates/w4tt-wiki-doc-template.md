# Servicio *{{Servicio}}*

> Grupo de servicios: `{{Grupo}}` · Especificación: [{{Grupo}}.yaml](../openapi/{{Grupo}}.yaml)

{{Descripción breve del servicio, a partir del summary del código}}

## Información común

#### Autenticación

Los endpoints requieren **Azure AD OAuth 2.0** (Bearer token).

#### Encabezados requeridos

```
Content-Type: application/json
Authorization: Bearer {access_token}
```

#### Seguridad

{{Privilegios, deberes o roles necesarios para el servicio, o "Pendiente de confirmar"}}

#### Códigos de estado HTTP

- `200 OK`: Llamada procesada. {{Si el servicio informa del resultado en el cuerpo: revisar el campo de éxito}}
- `400 Bad Request`: Formato inválido o datos no válidos.
- `401 Unauthorized`: Token ausente o inválido.
- `403 Forbidden`: La identidad autenticada no tiene permisos en F&O.
- `404 Not Found`: Ruta o servicio no encontrado en el Service Group.
- `500 Internal Server Error`: Error inesperado en servidor.

{{Nota "Importante" solo si el servicio devuelve resultado funcional en el cuerpo con HTTP 200}}

<!-- REPETIR LA SECCIÓN "Endpoint" POR CADA AxServiceOperation -->
## Endpoint *{{Operación}}*

{{Descripción de la operación}}

**Método:** `POST`
**URL:**

```
{{dynamics_url}}/api/services/{{Grupo}}/{{Servicio}}/{{Operación}}
```

Se debe reemplazar `{{dynamics_url}}` por la URL base del entorno de D365 Finance & Operations, p. ej. `https://<entorno>.operations.dynamics.com/`.

#### Cuerpo de la petición (JSON)

```json
{{Ejemplo JSON con un campo por parámetro X++, con el nombre exacto del parámetro}}
```

**Campos:**

- `{{campo}}` *({{tipo}}, {{obligatorio|opcional}})*: {{descripción}}. {{Valor por defecto / longitud máxima, si existen}}

#### Respuesta (JSON)

```json
{{Ejemplo JSON de la respuesta}}
```

**Campos:**

- `{{campo}}` *({{tipo}})*: {{descripción}}

#### Validaciones

- {{condición}} → `{{campo de resultado}}={{valor}}`, `message="{{mensaje, con etiqueta resuelta}}"`
- {{condición}} → `{{campo de resultado}}={{valor}}`, `message="{{mensaje}}"`

{{Nota sobre idioma de los mensajes, si se usan etiquetas}}
