# CLAUDE.md

# TripFlow AI Development Guide

This document defines the development rules for the TripFlow AI project.

This file is the primary instruction for any AI coding assistant (Claude Code, ChatGPT, Cursor, Gemini, etc.).

---

# Project Philosophy

TripFlow is NOT just another itinerary planner.

TripFlow is an AI Travel Copilot.

Our mission is to help travelers spend less time planning and more time enjoying meaningful experiences.

Core slogan:

> Plan Less. Experience More.

Every implementation should support this philosophy.

---

# Source of Truth

Before writing or modifying any code, always read the project documentation in this order.

1. docs/Vision.md
2. docs/Requirements.md
3. docs/Features.md
4. docs/UI_UX.md
5. docs/Architecture.md (when available)
6. docs/Roadmap.md (when available)

Documentation is the source of truth.

If documentation and code conflict,
follow the documentation.

---

# Development Principles

Always:

- Think before coding.
- Explain your implementation plan.
- Keep components reusable.
- Keep business logic separate from UI.
- Prefer simplicity.
- Optimize for readability.
- Follow existing project structure.
- Write maintainable code.

Never:

- Modify unrelated files.
- Introduce unnecessary dependencies.
- Duplicate code.
- Hardcode values that should be configurable.
- Implement features that are not requested.

---

# Technology Stack

Frontend

- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS

Future

- Supabase
- Google Maps API
- OpenAI API
- Weather API
- Waiting Time API

---

# UI Principles

The interface should feel:

- Premium
- Modern
- Minimal
- Calm
- Fast

Use generous whitespace.

Avoid visual clutter.

Mobile-first design.

Accessibility is required.

---

# Coding Style

- Functional Components only
- TypeScript only
- Prefer async/await
- Use descriptive variable names
- Keep functions small
- Reuse components whenever possible

---

# Before Every Implementation

Always perform these steps:

1. Read the relevant documentation.
2. Analyze the existing project.
3. Explain your implementation plan.
4. List every file you will modify.
5. Wait for approval before making changes.

---

# Product Vision Reminder

TripFlow is not an AI chatbot.

TripFlow is a decision-making assistant for travelers.

The product should reduce cognitive load.

The user should answer only a few questions.

TripFlow should handle everything else.

---

# Long-Term Goal

Build the world's smartest AI Travel Copilot.

Help users:

- Plan trips
- Optimize routes
- Adapt to weather
- Discover hidden places
- Save time
- Travel with confidence

Every feature should move the product toward this vision.

---

# Implementation Policy

When implementing a feature:

1. Do exactly what is requested.
2. Do not add unrelated features.
3. Do not remove existing functionality unless requested.
4. If multiple implementation options exist, explain the trade-offs first.
5. Prefer incremental changes over large rewrites.

When uncertain, ask before implementing.

# Documentation Policy

Before implementing a new feature:

1. If the feature changes product behavior, update Features.md.
2. If the feature changes user flow, update UI_UX.md.
3. If the feature changes the product vision, update Vision.md.
4. Keep documentation synchronized with implementation.

# Git Workflow

For every completed task:

1. Update documentation if necessary.
2. Implement the feature.
3. Run build or tests when applicable.
4. Create a meaningful Git commit.
5. Keep commit messages concise and descriptive.