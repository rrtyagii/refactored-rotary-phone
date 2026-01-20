# Infomatic

Infomatic is an iOS app that helps you learn technical topics (e.g., RAG, tokenization) through an Instagram-like scrollable feed. Content is sourced from a preloaded dataset and is designed to work offline-first.

## Goals

- Offline-first learning feed (scrollable, “post” format)
- Summarize topics from a predefined/preloaded dataset
- Keep local dataset small and bounded (target: ~50,000 words / ≤ 500MB)
- Optional follow-up Q&A per topic (on-device model)

## MVP Scope

- SwiftUI feed UI
- Topic detail view
- Load a local dataset (initially: curated Wikipedia topic extracts)
- Search and bookmarks (optional for MVP)

## Tech Stack (Initial)

- Platform: iOS
- UI: SwiftUI
- Language: Swift
- Storage:
  - Dataset: bundled JSON (read-only)
  - User data (later): SwiftData or Core Data (bookmarks, progress, history)

## Project Structure (Suggested)

- `InfomaticApp/`
  - `App/` (entry point)
  - `Views/` (Feed, Topic Detail, Follow-up Q&A)
  - `Models/` (Topic, Chunk, etc.)
  - `Services/` (Dataset loader, retrieval, model manager)
  - `Resources/` (dataset JSON, images)

## Dataset Plan

- Start with a curated list of topics (30–80)
- Store per-topic:
  - Title
  - Short summary (TL;DR)
  - Full text
  - Optional: chunked excerpts + metadata for retrieval

## Roadmap

1. **UI + Local Dataset**
   - Build the feed and topic pages
   - Load topics from bundled JSON

2. **Retrieval (Offline)**
   - Chunk topics and implement similarity search (embeddings)

3. **On-device Q&A (Optional)**
   - Add a local small language model for follow-up questions
   - Lazy-load model, handle memory pressure, cap context/output

## Getting Started

1. Open the project in Xcode.
2. Select an iOS Simulator or a connected iPhone.
3. Press **Run**.

## Contributing

- Keep changes small and easy to review.
- Prefer SwiftUI patterns and simple, testable services.
- Write clear commit messages.

## License

TBD

