# hal_meeting_summariser

prompt



->
currently the project has the option to upload audio file or text file of the conversation and then generate summary.
update the code so that instead of uploading the audio file there should be button to start recording and then stop recording , a timer should also be visible while recording , then after recording is stopped, it should generate accurate summary that covers all imp points for eg deadlines ,task assigned , problems , solns , and then there shoukd be an option to download the dsummary in formof pdf , and if mail id are provided it can also be used to share the summary pdf via mail to recipients , the project should use device microphone for recording , and raise error before hand only if it is unable to record from the mic , so that after meeting a proper result is gaurenteed.







Act as a Principal Frontend Engineer and Lead UI/UX Designer specialized in defense-industry operational dashboards. Build a complete, single-file (or highly modular, self-contained) production-ready React component with Tailwind CSS for a high-density, aero-military "Command Center" Meeting Summarizer tailored for HAL.

### 1. TECH STACK REQUIREMENTS
- Framework: React (with standard Hooks: useState, useEffect, useRef, useMemo)
- Styling: Tailwind CSS (v3 or v4 compatible)
- Animation/Icons: Lucide React for crisp, thin wireframe telemetry icons

### 2. UI/UX & GLASSMORPHISM DESIGN SYSTEM
- Base Canvas: Deep, unyielding aerospace slate background (`bg-slate-950`).
- Surface Panels: Implement a high-density Bento Grid layout. All panels must feature high-end glassmorphism: `bg-slate-900/40 backdrop-blur-xl border border-white/[0.08] shadow-[0_12px_40px_0_rgba(0,0,0,0.5)] rounded-md`.
- Typography: Sharp, geometric sans-serif for reading body text (`font-sans tracking-wide text-slate-200`). Crisp monospace for telemetry data, IDs, and timestamps (`font-mono text-xs uppercase tracking-wider text-blue-400/80`).
- Visual Aesthetic: No rounded gradients, no playful elements, absolutely NO AI sparkle or magic wand icons. Replace them with technical telemetry crosses, target brackets, or minimalist terminal chevron indicators.

### 3. THE 3-PANEL BENTO GRID LAYOUT ARCHITECTURE
- Header: Include a prominent classification banner ("RESTRICTED / INTERNAL ONLY"), meeting metadata dashboard ( Date, Duration), and the connection status indicator for the local Ollama instance.
- Panel Left (25% Width): Operational Control & Telemetry. Includes audio waveform visualization simulator, meeting index, and a chronological speaker breakdown matrix.
- Panel Center (50% Width): Dynamic Semantic Summary Engine. This is the container where the text streams in. It must support high-density typography, clear section dividing lines, and mock inline definitions for aeronautical terms when hovered.
- Panel Right (25% Width): Strategic Action Items Matrix. Task tokens with distinct priority badges (High/Medium/Low) in muted tactical hues (amber, slate, teal) featuring toggle states for delegation tracking.

### 4. 60 FPS LOCAL OLLAMA STREAM THROTTLING ENGINE
To prevent browser layout thrashing and UI thread locks during rapid token spam from local Ollama execution, you MUST implement the following engineering safeguards within the component:
- Token Buffer Queue: Do not push incoming stream chunks directly into the React state. Route them into a plain JavaScript array `ref` buffer (`tokenBuffer.current`).
- RequestAnimationFrame (rAF) Render Loop: Run an active loop matching the monitor's native refresh rate via `requestAnimationFrame`. Once per frame, check the buffer. If tokens exist, pop a controlled bundle (e.g., 2–4 tokens) and append them to the visual UI state.
- GPU Layer Promotion & Containment: Apply `will-change: transform` and `contain-content` properties via Tailwind CSS styles to the streaming summary panel container to isolate browser repaints from forcing full-page reflows over the backdrop filters.

### 5. EXECUTION CODE SPECIFICATION
- Write the entire component layout out cleanly. Do not use placeholders like "// implement rendering logic here". 
- Provide an integrated mock or functional `fetch` event handler loop that reads a readable stream from the Ollama local stream, parsing the JSON chunks (`data.response` or `data.message.content`) into the specialized performance-throttled queue buffer.
- Ensure the interface looks visually striking, completely operational, dense with information, yet highly readable from the moment it initializes.


-> add feature that there should be option to view previous meeting summaries with the meeting date , time , duration , a generated meeting title.
