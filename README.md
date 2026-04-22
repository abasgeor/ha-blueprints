# HA Blueprints

Reusable Home Assistant automation blueprints.

## Available blueprints

### 🌀 [Rack Ventilation](blueprints/automation/abasgeor/rack_ventilation.yaml)

Smart fan control by temperature for IT racks, network cabinets, and server closets.

- Configurable hysteresis (anti-flapping)
- Supports 1 or more fan switches in parallel
- Emergency mode (critical temperature)
- Sensor fail-safe (if sensor goes offline)
- State recovery after HA restart
- Optional push notifications (critical only)
- Periodic sync check

**Import in HA:**

```
Settings → Automations & Scenes → Blueprints → Import Blueprint
URL: https://github.com/abasgeor/ha-blueprints/blob/main/blueprints/automation/abasgeor/rack_ventilation.yaml
```

---

### 🔔 [Smart Device Health Alerts (Brand-Aware)](blueprints/automation/abasgeor/smart_device_alerts.yaml)

Monitor any set of entities for three health conditions — low battery,
offline/unavailable, and stale numeric data — with rich notifications that
auto-detect brand icons from the
[custom-brand-icons](https://github.com/elax46/custom-brand-icons) HACS pack
(`phu:` prefix).

- Low battery alerts with configurable threshold
- Offline / unavailable detection with grace period
- Stale-data detection (numeric sensors that silently died)
- Brand-aware notification icons (35+ brands: Aqara, Philips Hue, Tuya,
  Shelly, Sonos, Apple, Samsung, LG, Amazon, Google, Xiaomi, Moes,
  TP-Link, Levoit, Dreame, Ubiquiti, Bose, Roborock, Lutron, Ecobee,
  Nest, Ring, Arlo, Wyze, Reolink, Yale, Kwikset, August, Fibaro, Somfy,
  Sonoff, Matter, Thread, Zigbee, Z-Wave)
- Cooldown per entity to prevent notification floods
- Optional daily digest mode
- Mobile actions (iOS/Android snooze & dismiss)
- Optional persistent notifications to HA sidebar

**Import in HA:**

```
Settings → Automations & Scenes → Blueprints → Import Blueprint
URL: https://github.com/abasgeor/ha-blueprints/blob/main/blueprints/automation/abasgeor/smart_device_alerts.yaml
```

---

### 🌬 [Air Freshener Heater Schedule (Air Wick-style)](blueprints/automation/abasgeor/air_freshener_heater_schedule.yaml)

Built for **wick / heater-style** air fresheners (Air Wick, Glade PlugIns,
Febreze warmers) that need **sustained power** to evaporate oil. Active
windows, waves for areas, continuous-on for bathrooms, prime/boost times
for peak moments.

| Room type | Pattern | Notes |
|-----------|---------|-------|
| BATHROOM | Continuous ON during window | Priority comfort |
| BEDROOM | 30 on / 90 off waves | Subtle, anti-overwhelm |
| LIVING_ROOM | 60 on / 30 off waves | Daytime ambient |
| TV_ROOM | 60 on / 30 off waves | |
| DINING_ROOM | 45 on / 45 off waves | Meal-time coverage |
| KITCHEN | 45 on / 15 off waves | Masks cooking odors |
| LARGE_ROOM | 90 on / 15 off waves | Bigger space |
| ENTRYWAY | 30 on / 60 off waves | First impression |
| CUSTOM | user-defined | Full manual |

- Active window (default 07:00–22:00)
- Room-type preset sets wave pattern (on_minutes / off_minutes)
- Prime/boost times for forced warm-up before peak use
- Optional motion-gating for non-bathroom rooms (skip if empty)
- Optional humidity skip for bathrooms (pause during shower steam)
- Enforcement check every N minutes (restart-safe)
- Self-corrects if switch gets manually toggled

**Import in HA:**

```
Settings → Automations & Scenes → Blueprints → Import Blueprint
URL: https://github.com/abasgeor/ha-blueprints/blob/main/blueprints/automation/abasgeor/air_freshener_heater_schedule.yaml
```

---

## Conventions

- **Namespace:** blueprints live under `blueprints/automation/abasgeor/`
- **Naming:** `snake_case` for filenames, `PascalCase` for the visible `name:`
- **Versioning:** each blueprint states its version in the description; breaking changes bump major
- **Inputs:** sensible defaults whenever possible, with clear descriptions and proper `selector` types
- **Fail-safe:** when in doubt, default to the safer behavior

## License

MIT
