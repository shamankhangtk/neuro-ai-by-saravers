# NEURO AI by Saravers — Implementation & Design Plan

## Product scope

Build the full NEURO AI educational assistant described in the user's project prompt, preserving the requested English interface labels, module names, developer credits and future-robot architecture. The primary deliverable is a managed Expo/React Native app that runs in Expo Web/Preview and is ready for the Dashboard Android APK/AAB build flow. The UI will be responsive so the same implementation can later be wrapped for a Windows desktop EXE; an EXE artifact is not claimed until a real desktop build is performed.

## Implementation approach

- Keep the fixed Expo Router / React Native / TypeScript / NativeWind starter.
- Replace the starter home tab with a single cohesive app shell that supports mobile one-handed use and a wider desktop/web layout.
- Use local component state plus AsyncStorage for the single-device prototype: active section, settings, reading-list states, chat history and generated draft history. No API keys or passwords are stored client-side.
- Provide reusable service adapters under `lib/` for text generation, image generation and voice/transcription. Calls will target the project's server/API boundary and show explicit not-configured, loading, empty and error states. Built-in Manus LLM/service credentials remain server-side.
- Use React Native SVG for the neural-brain hero artwork and icon-like brand mark so the visual identity works on Android and Web without relying on a screenshot as a fake interface.
- Implement the requested destinations as functional screens/sections: Home, Neuro Chat, Study Tools, AI Image Studio, Library, CreateLab, Coding Help, About and Settings; include the requested future robot simulation/demo panel in About/Settings.
- The first pass prioritizes a complete demonstrable product surface and honest service boundaries. Real AI generation is enabled through the server adapter when the environment is available; otherwise the UI retains the user's input and explains what configuration is missing.

## Design direction: Neon Neural Glass

### Design movement
A premium sci-fi learning dashboard combining glassmorphism, holographic instrument panels and a luminous neural sculpture, directly inspired by the supplied NEURO AI reference image.

### Core principles
1. Learning-first hierarchy: every glow supports a clear learning action.
2. High contrast with calm density: dark navy surfaces, bright cyan action cues and violet emphasis without visual clutter.
3. Consistent system: the same wordmark, card geometry, border glow and microcopy across every module.
4. Trustful AI: service status, privacy, loading and failure states are visible rather than hidden.

### Color philosophy
Near-black navy gives the app a focused study-room atmosphere. Electric cyan signals action, access and learning; violet/magenta marks imagination and creative output. White text is reserved for the reading hierarchy, while muted blue-gray text preserves comfort during long study sessions.

### Layout paradigm
A command-deck shell: a compact brand rail/header, a focused content canvas and contextual action panels. On narrow screens it collapses into a scrollable single-column workspace with a compact menu; on wide screens it expands into a two-column hero and card canvas.

### Signature elements
- A glowing SVG neural coil/brain sculpture with orbit rings and a small cyan-violet pulse.
- Thin gradient-outline glass cards with circular icon wells.
- Section eyebrows, uppercase microcopy and cyan-to-violet action pills.

### Interaction philosophy
Buttons should feel like instruments: clear label, immediate pressed state, and a small visual status change. Navigation never hides the current section. Destructive actions use confirmation; service actions retain user input on failure.

### Animation
Use restrained entrance fades, pulse/orbit loops for the hero only, and short opacity/scale transitions for cards. Avoid continuous animation in long reading areas and avoid motion-dependent information.

### Typography system
Use the platform system sans for reliable native rendering. Apply a strong 32–48px display scale for hero headlines, 22–28px section headings, 15–17px body copy and 11–12px uppercase eyebrow labels with letter spacing. Weight and color create hierarchy before decoration.

### Brand essence
A free, futuristic learning companion for students who want to understand, create and explore in one place. Personality: intelligent, encouraging, imaginative.

### Brand voice
Headlines are concise and aspirational; CTAs are active and specific; helper text is honest and student-friendly. Example lines: “Learn Smarter. Create More.” and “Ask in your language. Learn at your pace.”

### Wordmark & logo
A compact neural-brain outline paired with the two-line wordmark “NEURO AI / BY SARAVERS TEAM”. The icon uses a cyan-to-violet visual split and is repeated in the header, hero and footer/brand panel.

### Signature brand color
Electric cyan `#28D9FF`, paired with violet `#8C55FF` as the ownable gradient edge.

## Project structure

- `app/(tabs)/index.tsx`: primary app shell, navigation state, home and requested workspace screens.
- `app/(tabs)/_layout.tsx`: hidden/native tab configuration so the custom app shell owns navigation.
- `components/neuro-art.tsx`: reusable SVG neural sculpture and brand mark.
- `components/neuro-ui.tsx`: reusable glass cards, section eyebrow, buttons and status rows.
- `lib/neuro-storage.ts`: AsyncStorage persistence for settings, chats and library statuses.
- `lib/neuro-api.ts`: server-side service adapter boundary for chat/image/speech requests with typed errors.
- `server/_core/index.ts`: API host and health endpoint; server routes remain the safe place for platform calls.
- `assets/images/*`: native icon/splash branding assets.
- `plan.md` and `TODO.md`: source requirements and implementation outcomes.

## Build workflow

1. Implement UI and state using the fixed Expo starter.
2. Run TypeScript diagnostics and the project check/lint commands; fix actionable errors.
3. Start Metro/Web and API on the fixed ports 8081/3000 and verify health.
4. Inspect the responsive preview at narrow and wide breakpoints when necessary.
5. Commit the accepted source/configuration to the managed project canonical branch.
6. Use the Dashboard native build action to produce the Android APK/AAB; do not claim an APK before the build result is available.
7. Prepare a desktop packaging handoff using the same web build only after an actual Windows packaging environment is available; do not represent the web preview as an EXE.
