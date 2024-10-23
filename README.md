
# Documentación de vue-speedometer

`vue-speedometer` es un componente de Vue.js para crear indicadores tipo velocímetro altamente personalizables. Ofrece varias opciones de personalización visual y es fácil de usar.

## Tabla de Contenidos

- [Instalación](#instalación)
- [Uso](#uso)
- [Props](#props)
- [Ejemplos](#ejemplos)
  - [Ejemplo Básico](#ejemplo-básico)
  - [Etiquetas y Transiciones Personalizadas](#etiquetas-y-transiciones-personalizadas)
  - [Segmentos Personalizados](#segmentos-personalizados)
- [Características Avanzadas](#características-avanzadas)
- [Recomendaciones](#recomendaciones)

## Instalación

Para instalar `vue-speedometer` en tu proyecto, ejecuta:

```bash
npm install vue-speedometer
```

## Uso

Después de la instalación, importa el componente y utilízalo en tus plantillas Vue:

```vue
<template>
  <VueSpeedometer :value="value" />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const value = ref(300); // Valor inicial para el velocímetro
</script>
```

Este es el uso más básico, donde el velocímetro muestra el valor con la configuración predeterminada.

## Props

Aquí están las propiedades disponibles para personalizar el componente `vue-speedometer`:

| Prop                        | Tipo         | Descripción                                                                                     | Valor Predeterminado |
|-----------------------------|--------------|-------------------------------------------------------------------------------------------------|----------------------|
| **`value`**                  | `Number`     | Valor mostrado por el velocímetro.                                                              | `0`                  |
| **`min-value`**              | `Number`     | Valor mínimo para el velocímetro.                                                               | `0`                  |
| **`max-value`**              | `Number`     | Valor máximo para el velocímetro.                                                               | `1000`               |
| **`segments`**               | `Number`     | Número de segmentos en el velocímetro.                                                          | `5`                  |
| **`needle-color`**           | `String`     | Color de la aguja del velocímetro.                                                              | `'steelblue'`        |
| **`start-color`**            | `String`     | Color inicial del velocímetro (lado izquierdo).                                                 | `'green'`            |
| **`end-color`**              | `String`     | Color final del velocímetro (lado derecho).                                                     | `'red'`              |
| **`ring-width`**             | `Number`     | Ancho del anillo del velocímetro.                                                               | `60`                 |
| **`text-color`**             | `String`     | Color de las etiquetas de texto en el velocímetro.                                              | `'black'`            |
| **`label`**                  | `String`     | Etiqueta de texto que se muestra debajo del velocímetro.                                        | `''`                 |
| **`force-render`**           | `Boolean`    | Fuerza el re-renderizado del componente.                                                        | `false`              |
| **`needle-transition`**      | `String`     | Define la animación de transición de la aguja. (`'easeElastic'`, `'easeQuadIn'`, etc.)           | `''`                 |
| **`needle-transition-duration`** | `Number` | Duración de la animación de transición de la aguja en milisegundos.                             | `500`                |
| **`custom-segment-labels`**  | `Array`      | Etiquetas personalizadas para cada segmento, cada una es un objeto con `{ text, position, color }`.| `[]`              |
| **`custom-segment-stops`**   | `Array`      | Puntos de parada personalizados para los segmentos. Definen dónde ocurren las transiciones de color.| `[]`              |
| **`max-segment-label`**      | `String`     | Etiqueta mostrada en el valor máximo del velocímetro.                                           | `''`                 |
| **`min-segment-label`**      | `String`     | Etiqueta mostrada en el valor mínimo del velocímetro.                                           | `''`                 |
| **`current-value-text`**     | `String`     | Texto personalizado para mostrar el valor actual. Usa `${value}` para interpolar el valor.      | `''`                 |

## Ejemplos

### Ejemplo Básico

```vue
<template>
  <VueSpeedometer
    :value="value"
    :min-value="0"
    :max-value="500"
    :segments="5"
    :needle-color="'red'"
    :start-color="'green'"
    :end-color="'red'"
    :ring-width="30"
    :text-color="'black'"
    :label="'Velocidad'"
  />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const value = ref(200); // Valor mostrado por el velocímetro
</script>
```

### Etiquetas y Transiciones Personalizadas

```vue
<template>
  <VueSpeedometer
    :value="value"
    :min-value="0"
    :max-value="1000"
    :segments="10"
    :needle-color="'blue'"
    :start-color="'yellow'"
    :end-color="'red'"
    :needle-transition="'easeElastic'"
    :needle-transition-duration="4000"
    :custom-segment-labels="[
      { text: 'Bajo', position: 'INSIDE', color: '#555' },
      { text: 'Moderado', position: 'INSIDE', color: '#333' },
      { text: 'Alto', position: 'INSIDE', color: '#999' }
    ]"
  />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const value = ref(750); // Valor mostrado por el velocímetro
</script>
```

### Segmentos Personalizados

```vue
<template>
  <VueSpeedometer
    :value="value"
    :min-value="0"
    :max-value="1000"
    :segments="5"
    :needle-color="'purple'"
    :start-color="'green'"
    :end-color="'red'"
    :custom-segment-stops="[0, 300, 600, 900, 1000]"
    :ring-width="40"
    :max-segment-label="'Sobre marcha'"
    :current-value-text="'Velocidad: ${value}'"
  />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const value = ref(400); // Valor mostrado por el velocímetro
</script>
```

## Características Avanzadas

- **`force-render`**: Utiliza esto para forzar que el velocímetro se re-renderice si estás cambiando propiedades dinámicamente y necesitas que se actualice.
- **`needle-transition` & `needle-transition-duration`**: Estas propiedades permiten animar la aguja mientras el valor cambia. Por ejemplo, usa `'easeElastic'` para una animación suave con una duración de `4000 ms`.

## Recomendaciones

- **Actualizaciones Dinámicas**: Si estás actualizando el valor del velocímetro dinámicamente (por ejemplo, en respuesta a la entrada del usuario o datos en tiempo real), asegúrate de usar `ref` o `reactive` de Vue para mantener los valores reactivos.
- **Renderizado**: Si notas que los cambios no se reflejan de inmediato, considera usar la propiedad `force-render` para asegurarte de que el componente se actualice como se espera.

---

Para preguntas adicionales o para explorar más casos de uso avanzados, no dudes en revisar la documentación oficial o contactar a la comunidad para obtener soporte.
