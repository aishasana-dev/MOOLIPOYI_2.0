
# MMN — Mosquito Mourning Network

A fully functional, Malayalam-first single-page hackathon web app for the absurd Mosquito Mourning Network concept.

## Run

No build step is required. Open `index.html` in a browser. For best results, use VS Code Live Server or any static server.

## Included functionality
- Cinematic intro with localStorage skip/replay
- Responsive premium dark UI
- Mosquito death report form with image preview
- LocalStorage persistence
- Unique MMN IDs
- Simulated AI analysis (explicitly labelled demo/simulated)
- Profile, printable certificate, family tree, notification flow
- Condolence system
- Predefined AI family chat
- Funeral cinematic sequence
- Searchable memorial registry
- Interactive digital cemetery
- MMN CSI case screen
- Mosquito Court with saved verdict
- Live dashboard based on local data
- Reduced-motion accessibility support
- Print-friendly certificate

## Important
The app intentionally does **not** claim real AI image inference. The analysis screen is a simulated demo unless a real model/API is later connected.

# മൂളിപ്പോയി — MOOLIPOYI

> **“കൊന്നത് നിങ്ങൾ… മൂളിപ്പോയത് അവൻ.”**  
> *Every buzz deserves a memory.*

**MOOLIPOYI (Mosquito Mourning Network)** is a Malayalam-first, cinematic interactive web experience for reporting, remembering, and—somehow—mourning mosquitoes. It turns a tiny, ridiculous tragedy into a dark, beautiful night-world of certificates, grieving mosquito relatives, an AI-powered family chat, funerals, and a growing digital cemetery.

Built as a student/hackathon-style frontend with **Google AI Studio**, this is deliberately not a normal multipage site. It is one continuous, sound-driven story where the mosquito, the camera, and the environment carry the user from scene to scene.

## Why does this exist?

Because every mosquito you swatted had dreams. Probably annoying ones. But still.

MOOLIPOYI playfully asks: *what if an ordinary mosquito death received the emotional production budget of a sci-fi memorial film?* The result is a Malayalam-humour experience that combines storytelling, motion, sound, and interactive UI into something memorable enough to make people ask: “Why am I emotionally invested in this mosquito?”

## Experience at a glance

1. A mysterious, sound-enabled intro reveals the MOOLIPOYI world.
2. The user reports a mosquito death with an image and optional details.
3. The image is analysed (with a secure vision model when configured, or a deterministic local fallback).
4. A living mosquito profile and dynamically generated death certificate appear.
5. The fictional mosquito family is identified and notified.
6. The user sends condolences and chats with the family.
7. A quiet funeral leads to a memorial and finally an explorable digital cemetery.
8. Every reported mosquito remains saved locally, so the cemetery grows over time.

## Main features

- Malayalam-first, dark cinematic interface with English reserved for small technical labels and metadata.
- Animated opening sequence with a subtle **Skip Intro** control and user-initiated audio choice.
- Functional mosquito-death report flow: image, name, location, time, cause, and custom cause support.
- AI identification view with animated scanning states, species, confidence, visible features, and intentionally silly observations such as “yes… it is a mosquito.”
- Dynamic mosquito profile, ID, family, age/status, and death cause.
- Story-driven **death certificate** generated from the submitted record, including date, cause, location, certificate number, and verification stamp.
- Interactive fictional mosquito family: reactive character selection and changeable personalities.
- Family notification sequence, condolence messages, and family responses.
- Context-aware AI family chat with fallback behaviour for sympathy, apology, questions, jokes, admissions, anger, sadness, greetings, farewells, and unrelated messages.
- Funeral scene, memorial page, and an interactive night-time digital cemetery with individually stored graves.
- Responsive mobile experience with touch-friendly controls, camera upload support, responsive type, reduced effects where needed, and no intentional horizontal overflow.
- Local persistence for multiple records and audio preferences.

## The scenes

| Scene | What happens |
| --- | --- |
| Intro | A near-black, magical/cinematic reveal introduces the mosquito and the line “കൊന്നത് നിങ്ങൾ… മൂളിപ്പോയത് അവൻ.” |
| Landing | Moonlit memorial world, animated mosquito, primary reporting CTA, and path to memories. |
| Report a Death | Upload an image and capture details such as name, location, time, and cause. |
| AI Identification | Scanning animation, image analysis, classification, confidence, visible features, and fallback-safe results. |
| Mosquito Profile | A cinematic character reveal for the departed mosquito. |
| Death Certificate | A data-driven certificate materialises, receives its stamp, then reveals the family. |
| Family Identification | Meet the reactive family: grandmother, parents, siblings, cousins, and perhaps an alarming family lawyer. |
| Family Notification | A messenger mosquito delivers the news through an animated sequence. |
| Condolences | Leave a saved condolence message; the family responds in context. |
| AI Family Chat | Continue a contextual conversation grounded in the mosquito’s story and chat history. |
| Funeral | A restrained, 20–30 second candlelit memorial moment: “ഇനി മൂളില്ല… പക്ഷേ… ഓർമ്മയുണ്ടാകും.” |
| Memorial | Review the mosquito’s details and leave additional memorial messages. |
| Digital Cemetery | Explore a misty night cemetery; graves glow, buzz, and open their memorials. |

> **Removed by design:** Mosquito CSI, investigation dashboards, evidence collection, detective systems, and court/investigation flows are intentionally not part of MOOLIPOYI.

## One cinematic world, not a pile of pages

Screen changes are designed as motivated scene transitions rather than abrupt replacements. Examples include:

- A mosquito flies toward the reporting CTA and the camera follows it.
- The uploaded image expands into the AI scanning environment.
- The scanned portrait becomes the mosquito profile.
- Profile details dissolve into particles that form the death certificate.
- The certificate pulls back to reveal the family.
- A candle flame grows into the cemetery’s moonlight.
- The camera moves toward a grave and transforms it into a memorial.

The mosquito acts as a recurring visual bridge: flying, hovering, landing, reacting to the cursor, disappearing behind UI, and leaving subtle trails—alive enough to be charming, but not so busy that it becomes the real villain.

## AI behaviour and safe fallback

MOOLIPOYI is designed so an AI-looking interface never pretends to have called an AI service when it has not.

| Capability | When an AI service is configured | When it is not configured |
| --- | --- | --- |
| Image identification | Uses a real vision model/API through a secure backend. | Uses deterministic local classification/fallback data. |
| Family chat | Uses an LLM through a secure backend, with the mosquito story and chat history as context. | Uses a contextual local response system that classifies intent and produces story-consistent Malayalam replies. |

The chat context includes the user’s exact message, emotional tone, question, conversation history, mosquito name, cause of death, family personalities, and the current story state. Fallback replies should vary rather than repeat the same canned sentence.

## Sound system

Audio is part of the experience—not a decorative speaker icon.

- First interaction asks whether to continue with sound or silently; this respects browser autoplay restrictions.
- Audio starts only after the user has made a choice and the `AudioContext` can be resumed.
- A planned `AudioManager` handles master/music/ambience/effects volume, mute, scene audio, fade in/out, crossfades, cleanup, and saved audio settings.
- Scene audio shifts from night ambience and scanning beeps to document/stamp sounds, candle/wind atmosphere, and cemetery ambience.
- Several subtle mosquito buzz variants are used instead of one endless loop. Where supported, Web Audio stereo panning can make the buzz travel with the mosquito.
- If sound cannot load or play, the site should remain functional and gracefully continue in silent mode.

Expected audio organisation:

```text
public/audio/
├── ambience/     # night, family, funeral, cemetery
├── mosquito/     # short, near, far, pass buzzes
├── ui/           # click, hover, confirm, reveal, chime
└── ai/           # scan, beep, completion
```

## Data and persistence

MOOLIPOYI uses browser `localStorage` for persistent, local-only experience data. Refreshing the browser should not erase a reported mosquito; creating more reports should add more graves to the cemetery.

Each mosquito record is designed to retain:

```text
id, name, image, species, confidence, date, time, location, cause,
family, family personalities, chat history, condolence messages,
funeral status, memorial data, cemetery position
```

Audio preference/state is also persisted. Because this is browser storage, clearing site data or changing browsers/devices removes or separates locally saved records.

## Visual and motion language

- **Palette:** near-black `#070B10`, deep blue `#0D1722`, moonlight `#DDE7E5`, electric cyan `#63E6E2`, soft lime `#A8C66C`, dream purple `#8F8CE8`, and extremely sparing coral `#F07872`.
- **Typography:** Noto Serif Malayalam for cinematic headings; Noto Sans Malayalam for UI/body text.
- **Atmosphere:** moonlight, mist, flowers, candles, subtle particles, depth, blur, parallax, light, and rounded dark panels.
- **Interaction:** purposeful hover/click feedback, restrained card tilt, cursor-responsive art, and cinematic text—never motion for motion’s sake.

The intro’s motion language, pacing, camera feel, and reveal style are inspired by the supplied Pinterest reference, while MOOLIPOYI’s visuals, artwork, sound, and story remain original.

## Architecture overview

The source build prompt calls for reusable, state-driven frontend components. A suggested implementation map is:

```text
App / shared application state
├── Intro + LandingScene
├── DeathReport → AIAnalysis → MosquitoProfile → DeathCertificate
├── MosquitoFamily → FamilyNotification → CondolenceSystem → FamilyChat
├── FuneralScene → Memorial → DigitalCemetery
├── SceneTransition + CinematicText + ParticleField
├── InteractiveMosquito
└── AudioManager + SoundControl
```

Suggested component names from the build specification include `InteractiveMosquito`, `SceneTransition`, `AudioManager`, `LandingScene`, `DeathReport`, `AIAnalysis`, `MosquitoProfile`, `DeathCertificate`, `MosquitoFamily`, `FamilyNotification`, `CondolenceSystem`, `FamilyChat`, `FuneralScene`, `Memorial`, `DigitalCemetery`, `ParticleField`, `CinematicText`, and `SoundControl`.

## Technology notes

The confirmed project brief describes a **complete working frontend** created with **Google AI Studio**. The supplied Google AI Studio project view also confirms a **Vite + TypeScript** project structure, including `src/`, `server.ts`, `vite.config.ts`, `tsconfig.json`, `.env.example`, and `package.json`. The build brief explicitly calls for browser `localStorage`, `AudioContext`/Web Audio behaviours, CSS transforms, `requestAnimationFrame`, and Canvas where appropriate.

The brief recommends **Framer Motion or an equivalent animation system**, but does not confirm that a particular library, framework, package manager, hosting provider, vision model, or LLM provider is installed. Those should not be claimed as project dependencies unless verified in the repository.

| Area | Confirmed / specified in the build brief |
| --- | --- |
| Product | Malayalam-first frontend web experience |
| Creation tool | Google AI Studio |
| Build tooling | Vite |
| Language/configuration | TypeScript (`.ts`, `tsconfig.json`) |
| Source/server layout | `src/` and `server.ts` |
| Persistence | Browser `localStorage` |
| Motion | CSS transforms, `requestAnimationFrame`, Canvas where appropriate; Framer Motion or equivalent recommended |
| Audio | Browser audio / `AudioContext`-based flow, with an `AudioManager` design |
| Optional AI | Real vision/LLM only when securely configured through a backend; local deterministic/contextual fallback otherwise |

## Performance and accessibility-minded decisions

- Prefer GPU-friendly transforms and opacity for motion.
- Keep animation loops clean and stop them when scenes change.
- Lazy-load where appropriate; optimise image assets and compress audio.
- Avoid giant video backgrounds and unnecessary WebGL complexity.
- Crossfade and clean audio nodes/listeners to avoid stacked tracks and memory leaks.
- Reduce particle density and simplify mosquito movement on mobile.
- Use touch-friendly controls and responsive vertical layouts.

## Running the project

The project structure confirms Vite and TypeScript, though the supplied material does not reveal the exact scripts or package-manager lockfile. Check `package.json` for the authoritative commands.

At a minimum:

1. Clone or download the repository.
2. Install dependencies using the package manager indicated by the project files (typically `npm install` when using npm).
3. Copy `.env.example` to `.env` only if the implementation includes optional backend AI integration.
4. Start the development server using the script defined in `package.json` (commonly `npm run dev` for Vite projects).
5. Open the app in a modern browser, make an audio choice at the intro, and report a mosquito death. Condolences are optional. Emotional consequences are not.

### Environment variables (only for optional real AI integration)

```dotenv
# .env.example
# Keep real keys on a secure server/backend. Never expose them in browser code.
VISION_API_KEY=
LLM_API_KEY=
```

These names are illustrative placeholders rather than confirmed provider-specific variables. If no secure backend or API key is configured, the local fallbacks should keep the core experience usable.

## Example project structure

The exact repository structure is not confirmed by the build prompt. A sensible layout could be:

```text
.
├── public/
│   └── audio/
├── src/
│   ├── components/
│   ├── scenes/
│   ├── state/
│   ├── services/                # optional secure AI/audio services
│   └── assets/
├── server.ts                    # server entry point present in the generated project
├── vite.config.ts
├── tsconfig.json
├── .env.example                 # only when optional AI integration is implemented
└── README.md
```

## Limitations and safety

- AI image analysis and family chat must not pretend to be live AI when no model is configured.
- Real AI calls should go through a secure backend; **never** place API keys in frontend code, committed `.env` files, or client-side bundles.
- Local fallback results are deterministic/contextual experience logic, not scientific mosquito identification.
- Data is held in the user’s browser storage, not presented as a durable cloud memorial service.
- Audio availability varies by browser, device, user choice, and asset-loading conditions; silent mode is a supported fallback.
- This project is satire and storytelling—not entomological, legal, medical, or grief-support software. Please consult a real expert for anything more serious than a mosquito funeral.

## Demo checklist

For a short demo, show:

1. The intro and sound opt-in.
2. Reporting a mosquito death with a photo and cause.
3. AI analysis, profile, and dynamically generated certificate.
4. A condolence and a context-aware family-chat response.
5. The funeral-to-cemetery transition.
6. A saved grave still present after refresh.

## Credits & acknowledgement

- **Google AI Studio** — used to create the project.
- **Pinterest reference** — provided as motion-language and presentation inspiration for the intro. It guided the desired pacing, illusion, camera feel, and reveal quality; it does **not** imply copied assets, artwork, music, or exact animation.
- **Malayalam language and humour** — the heart of the MOOLIPOYI world.

---

*MOOLIPOYI: a place where the buzz may be gone, but the drama lives forever.*
# Moolipoyi
🦟 **MOOLIPOYI** — We built a whole afterlife for mosquitoes.  Report a death, get an AI identification, meet the grieving family, send condolences, attend the funeral, and visit the digital cemetery.  Because apparently, **killing a mosquito now comes with paperwork, family drama, and consequences.** 💀🕯️  **You killed it. We gave it closure.**

