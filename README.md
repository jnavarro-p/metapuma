# MetaPuma

**Agente conversacional pedagógico para el apoyo de habilidades metacognitivas en educación superior.**

MetaPuma es un sistema conversacional inteligente desarrollado por Joaquin Navarro Perales como parte de su investigación doctoral en Ciencias de la Computación de la Universidad Internacional de La Rioja (UNIR).

El sistema utiliza Procesamiento del Lenguaje Natural (PLN) para interactuar con estudiantes mediante preguntas abiertas, pistas y retroalimentación. Fue implementado en **Dialogflow ES** e integrado con **Telegram** como interfaz de comunicación.

## Arquitectura conversacional

MetaPuma establece una correspondencia entre los componentes de una estrategia pedagógica y los mecanismos computacionales de Dialogflow ES:

| Componente pedagógico | Implementación |
|---|---|
| Reactivos | Intents |
| Respuestas esperadas | Frases de entrenamiento |
| Pistas | Fallback intents |
| Retroalimentación | Respuestas predefinidas |
| Control de la interacción | Contextos |

El sistema presenta una secuencia de 18 reactivos. Cuando reconoce una respuesta correcta, proporciona retroalimentación y avanza al siguiente reactivo. En caso contrario, ofrece una pista y permite realizar otro intento.

## Contenido del repositorio

El repositorio contiene la configuración exportada de Dialogflow ES:

- `Agent.json`: configuración general del agente.
- `package.json`: metadatos de la exportación.
- `intents/`: archivos JSON con los intents, frases de entrenamiento, respuestas y configuraciones de interacción.

## Implementación

**1. Importar el agente en Dialogflow ES**

Comprimir los archivos de configuración en un ZIP, conservando su estructura original, e importarlos desde *Export and Import → Restore from ZIP* en [Dialogflow ES](https://dialogflow.cloud.google.com/).

**2. Crear un bot en Telegram**

1. Abrir [BotFather](https://t.me/BotFather), la herramienta oficial de Telegram para administrar bots.
2. Enviar el comando `/newbot`.
3. Asignar un nombre y un nombre de usuario al bot.
4. Copiar el token de acceso proporcionado por BotFather.

**3. Conectar Telegram con Dialogflow ES**

1. Abrir el agente importado en Dialogflow ES.
2. Acceder a *Integrations → Telegram*, si esta integración se encuentra disponible.
3. Introducir el token generado por BotFather.
4. Activar la integración y probar el funcionamiento del bot desde Telegram.
