# NEURO AI by Saravers — Delivery TODO

## 1. Brand, shell and responsive visual system
- [ ] The app is named “NEURO AI” with “BY SARAVERS TEAM”, tagline “Knowledge for Everyone.”, supporting slogan “Learn. Explore. Imagine. Create.”, mission “A Free Gift for Students.”, developer Sara Abdul Latif and institution Government Girls Higher Secondary School, Ghotki.
- [ ] The main interface is English, while the assistant can follow the student's language, including English, Urdu, Roman Urdu, Sindhi and other supported languages.
- [ ] The visual system uses deep navy/near-black backgrounds, electric blue, neon cyan, violet, purple and subtle magenta gradients; glowing borders; soft light; glassmorphism; rounded corners; modern typography; a futuristic neural-brain/AI sculpture; subtle grid/neural connections; tasteful animations; and responsive laptop, desktop, tablet and mobile layouts.
- [ ] The header includes the neural-brain logo, brand text, Home, Neuro Chat, Study Tools, AI Image Studio, Library, CreateLab, Coding Help, About, Settings and a glowing Get Started button; mobile navigation has a working hamburger menu; every item opens its destination.
- [ ] The native icon, splash and favicon use the NEURO AI identity without baked-in rounded corners.

## 2. Homepage
- [ ] The hero includes the badge “YOUR AI LEARNING COMPANION”, heading “Learn Smarter. Create More.”, supporting text “Your personal AI assistant for questions, study, coding, creativity and discovery.”, Start Exploring and Explore Features buttons, and a premium cyan/blue/purple/magenta neural visual over a dark grid.
- [ ] The hero includes the three quick-benefit cards: AI Study Assistant — “Get help with your studies, anytime.”; Multilingual Support — “Ask in your language and get answers in yours.”; Creative Tools — “Generate images, ideas and more.”
- [ ] The feature section is titled “Everything You Need to Learn” with subtitle “One intelligent platform for learning, creativity and discovery.”
- [ ] Feature cards exist with icons, descriptions, actions and working destinations for Neuro Chat, Study Assistant, AI Image Studio, Neuro Library, CreateLab and Coding Help.

## 3. Neuro Chat
- [ ] The chat workspace supports New chat, conversation history, previous-chat search, rename, delete with confirmation, text input, send, Enter-to-send and Shift+Enter newline.
- [ ] The workspace shows loading, errors, timestamps, copy answer, regenerate answer and stop-generation behavior where supported; it keeps the input on errors.
- [ ] Markdown-like headings, lists and code blocks are readable, with a Copy Code/Copy answer action where applicable.
- [ ] The responsive sidebar works on wide and narrow layouts.
- [ ] Chat calls use a real connected AI service when configured, follow the student's language and do not show fake AI success. Unavailable service/API/network errors are explained clearly.

## 4. Multilingual and voice assistant
- [ ] Settings exposes a language preference while chat can follow the language used by the student.
- [ ] Voice Assistant includes microphone, listening/stop controls, editable speech-to-text transcription, AI answer, text-to-speech playback, play/pause, voice/language preferences, permission/error messaging and a visible active-mic state.
- [ ] The app does not secretly record/store conversations and clearly indicates unsupported browser/device voice capabilities.

## 5. Study Assistant
- [ ] The study workspace includes Topic Explainer, Notes Generator, Chapter Summarizer, MCQ Generator, Quiz Creator, Flashcard Generator, Revision Planner, Viva Preparation, Presentation Outline Generator and Assignment Planning Assistant.
- [ ] Students can enter topic, subject, class level and preferred explanation length.
- [ ] Results are readable, organized and support copy plus download/export where practical.
- [ ] The UI makes clear that AI educational content should be checked for accuracy.

## 6. AI Image Studio
- [ ] Image Studio includes prompt, optional negative prompt, style, aspect-ratio selection, Generate, loading/progress, preview, Download, Regenerate and clear error handling.
- [ ] Style options include realistic, illustration, 3D, educational diagram, futuristic, cartoon and digital art.
- [ ] The real image service is used when configured; failed/temporary results are not presented as generated images.

## 7. Neuro Library
- [ ] Library includes featured books, browse, search by title/author, genre/subject filters, sorting, covers, titles, authors, descriptions and publication details.
- [ ] A book-details flow exists with My Reading List and Want to Read, Reading and Completed statuses.
- [ ] “Ask Neuro About This Book” uses available book information.
- [ ] Preferences persist for a single-device prototype; legitimate book data such as Open Library can be used where connected; the app does not claim full-text access when it is not legally available.

## 8. CreateLab
- [ ] CreateLab is labeled “One Prompt. Multiple Possibilities.” and lets students select an output type and enter a prompt.
- [ ] Output types include Project Ideas, Presentation Outlines, Report Drafts, Poster Concepts, Website Starter Code, Practice Quizzes, Study Guides, Viva Questions, Creative Writing and Educational Explanations.
- [ ] Results appear in organized cards or document-style output with copy, regenerate and export actions where practical, using the actual AI backend when configured.

## 9. Coding Help
- [ ] Coding Help covers HTML, CSS, JavaScript, Python, responsive web development, layouts, debugging, error explanations, optimization and beginner concepts.
- [ ] Code is displayed in readable syntax-highlighted blocks with Copy Code, purpose and run instructions.
- [ ] Arbitrary server-side code is never executed.

## 10. Future Neuro Robot architecture
- [ ] The app includes a clearly labeled simulation/demo mode and configurable modules for future audio playback and movement commands.
- [ ] It does not claim physical robot integration is working without tested hardware; disconnects fail safely and the core app remains useful without a robot.

## 11. Settings and personalization
- [ ] “Make It My Way” includes preferred language, simple/detailed answers, light/dark theme if supported, voice playback preference, image-generation preferences, chat-history controls, clear-history confirmation and privacy information.
- [ ] API keys, passwords and sensitive credentials are never stored in browser/native storage.

## 12. About, credits and footer
- [ ] About explains that Neuro AI by Saravers is an educational AI platform for questions, difficult concepts, coding practice, books and creativity; states the mission “To make learning more accessible, interactive and inspiring for students.”; and includes Accessible Learning, Creativity, Technology for Education, Student Empowerment and Responsible AI.
- [ ] The app clearly distinguishes available features from features still in development.
- [ ] Credits display “Developed by Sara Abdul Latif”, Saravers Team and “An educational AI project associated with Government Girls Higher Secondary School, Ghotki.” without implying official school endorsement.
- [ ] Footer includes logo, brand, “Knowledge for Everyone.”, optional “Learn. Explore. Imagine. Create.”, developer/institution, Home/About/Features/Library/Privacy Policy/Terms of Use/Contact links and dynamic current-year copyright.

## 13. Backend, safety and build readiness
- [ ] AI provider calls stay behind the server/API boundary; environment values are used instead of hardcoded secrets; an `.env.example` and local setup instructions are provided when server integrations are added.
- [ ] Input validation, sensible request limits/rate limiting, security headers, appropriate CORS, loading/empty/error states and honest optional/required-service documentation are present.
- [ ] The fixed Expo ports 8081 (Metro/Web) and 3000 (API) remain unchanged; `pnpm db:push` and applicable checks run successfully before first OAuth/API traffic.
- [ ] TypeScript diagnostics are registered and actionable errors are fixed.
- [ ] The accepted source/configuration is committed to the managed canonical branch.
- [ ] Android APK/AAB is produced only through the actual Dashboard native build result.
- [ ] A Windows EXE is only claimed after a real desktop packaging build; until then, provide the reusable Expo Web/desktop packaging handoff without mislabeling Preview as an EXE.

## 14. Secure admin login and prompt editor
- [ ] Login tab displays a prefilled `saraverse.edu.gov.pk` username field and password field, but the password remains a protected server-side secret and is never bundled into APK/EXE/browser code.
- [ ] Login validates credentials server-side, rate-limits attempts, returns a short-lived admin session token, supports logout and rejects unauthenticated editor requests.
- [ ] Authenticated Prompt Editor accepts a plain-language feature/content request and returns a reviewable proposal describing affected screens, implementation steps, risks and approval requirements.
- [ ] The editor never executes arbitrary code, reveals secrets, deletes data or falsely claims that production source was changed; actual accepted changes still require a reviewed project update and build/publish step.
- [ ] Voice input/playback provides browser capability detection, permission/error feedback, language mapping, duplicate-submit protection and a native fallback message when the device adapter is unavailable.
- [ ] Accuracy and safety copy tells students to verify important facts, preserves failed inputs for retry, and never presents an unavailable service as a successful result.
