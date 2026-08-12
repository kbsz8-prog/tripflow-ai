Guiding Principle

Don't plan the whole trip. Understand the trip, and help decide what's next.


---

# 5. `docs/UI_UX.md`

이 파일은 이번 방향 전환에서 **특히 중요**해. 기존 itinerary planner UI를 그대로 유지하면 Vision과 실제 제품 경험이 서로 충돌하기 때문에, 앞으로의 화면 설계 기준을 아래처럼 잡는 게 좋아.

```md
# TripFlow AI — UI / UX

## 1. Design Philosophy

TripFlow is not a traditional itinerary planner.

The UI should not make travelers feel like they are managing a schedule.

Instead, the experience should feel like having an intelligent travel companion who understands:

- Where you are
- What time it is
- What you have already done
- What you want
- What is happening around you
- What you might want to do next

The primary question of the UI is:

> **"What should I do next?"**

---

# 2. Core UX Principles

## 2.1 Context Over Schedule

The current situation is more important than a fixed itinerary.

The UI should prioritize:

- Current location
- Current time
- Current activity
- Available time
- Relevant recommendations

A full itinerary should be secondary.

---

## 2.2 Recommendation Over Navigation

The user should not need to search through many screens to find something useful.

TripFlow should proactively surface relevant actions.

---

## 2.3 Conversation + Action

AI responses should not end with text.

They should lead to actions.

Example:

```text
User:
"I'm hungry and don't want to walk much."

        ↓

TripFlow understands intent

        ↓

Recommendation Card

┌─────────────────────────────┐
│ Recommended for you         │
│                             │
│ Restaurant A                │
│ 8 min walk                  │
│ ⭐ 4.6                      │
│ Low wait                    │
│                             │
│ [Go] [Save] [More]          │
└─────────────────────────────┘

        ↓

Map / Navigation
2.4 User Control

TripFlow recommends.

The traveler decides.

The AI should never make the traveler feel locked into a plan.

2.5 Minimal Planning

The UI should make it possible to use TripFlow without creating a detailed itinerary.

Users should be able to provide:

"We're staying here."

"We want to visit these places."

"We like good food."

and let TripFlow handle the rest.

3. Information Architecture

The primary navigation should be simple.

TripFlow
│
├── Now
│
├── Map
│
├── Trip
│
├── Saved
│
└── Profile

AI interaction should be available throughout the application rather than isolated in a separate chatbot screen.

4. Primary Screen — Now
Purpose

The Now screen is the heart of TripFlow.

It answers:

"What is happening right now, and what should I do next?"

Content Priority
1. Current Context

Show:

Current location
Current time
Weather
Current activity
Available time
2. AI Recommendation

Show the most relevant next action.

3. Alternatives

Provide a small number of alternatives rather than an overwhelming list.

4. Map Context

Show relevant locations visually.

Example
┌─────────────────────────────────┐
│ TripFlow                     ☰  │
├─────────────────────────────────┤
│                                 │
│  📍 Central Park                │
│  3:12 PM                        │
│  ☀️ 24°C                         │
│                                 │
│  What would you like to do?     │
│                                 │
│  ┌───────────────────────────┐  │
│  │ Ask TripFlow...           │  │
│  └───────────────────────────┘  │
│                                 │
│  Recommended for you            │
│                                 │
│  ┌───────────────────────────┐  │
│  │ Museum                     │  │
│  │ 12 min away                │  │
│  │ Short wait                 │  │
│  │                            │  │
│  │ [Go] [Save]               │  │
│  └───────────────────────────┘  │
│                                 │
│  Nearby                         │
│  [Coffee] [Park] [Food]        │
│                                 │
└─────────────────────────────────┘

The Now screen should feel alive and context-aware.

5. Map Screen
Purpose

The Map screen provides spatial context.

It should answer:

"Where should I go?"

The map should not simply display every possible place.

It should highlight contextually relevant places.

Map Elements
Current location
Recommended destination
Saved places
Nearby discoveries
Route
Transportation mode
Travel time
Estimated arrival time
Map Interaction

A user should be able to:

Select a recommendation.
Preview the route.
Change transportation.
Save the location.
Start navigation.

The map should work together with the AI rather than exist as an isolated feature.

6. Trip Screen
Purpose

The Trip screen contains the broader trip context.

It is not intended to be the primary day-to-day interaction.

It may include:

Destination
Dates
Accommodation
Saved places
Reservations
Important plans
Travel preferences

The Trip screen answers:

"What do I have for this trip?"

Flexible Itinerary

If an itinerary exists, it should be treated as flexible context rather than a strict schedule.

Example:

Today

✓ Hotel
✓ Central Park

Optional
→ Museum
→ Coffee
→ Dinner

Flexible
→ Explore nearby

The user should always be able to change the plan.

7. Saved Screen
Purpose

Collect places and ideas the traveler may want to visit.

Categories may include:

Places
Restaurants
Cafes
Shops
Activities

Saved items should contain enough context to become useful later.

For example:

Location
Category
User notes
Distance
Opening hours
Travel relevance
8. AI Interaction

AI should be available from every major screen.

The user should not have to enter a dedicated "AI Chat" section to interact with TripFlow.

Persistent AI Input

A lightweight input may be available at the bottom of the screen:

┌───────────────────────────────────┐
│ Ask TripFlow...              🎙️   │
└───────────────────────────────────┘

Users can enter natural language.

Examples:

"What should we do now?"
"I'm hungry."
"Find somewhere nearby."
"I don't want to walk."
"Let's skip the museum."
"What's good around here?"
9. Recommendation Cards

Recommendations should be actionable.

A recommendation card may include:

Name
Category
Distance
Travel time
Opening status
Waiting time
Rating
Why it is recommended
Primary action

Example:

┌───────────────────────────────┐
│ ☕ Blue Bottle Coffee          │
│                               │
│ 7 min walk                    │
│ Open now                      │
│                               │
│ Why this?                     │
│ You're nearby and have        │
│ about 45 minutes available.   │
│                               │
│ [Go] [Save] [More]            │
└───────────────────────────────┘

The "Why this?" explanation is important for user trust.

10. Dynamic Re-planning UX

When the situation changes, TripFlow should not simply show an error.

It should explain the change and offer alternatives.

Example:

⚠️ Your restaurant now has a 50-minute wait.

TripFlow suggests:

1. Try another nearby restaurant
2. Explore the nearby market first
3. Keep the reservation and change the current plan

The traveler chooses the response.

11. Plan Changes

When a user changes their mind, the UI should make it easy.

Example:

Current Plan

Museum
   ↓
Lunch
   ↓
Shopping
   ↓
Hotel

User:

"Let's skip the museum."

TripFlow:

Museum removed.

Updated plan:

Nearby Coffee
   ↓
Lunch
   ↓
Shopping
   ↓
Hotel

The change should feel lightweight rather than requiring the user to rebuild the entire itinerary.

12. Context Visualization

TripFlow should expose enough context to make AI recommendations understandable.

Possible context indicators:

📍 Location
🕒 Time
☀️ Weather
🚶 Walking
🚇 Transit
🍽️ Reservation
⏱️ Available Time

The UI should avoid overwhelming users with technical details.

Only context relevant to the current decision should be emphasized.

13. Mobile-First Experience

Travelers primarily use TripFlow while moving.

Therefore, the core experience should be mobile-first.

Priorities:

Fast access
Large touch targets
Minimal typing
Map integration
Voice input
Clear recommendations
One-tap actions

The user should be able to interact with TripFlow while walking or moving between locations.

14. Desktop Experience

Desktop should focus more on:

Trip setup
Planning
Saved places
Trip overview
Detailed map exploration
Preference management

Desktop can provide a richer workspace.

Mobile should prioritize real-time travel assistance.

15. Voice Interaction

Voice is a future priority because travel is a hands-busy, eyes-busy environment.

Examples:

"What's nearby?"

"Take me somewhere good for lunch."

"I'm tired. What's easy?"

"What's next?"

The goal is to make TripFlow feel more like a companion than an app.

16. Proactive UX

Future versions may proactively surface relevant information.

Examples:

Rain expected in 30 minutes.

You are 10 minutes away from a saved indoor attraction.

or:

You have 90 minutes before dinner.

There are three nearby places that fit your preferences.

Proactive recommendations should be:

Relevant
Timely
Explainable
Non-intrusive
Easy to dismiss
17. Trust & Transparency

AI recommendations should explain why they are being made.

Example:

Recommended because:

You're nearby
It is open now
The weather is suitable
You saved it earlier
You have enough time
It matches your preferences

Users should understand that TripFlow is making a recommendation, not a command.

18. UX Evolution

The UI should evolve together with the product.

Early Stage
Trip
 ↓
Saved Places
 ↓
Basic Recommendations
Assistant Stage
User
 ↓
Conversation
 ↓
Recommendation
 ↓
Action
Agent Stage
Context
 ↓
AI Agent
 ↓
Recommendation
 ↓
User Decision
 ↓
Updated Context
Travel Jarvis Stage
Traveler
      ↕
AI Travel Agent
      ↕
Memory
      ↕
Context
      ↕
Tools
      ↓
Proactive Assistance
19. UX Principles Summary

TripFlow should feel:

Simple
Context-aware
Conversational
Adaptive
Personal
Trustworthy
Action-oriented
Non-intrusive

TripFlow should not feel:

Like a rigid itinerary
Like a spreadsheet
Like a generic chatbot
Like a search engine
Like a complicated trip management system
Core UX Principle

Don't make the traveler manage the trip.
Let TripFlow understand the trip and help with what's next.