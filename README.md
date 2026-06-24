# AI Dental Scheduler — Voice Bot

![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Vapi](https://img.shields.io/badge/Vapi-AI_Voice-6C5CE7?style=flat-square)
![Google Calendar](https://img.shields.io/badge/Google-Calendar_API-4285F4?style=flat-square&logo=googlecalendar&logoColor=white)
![Twilio](https://img.shields.io/badge/Twilio-SMS-F22F46?style=flat-square&logo=twilio&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-Functions-00C7B7?style=flat-square&logo=netlify&logoColor=white)
![Repo](https://img.shields.io/badge/Source-Private-orange?style=flat-square)

**I built an AI receptionist that picks up the phone, talks to patients naturally, checks the dentist's calendar, books appointments, and sends SMS confirmations — without a human touching anything.**

**⚡ At a glance**
- 🎙️ Natural **voice AI** (Vapi) answering real phone calls 24/7 — not a chatbot
- 📅 Checks **live Google Calendar** availability and books the slot mid-call, handling conflicts on the fly
- 💬 Fires an automatic **Twilio SMS** confirmation the moment a booking lands
- ☁️ Fully **serverless** (Netlify Functions) — nothing to host, scales to zero
- 💸 Replaces a $30k/yr receptionist; every missed call is a $500–$2,000/yr patient saved

---

## Why This Matters

Dental offices miss calls. A lot of them. Every missed call is a lost patient worth $500–$2,000/year in recurring visits. Hiring a receptionist costs $30k+/year. This bot handles scheduling 24/7 for a fraction of that.

This isn't a chatbot — it's a **voice AI** that handles real phone calls with natural conversation.

## What I Built

### Conversational Voice Agent (Vapi)
- Integrated **Vapi AI** as the voice layer — handles natural speech recognition and response generation
- The bot understands context: *"I need a cleaning next Tuesday afternoon"* → checks availability → *"I have 2:00 PM and 3:30 PM open. Which works better?"*
- Handles edge cases: no availability, rescheduling, cancellations, questions about services

### Real-Time Calendar Integration
- Connected to **Google Calendar API** to check live availability
- Bot queries open slots in real-time during the call — no stale data
- Books appointments directly on the calendar with patient name, service type, and contact info
- Handles conflicts: if a slot gets taken while the patient is on the phone, the bot offers alternatives

### SMS Confirmation Pipeline
- After booking, automatically sends an **SMS confirmation via Twilio** with:
  - Appointment date, time, and dentist name
  - Office address and contact info
  - Cancellation/rescheduling instructions

### Serverless Backend (Netlify Functions)
Built the entire backend as **serverless functions** — no server to manage, scales automatically:

| Function | What It Does |
|----------|-------------|
| `check-availability` | Queries Google Calendar for open slots in a date range |
| `book-appointment` | Creates the calendar event + triggers SMS confirmation |
| `status` | Health check endpoint for monitoring uptime |
| `diagnose` | Troubleshooting endpoint that validates all API connections |

### Monitoring Dashboard
- Built a static HTML/JS dashboard for monitoring system health
- Shows API connection status, recent bookings, and error logs
- One-page setup instructions for the dental office

## How a Call Works

```
Patient calls the office number
         │
         ▼
┌──────────────────────────┐
│       Vapi AI Voice      │
│  "Hi! I'd like to book   │
│   a cleaning for next    │
│   Tuesday afternoon."    │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│   check-availability()   │
│   Google Calendar API    │
│   → "2:00 PM and 3:30   │
│     PM are available"    │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│    book-appointment()    │
│   Creates calendar event │
│   with patient details   │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│      Twilio SMS          │
│  "Your appointment is    │
│   confirmed for Tue at   │
│   2:00 PM. See you then!"│
└──────────────────────────┘
```

## Tech Stack

`JavaScript (ES6+)` · `Vapi AI` · `Google Calendar API` · `Twilio SMS` · `Netlify Functions` · `Supabase` · `HTML/JS Dashboard`

---

> *Closed source. This is a real business automation tool — demo and source code available for serious inquiries.*
