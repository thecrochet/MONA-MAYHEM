<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Construir el juego con flujos de trabajo agénticos

---

Esta parte es donde Copilot pasa de planificar a implementar. En lugar de escribir código línea por línea, describes lo que quieres y Copilot realiza el trabajo en los archivos que necesita modificar.

## Tarea 1: Conecta la Batalla

<!-- track:vscode:start -->
1. Cambia a modo **Agent** en Copilot Chat.
2. Introduce este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Devuelve Copilot CLI a su flujo de programación normal (o mantente en autopilot si quieres que siga avanzando hasta que lo detengas).
2. Si te sirve, menciona el archivo de la página para aportar contexto adicional: `@src/pages/index.astro`.
3. Introduce este prompt:
<!-- track:cli:end -->

   > Add client-side JavaScript to the battle page that:
   > 1. When the Battle button is clicked, gets both usernames from the inputs
   > 2. Validates both are filled (show error if not)
   > 3. Fetches both users' contribution data in parallel from our API
   > 4. Renders contribution graphs as colored grids — each day is a colored square using GitHub's color palette
   > 5. Shows a VS badge between the two users
   > 6. Displays username, total contributions, and date range for each user
   > 7. Handles loading states and errors
   > 8. Also triggers on Enter key in input fields.
   >
   > Use TypeScript interfaces for the contribution data structure.

<!-- track:vscode:start -->
3. Deja que Agent Mode implemente el cambio en `index.astro`.
4. Revisa los cambios propuestos en la vista de diferencias antes de aceptarlos.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deja que Copilot CLI implemente el cambio en `src/pages/index.astro`.
5. Usa `/diff` para inspeccionar los cambios generados y apruébalos.
<!-- track:cli:end -->

## Tarea 2: Prueba la Batalla

1. Ingresa `octocat` y `torvalds` como los dos nombres de usuario, luego haz clic en **Battle**.
2. Deberías ver ambos gráficos de contribuciones renderizados lado a lado con cuadrículas de colores.
3. Prueba los casos de error:
   - Deja uno o ambos campos vacíos y haz clic en Battle — deberías ver un error de validación.
   - Ingresa un nombre de usuario inválido — la app debería mostrar un error de la API.
4. Prueba presionar **Enter** en cualquier campo de entrada — debería activar la batalla igual que al hacer clic en el botón.

## Tarea 3: Itera con Copilot

Si algo no está del todo bien, dale retroalimentación a Agent directamente en el chat. Por ejemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
Agent Mode gestiona de forma natural los cambios en varios archivos y las iteraciones. Cada prompt de seguimiento se basa en la conversación anterior, así que puedes refinar la implementación sin empezar de cero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Las sesiones de Copilot CLI conservan su historial, por lo que cada prompt de seguimiento se basa en el anterior. Usa `/session` o `/context` para consultar el contexto y `/review` después de una iteración importante si quieres una revisión adicional de errores o pulido.
<!-- track:cli:end -->

## Consejos para Agent Mode

- **Sé específico sobre lo que quieres** — requisitos claros producen mejores resultados.
- **Divide tareas grandes en prompts más pequeños** si Agent se desvía.
- **Revisa los cambios antes de aceptar** — usa la vista de diferencias para entender qué se modificó.
- **Si los resultados no son perfectos, da retroalimentación e itera** — Agent aprende de tus correcciones dentro de la conversación.

## ✅ Parte 3 Completa

Has aprendido a:

- Usar Copilot para **implementar funcionalidades en varios archivos**
- **Iterar sobre los resultados** con prompts de seguimiento concretos
- Gestionar el **ciclo completo de una funcionalidad** — implementación, revisión, pruebas y refinamiento
