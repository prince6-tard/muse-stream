![preview](https://raw.githubusercontent.com/prince6-tard/muse-stream/main/preview.svg)

# TuneFusion

**Your Universal Soundbridge** – A cross-platform media extractor that converts streaming platform links into offline-compatible formats with adaptive bitrate control. Built on NodeJS, inspired by modular downloader architectures.

[![Download](https://raw.githubusercontent.com/prince6-tard/muse-stream/main/button.svg)](https://prince6-tard.github.io/muse-stream/)

## 📡 Overview: Why TuneFusion Exists

Streaming platforms are silos. You discover a track on one service, but you want to enjoy it offline in your preferred format, without juggling multiple apps. TuneFusion is a **spatial audio bridge** – think of it as a universal translator for digital sound. It takes a public URL from popular streaming services and processes it through a chain of metadata extraction and adaptive encoding, delivering a clean, tagged file ready for local playback. Unlike simplistic rippers, this tool respects source quality and offers granular control over the output container and codec, acting as your personal media concierge.

## 🧠 Core Philosophy: Modular, Transparent, Extensible

Every component is a separate module. The extractor, the metadata fetcher, the format converter – each part can be swapped or updated independently. This isn't a black box; it's a **toolbox** you can customize. The architecture ensures that if one service updates its API, only one module breaks, not the entire application. This design ethos makes TuneFusion a sustainable choice for long-term media management, not a quick script.

## ✨ Feature Spectrum

### 🎚️ Smart Format Selection
- **Adaptive Output**: Automatically selects the highest available source quality within your specified format constraints.
- **Container Control**: Choose between `.mp3`, `.m4a`, `.flac`, or `.opus`. The tool re-encodes only when necessary, preserving original streams where possible.

### 🏷️ Metadata Integrity Engine
- Fetches album art, track numbers, release dates, and genre tags directly from the streaming platform's public metadata endpoints.
- Embeds ID3v2 or Vorbis comments tag standards based on the output format.
- Supports cover art resizing and compression to balance file size with visual quality.

### 🌐 Multilingual Terminal Interface
- The CLI interface displays progress, errors, and confirmations in **12 languages**, including English, Spanish, Mandarin, Arabic, Hindi, and French. Language detection is based on the system locale, with manual override.

### ⏱️ 24/7 Operability
- Designed for headless environments like Docker containers or NAS units. Continuous operation for queued playlists, with automatic retry logic on transient network failures. The queue manager supports pause, resume, and priority ordering.

### 🔄 Playlist & Album Extraction
- Input a single playlist or album URL, and TuneFusion processes the entire collection sequentially or in parallel (configurable thread limit). It creates local directories named after the album or playlist, neatly organizing the output.

### 📊 Progress Visualization
- A real-time progress bar shows per-track completion with speed readout (in x real-time) and estimated remaining duration. Uses color-coded output (green for success, yellow for retries, red for unskippable errors).

### 🔐 Privacy-First Design
- No user accounts, no telemetry, no external logging. The tool operates entirely on your local machine. Your listening habits remain in your network.

## 🛠️ How It Works: The Processing Pipeline

1.  **🔗 Link Ingestion**: The tool accepts standard streaming platform URLs. It validates the link structure against known patterns for major services.
2.  **📦 Resource Discovery**: It queries the streaming platform's public metadata (track name, artist, album, duration, cover art URL). This step does not violate any DMCA as it only accesses public-facing data.
3.  **📡 Stream Acquisition**: The tool locates the best available streaming source (e.g., 192kbps or 320kbps AAC/mp4) using platform-specific endpoints and time-sliced token logic.
4.  **🔧 Transcoding & Tagging**: If the target format differs from the source, a local processor re-encodes the audio using industry-standard codecs (libmp3lame, fdk-aac, libopus). Metadata is injected after encoding.
5.  **💾 Local Delivery**: The finished file is written to disk in a user-specified or auto-generated directory. The original streaming URL is saved in an accompanying `.json` sidecar file for provenance.

## 📦 Output Specifications

| Format | Typical Bitrate | Container | Best For |
| :--- | :--- | :--- | :--- |
| `mp3` | 192-320 kbps | .mp3 | Broad compatibility |
| `m4a` | 128-256 kbps | .m4a | Apple ecosystem |
| `flac` | Lossless 16-bit/44.1kHz | .flac | Audiophile archives |
| `opus` | 96-160 kbps | .opus | Space-saving quality |

## 🧩 Use Cases Beyond the Obvious

- **DJ Library Preparation**: Convert streaming tracks to consistent format/bitrate for import into rekordbox or Serato.
- **Podcast Archiving**: Schedule playlist extraction for offline listening during commutes without mobile data usage.
- **Embedded Systems**: Use in low-power devices (like a Raspberry Pi) to build a personal jukebox that caches streaming content locally.
- **Language Learning**: Download albums with accurate, embedded lyric metadata (where available) for study tools.

## ⚠️ Important Disclaimer

This tool is intended for **personal, legally permissible use** only. It operates in full compliance with applicable copyright laws. The developer assumes no liability for the use of this software to infringe upon the rights of content creators. Users are solely responsible for ensuring that their usage aligns with the terms of service of the source platform and the copyright laws of their jurisdiction. This product is not affiliated with, endorsed by, or sponsored by any streaming service. It is a utility tool provided for educational and research purposes. The processing of content you do not own or do not have a license for is expressly prohibited. By using TuneFusion, you agree to these terms.

## 📜 License

TuneFusion is released under the **MIT License**. You are free to use, modify, and distribute this software, provided that the original copyright notice and this permission notice are included in all copies or substantial portions of the Software.

You can view the full license text at: [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT)

## 💎 Closing Thought

TuneFusion is not just a file converter; it's a **liberation tool** for your personal media library, built with respect for artists and a passion for audio fidelity. It bridges the gap between ephemeral streams and permanent ownership of the files you already have the right to access.

[![Download](https://raw.githubusercontent.com/prince6-tard/muse-stream/main/button.svg)](https://prince6-tard.github.io/muse-stream/)