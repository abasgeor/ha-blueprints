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

Or clone the file manually into `/config/blueprints/automation/abasgeor/`.

---

## Conventions

- **Namespace:** blueprints live under `blueprints/automation/abasgeor/`
- **Naming:** `snake_case` for filenames, `PascalCase` for the visible `name:`
- **Versioning:** each blueprint states its version in the description; breaking changes bump major
- **Inputs:** sensible defaults whenever possible, with clear descriptions and proper `selector` types
- **Fail-safe:** when in doubt, default to the safer behavior

## License

MIT
