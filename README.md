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
- Brand-aware notification icons (Aqara, Philips Hue, Tuya, Shelly,
  Sonos, Apple, Samsung, LG, Amazon, Google, Xiaomi, Moes, TP-Link,
  Levoit, Dreame, Ubiquiti, Bose, Roborock, Lutron, Ecobee, Nest,
  Ring, Arlo, Wyze, Reolink, Yale, Kwikset, August, Fibaro, Somfy,
  Sonoff, Matter, Thread, Zigbee, Z-Wave — 35+ brands out of the box)
- Cooldown per entity to prevent notification floods
- Optional daily digest mode (end-of-day summary)
- Mobile actions (iOS/Android snooze & dismiss)
- Optional persistent notifications to HA sidebar

**Import in HA:**

```
Settings → Automations & Scenes → Blueprints → Import Blueprint
URL: https://github.com/abasgeor/ha-blueprints/blob/main/blueprints/automation/abasgeor/smart_device_alerts.yaml
```

---

### 🌬 [Smart Air Freshener Cycle](blueprints/automation/abasgeor/air_freshener_smart_cycle.yaml)

Runs an air-freshener / aroma diffuser on a smart schedule with **room-type
presets**, optional motion-awareness and quiet hours.

| Room type | Interval | Spray | Notes |
|-----------|----------|-------|-------|
| BATHROOM | 30 min | 5 s | After-use pulse if motion-aware |
| BEDROOM | 60 min | 3 s | Paused during sleep hours |
| LIVING_ROOM | 45 min | 10 s | Daytime focus |
| KITCHEN | 30 min | 10 s | Helps mask cooking odors |
| LARGE_ROOM | 30 min | 15 s | Open-plan / high-ceiling |
| ENTRYWAY | 60 min | 5 s | First-impression setting |
| CUSTOM | you set | you set | Full manual |

- Pick the room type and let the blueprint set interval + duration
- Override anything with the custom interval / duration fields
- Quiet hours (no spray while sleeping)
- Motion-awareness: bathrooms switch to **after-use pulse** (fires ~2 min
  after the last motion); other rooms gate on recent motion
- Humidity-skip (optional): don't waste fragrance while the bathroom is
  steamy from a shower
- Fail-safe: always turns the switch back off after the spray

**Import in HA:**

```
Settings → Automations & Scenes → Blueprints → Import Blueprint
URL: https://github.com/abasgeor/ha-blueprints/blob/main/blueprints/automation/abasgeor/air_freshener_smart_cycle.yaml
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
