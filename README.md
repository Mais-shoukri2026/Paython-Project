# Sensor Station Monitor

A simple Python project that simulates a monitoring station which takes sensor readings, validates them, and decides whether to raise a safety alarm.

## How It Works

The `station` class keeps a list of readings and applies two checks:

1. **Validity check** (`check`) — readings above `max_valid` (800) are marked `"Bad"` and rejected outright.
2. **Safety check** (`act`) — valid readings above `safe_smoke` (180) trigger an `"Alarm"`; otherwise the reading is `"Safe"`.

The `state` method combines both checks, and `run` prints the resulting state for every stored reading.

## Features

- Add and store multiple sensor readings
- Automatic rejection of out-of-range readings
- Alarm/safe classification based on a smoke safety threshold
- Simple greeting method for the station

## Usage

Run the script directly:

```bash
python Python_project.py
```

This will:
1. Greet the station by name
2. Add four sample readings (100, 300, 600, 900)
3. Print each reading alongside its status (`Rejected`, `Alarm`, or `Safe`)

## Example Output

```
Hi Mais Station
[100]
[100, 300]
[100, 300, 600]
[100, 300, 600, 900]
100 Safe
300 Alarm
600 Alarm
900 Rejected
```

## Configuration

- `max_valid` — highest reading considered valid (default: 800)
- `safe_smoke` — threshold above which an alarm is raised (default: 180)

Both can be adjusted when needed by editing the class attributes.

## Notes

This is a minimal educational example, not production-grade fire/smoke detection software.

## License

MIT
