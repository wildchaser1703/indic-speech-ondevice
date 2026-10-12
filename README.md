# indic-speech-ondevice

**What latency, accuracy and energy do you actually get running Indian-language
speech entirely on-device, on commodity hardware, on phone-grade audio?**

A reproducible benchmark rig — not a demo. Scripted audio is replayed through
the pipeline rather than spoken into a mic, so results are comparable across
runs, machines and components. Everything is open source and runs locally.

Measured on identical audio under two channel conditions, **16kHz clean and
8kHz narrowband (phone)** — the phone channel being where Indian deployments
actually fail, and which is effectively unbenchmarked in public:

- ASR real-time factor and TTFB · LLM TTFT · TTS RTF and TTFB
- Voice-to-voice p50/p95/p99 · peak RAM · energy per turn
- WER/CER, and **entity-slot accuracy** — whether names, numbers and amounts
  survived, which predicts deployment success far better than WER does
- **Endpointing false-cut rate** — how often the agent talks over the user,
  which code-switched Indic speech provokes badly

Components: AI4Bharat IndicConformer, whisper.cpp, faster-whisper, IndicF5,
Indic Parler-TTS, Kokoro, Silero VAD, Pipecat, llama.cpp/MLX.

**Status: in progress.** Reference bar is sub-800ms voice-to-voice; fully local
on a laptop is expected to land well above it, and the size of that gap is the
point of the exercise.
