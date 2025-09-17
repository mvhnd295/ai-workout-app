# ai_workout_app
🏋️ AI Workout & Bodybuilding App

An AI-powered fitness app built with Flutter that helps users create personalized workout plans, track exercises, analyze progress, and chat with an AI coach.

✨ Features:

📅 Workout planner (AI-generated routines)

📝 Workout logging (sets, reps, weights)

📊 Progress tracking (charts & analytics)

🧠 AI coach (Q&A, advice, analysis)

☁️ Offline-first (Hive) + cloud sync (Supabase)

👤 Guest mode & authentication (Google, Email, Apple)

🎨 Modern UI with dark/light mode + gamification

🛠️ Tech Stack
Frontend (Flutter)

Flutter (latest stable)

State management → Riverpod

UI Components → flutter_animate, rive, shadcn_ui (if you want web-like components)

Charts → fl_chart

Notifications → flutter_local_notifications

Data Layer

Hive → Local offline DB (workouts, logs, AI cache)

Supabase →

Authentication (Email, Google, Apple, Guest upgrade)

Database sync (Postgres)

Cloud backup for user data

AI Layer

OpenAI GPT-4-mini (Workout planner, progress analysis)

GPT-3.5 (Chat coach Q&A)

dart_openai / REST API calls

Prompting strategy → JSON outputs for structured data

Other

CI/CD → GitHub Actions / Codemagic

Error reporting → Sentry or Firebase Crashlytics

Testing → Unit tests (usecases), Widget tests (screens)

🏗️ Architecture

This project follows Clean Architecture + Feature-first organization with MVVM (via Riverpod).

lib/
 ├── core/                # Shared utilities, errors, theme, router
 ├── features/
 │    ├── auth/           # Authentication + guest mode
 │    ├── workout/        # Workout CRUD + logging
 │    ├── ai/             # AI planner, analyzer, chat coach
 │    ├── progress/       # Charts, stats
 │    ├── settings/       # Preferences, theme, localization
 └── main.dart

📐 Architecture Diagram
   ┌────────────┐       ┌──────────────┐
   │   UI Layer │──────▶│ Presentation │ (Riverpod/Bloc)
   └────────────┘       └──────────────┘
                             │
                             ▼
                      ┌─────────────┐
                      │   Domain    │ (Entities + Usecases)
                      └─────────────┘
                             │
                             ▼
        ┌───────────────────────────────┐
        │             Data               │
        │   - Repositories               │
        │   - Hive (local DB)            │
        │   - Supabase (remote sync)     │
        │   - AI API (OpenAI)            │
        └───────────────────────────────┘
