# Nest

Desktop repair shop management platform. Native Tkinter GUI that brings RepairDesk ticketing, AI-powered ticket analysis, hardware diagnostics, and business intelligence into a single application.

Predecessor to [Anvil](https://github.com/phnxsystms/Anvil).

## Features

- **RepairDesk Integration** — full ticket lifecycle (create, update, notes, status), customer and inventory management, batch operations with intelligent caching
- **NestBot AI Assistant** — multi-provider (Claude, OpenAI, Gemini), ticket analysis, diagnostic suggestions, repair pattern recognition, business metrics
- **Hardware Diagnostics** — PC (storage, RAM, drivers, boot performance, registry), Android, and iOS diagnostic tools built-in
- **Appointment Scheduling** — Google Calendar integration with two-way sync
- **Business Analytics** — revenue per ticket, profit margins, customer lifetime value, demand prediction, performance dashboards
- **Portable** — runs from USB, supports Windows, macOS, and WinPE environments

## Architecture

```
nest/
├── main.py                  # App entry point
├── launch_nest.py           # Bootstrap launcher
├── api/                     # RepairDesk + Google Calendar integration
│   ├── api_client.py        # RepairDesk API client with caching
│   ├── auth.py              # Encrypted auth (Fernet), PIN login, session management
│   └── google_calendar.py   # Calendar API
├── ai/                      # AI systems
│   ├── nestbot.py           # AI assistant (Claude/OpenAI/Gemini)
│   └── intelligent_analysis.py  # Repair patterns, business metrics, predictions
├── ui/                      # Tkinter + CustomTkinter GUI
│   ├── dashboard.py         # Main dashboard
│   ├── tickets.py           # Ticket management
│   ├── ticket_modal.py      # Ticket detail view
│   ├── customers.py         # Customer management
│   ├── inventory.py         # Parts and inventory
│   ├── appointments.py      # Calendar integration
│   ├── reports.py           # Business reports
│   ├── pc_tools.py          # PC diagnostics
│   ├── mobile_tools.py      # Android/iOS diagnostics
│   └── login.py             # Auth UI
├── utils/                   # Config, caching, platform paths
└── knowledge/               # AI knowledge base
```

## Running

```
python launch_nest.py
```

Or build as standalone:
```
pyinstaller --onefile --noconsole launch_nest.py
```

## Requirements

- Python 3.10+
- See `requirements.txt` for dependencies (PySide6 not required — uses Tkinter/CustomTkinter)
- RepairDesk API key
- AI provider API key (optional — Claude, OpenAI, or Gemini)

## How It Relates to Anvil

Nest was the first attempt at a repair shop management platform. It handles the same problem space as Anvil but with a different approach:

- **Nest**: Traditional desktop app with built-in AI chat, direct RepairDesk API calls, Tkinter GUI
- **Anvil**: Wraps Claude Code as a subprocess, uses MCP for RepairDesk, PySide6 GUI, prompt-driven AI behavior with persistent memory

Anvil replaced Nest as the primary platform.
