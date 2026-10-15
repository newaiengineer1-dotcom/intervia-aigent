# Intervia AI — UI Functionality Validation Matrix (2026-10-14)

This release was reviewed against the prior Intervia requirements and the supplied cockpit screenshot theme.

## Input coverage

| UI input | Key / state | Expected output / downstream behavior |
|---|---|---|
| Groq API key | `api_key_input` | Gateway authentication; secret can also come from Streamlit Secrets |
| Target role | `target_role_input` | Used by evidence/interviewer/report context |
| Company | `company_input` | Optional role/company context and report metadata |
| Interview mode | `mode_input` | Strategy/interviewer question style |
| Interview categories | `categories_input` | Adaptive category balancing and report coverage |
| Duration | `duration_input` | Timer and adaptive target questions |
| Question format | `question_mode_input` | Text or browser speech playback |
| Answer format | `answer_mode_input` | Typed response or Whisper voice response |
| Company/role analysis | `research_input` | Optional analysis using supplied context |
| Camera snapshot | `camera_enabled_input` | Optional presentation-cue analysis |
| Speech language | `speech_language_input` | Browser question speech language / session metadata |
| AI practice-answer length | `answer_length_input` | Coaching answer-length preference |
| CV/Resume upload | `cv` | Candidate evidence + ATS readiness |
| Job Description upload | `jd` | JD requirements + ATS keyword alignment |
| JD paste | `jd_text_input` | Alternate JD input |
| Company-specific context | `company_track_input` | Optional context passed to analysis/report |
| Dashboard reset action | `reset_dashboard_button` | Clears the active session and preserves the API key |
| Typed answer | `answer_input_<turn>` | Coaching + scores + next adaptive question |
| Voice answer | `answer_audio_<turn>` | Whisper transcription + speech metrics + coaching |
| Camera snapshot | `camera_<turn>` | Presentation cues only |

## Output coverage

- Evidence pack: candidate facts, JD requirements, matches, gaps, grounding rule.
- ATS: readiness estimate, keyword match, matched/missing keywords, headings, contact signals, bullet signals, quantified achievements, parseability signal, risk flags, strengths and improvements.
- Interview: question, category, answer, scores, verification notes, suggested better answer, next improvement.
- Voice: transcript, filler highlighting, WPM, filler count and voice-answer history.
- Session snapshot: interview score, ATS readiness, question count, category coverage and priority focus.
- Reports: Markdown and PDF include configuration, ATS/evidence, every turn, scores, suggestions, speech/presentation data and session snapshot.
- Reset: clears active interview state and preserves the API key/deployment configuration.

## Visual accessibility coverage

The final CSS layer explicitly styles text inputs, text areas, selectboxes, multiselect tags, radio controls, checkboxes, buttons, download buttons, uploaders, audio input, metrics, progress bars, alerts, expanders and tabs with high-contrast text and visible borders. Keyboard focus rings and reduced-motion support are included.

## Runtime limitation

Static compilation, AST/project checks, deterministic regression tests, report/PDF smoke tests and ZIP integrity can be validated in the build environment. Live Groq, Whisper, browser microphone, camera and Streamlit Cloud behavior still require deployment with a valid Groq key, network access and browser permissions.

## Clean UI changes (2026-10-14)

- Interview setup is one continuous sidebar panel; no setup tabs remain.
- A single dashboard reset button replaces duplicate reset controls and confirmation widgets.
- Inputs and action buttons use descriptive labels instead of emoji-only labels.
- The luxury Obsidian + Sapphire theme remains configured in `.streamlit/config.toml`.
- Automated regression tests and project verification pass. Live browser rendering and live Groq calls require deployment dependencies and a valid API key and were not performed in the build sandbox.
