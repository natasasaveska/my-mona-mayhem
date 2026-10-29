<!-- l10n-sync: source-file="04-design-vibes.md" -->
# Parte 4: Tematización Orientada al Diseño

---

En esta parte, usarás **Plan Mode** para diseñar una transformación de tema completa, y luego **Agent Mode** para implementarla. Esto es desarrollo orientado al diseño — comienza con la visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el Tema Retro

<!-- track:vscode:start -->
Cambia al modo **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar el modo de planificación.
<!-- track:cli:end -->

Ingresa este prompt:

> I want to transform this page into a full retro arcade experience. Plan a comprehensive visual overhaul that includes: CRT scanline effects on the background, neon glow on the title that pulses like a neon sign, animated VS badge with gradient color shifts, shine/shimmer overlay on the user result cards, float-in animations for input fields, color-shifting loading text between green and purple, and hover glow effects on contribution squares. Keep the dark background (`#0a0a1a`) with green (`#5fed83`) and purple (`#8a2be2`) accent colors. Use a dark theme with the Press Start 2P retro gaming font from Google Fonts.

Copilot generará un plan detallado de implementación cubriendo todos los efectos visuales. **No lo aceptes de inmediato** — revisa el plan e itera:

- Sugiere ajustes en la velocidad de las animaciones (por ejemplo, "Make the neon pulse slower, around 3 seconds")
- Pregunta sobre efectos específicos (por ejemplo, "How will the shimmer overlay work on the cards?")
- Solicita cambios en el enfoque si algo no te convence

<!-- track:vscode:start -->
Cuando estés satisfecho con el plan, cambia al modo **Agent** y pide a Copilot que lo implemente.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Cuando estés satisfecho con el plan, pide a Copilot CLI que proceda con la implementación.
<!-- track:cli:end -->

## Tarea 2: Implementa el Tema

Pide a Copilot que implemente el plan del tema retro arcade que acabas de diseñar:

> Implement the retro arcade theme plan we just designed.

Copilot agregará múltiples animaciones CSS, pseudo-elementos y transiciones en tu hoja de estilos. Esto puede incluir:

- `@keyframes` para scanlines, pulso neón, shimmer y efectos de aparición flotante
- Pseudo-elementos (`::before`, `::after`) para efectos de superposición
- CSS custom properties para los colores del tema
- Transiciones y estados hover para elementos interactivos

Una vez aplicados los cambios, **revisa la vista previa en tu navegador** para ver la transformación completa al estilo retro arcade.

<!-- track:cli:start -->
Cuando se apliquen los cambios, usa `/diff` para revisar los cambios de estilo antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Ajusta el estilo visual

> **⚠️ ¿No ves los cambios?** Si el nuevo tema o las animaciones no aparecen, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y fuerza la recarga (`Ctrl+Shift+R`) en el navegador.

Mantén la vista previa del navegador abierta e itera sobre el diseño. Prueba prompts como:

> The scanline effect is too strong, reduce opacity to 0.03

> Add a subtle electrical flicker to the title text

> The VS badge should pulse more dramatically

Esto es **desarrollo orientado al diseño**: iteras sobre el resultado visual en tiempo real. Cada prompt refina la experiencia hasta que tenga el aspecto adecuado. No te conformes con "suficientemente bueno": ajusta el diseño hasta que la página parezca sacada de una máquina recreativa.

## Tarea 4: Actualiza las Instrucciones

Tus instrucciones deben reflejar las decisiones de diseño importantes para que los prompts posteriores mantengan la coherencia.

<!-- track:vscode:start -->
Pide a Copilot Chat:
> Add a design guide section to copilot-instructions.md describing our retro arcade theme: colors, fonts, animation style
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:
> Update our repository instructions with a short design guide for the retro arcade theme: colors, fonts, animation style, and the rule that new UI should keep the neon aesthetic.
<!-- track:cli:end -->

Haz commit de las instrucciones y los cambios de diseño cuando la página tenga el aspecto esperado.

## ✅ Parte 4 Completa

**Lo que aprendiste:**

- Usar flujos de planificación para esbozar un **sistema de diseño antes de implementarlo**
- **Iterar sobre el resultado visual** con prompts breves de seguimiento
- **Actualizar las instrucciones tras tomar decisiones importantes** para mantener la identidad visual
