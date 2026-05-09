# Elite Missions - Settings Reference

## 🎛️ Available Settings

### Speed Control

**Setting Name:** Speed  
**Range:** 50 - 300 speed/second  
**Default:** 150  
**Type:** Slider

```lua
spd = 150  -- Change this value
```

**Recommendations:**
- 🐢 **50-100:** Slowest, most reliable, obvious
- ⚡ **150-200:** Default, balanced, recommended
- 🚀 **250-300:** Fastest, may get flagged

**Tips:**
- ✅ Use 150 for first-time runs
- ✅ Increase if teleporting fails
- ✅ Decrease if getting flagged
- ✅ Test each mission with new speed

---

### C4 Delay

**Setting Name:** C4 Delay  
**Range:** 0.1 - 2.0 seconds  
**Default:** 0.5  
**Type:** Slider

```lua
c4d = 0.5  -- Change this value
```

**What it does:**
- Controls delay between C4 placements
- Higher = More time between actions
- Lower = Faster but risky

**Recommendations:**
- ⚡ **0.1-0.3:** Very fast, may miss
- ✅ **0.5-0.7:** Default, reliable
- 🐢 **1.0-2.0:** Slow, always works

**Tips:**
- ✅ Increase if C4 not placing
- ✅ Increase for high server lag
- ✅ Decrease for faster runs
- ✅ Use 1.5+ on busy servers

---

### Mission Selection

**Setting Name:** Mission  
**Options:**
1. Save Saber Fox!
2. Take Over The Sub!
3. Defeat The Giga Chad

**Type:** Dropdown

**Details:**

| Mission | ID | Time | Difficulty | Reward |
|---------|----|----- |------------|--------|
| Fox | 1 | 17.5s | Medium | ⭐⭐⭐ |
| Sub | 2 | 23s | Hard | ⭐⭐⭐⭐ |
| Giga | 3 | 23s | Expert | ⭐⭐⭐⭐⭐ |

---

### Difficulty Level

**Setting Name:** Diff  
**Options:**
1. Easy
2. Medium
3. Hard

**Type:** Dropdown

**Comparison:**

```
┌──────────┬──────────┬──────────┬──────────┐
│ Factor   │ Easy     │ Medium   │ Hard     │
├──────────┼──────────┼──────────┼──────────┤
│ Time     │ Fastest  │ Normal   │ Longest  │
│ Reward   │ Low      │ Medium   │ Highest  │
│ Enemies  │ Few      │ Some     │ Many     │
│ Risk     │ Low      │ Medium   │ High     │
└──────────┴──────────┴──────────┴──────────┘
```

**Tips:**
- ✅ Use Easy for practice
- ✅ Use Hard for maximum profit
- ✅ Difficulty affects rewards only

---

### Auto Loop

**Setting Name:** Auto Loop  
**Type:** Toggle (On/Off)  
**Default:** Off

```lua
loop = false  -- Set to true to enable
```

**What it does:**
- Automatically repeats selected mission
- Waits for cooldown automatically
- Runs continuously until disabled

**Tips:**
- ⚠️ Don't leave running unattended
- ⚠️ Watch for anti-cheat triggers
- ⚠️ Add manual breaks every 30 mins
- ✅ Best for AFK farming on private servers

---

## 📊 Optimal Settings by Goal

### For Speed Runners
```lua
spd = 300        -- Maximum speed
c4d = 0.2        -- Minimal delay
loop = false     -- One mission at a time
cd = "Hard"      -- Maximum rewards
```

### For Casual Players
```lua
spd = 150        -- Balanced speed
c4d = 0.5        -- Comfortable delay
loop = false     -- Single runs
cd = "Medium"    -- Good rewards
```

### For AFK Farming
```lua
spd = 100        -- Careful, obvious
c4d = 1.0        -- Very reliable
loop = true      -- Auto repeat
cd = "Hard"      -- Maximum rewards
```

### For Stealth
```lua
spd = 75         -- Very slow
c4d = 1.5        -- Long delays
loop = false     -- Minimal activity
cd = "Easy"      -- Lower risk
```

---

## ⚙️ Advanced Configuration

### Mission Cooldowns

Each mission has a cooldown before repeating:

| Mission | Cooldown | Details |
|---------|----------|----------|
| Fox | Variable | Shown in UI |
| Sub | Variable | Shown in UI |
| Giga | Variable | Shown in UI |

The script automatically detects and waits for cooldowns.

### Custom Coordinates

Edit mission positions in the script:

```lua
local foxLogic = function(d, e, f)
  -- d = starting position
  -- e = middle position
  -- f = end position
end
```

### Custom Positions Example

```lua
local customD = Vector3.new(-9554, 160, 396)
local customE = Vector3.new(-9559, 160, 405)
local customF = Vector3.new(-9572, 126, 275)

foxLogic(customD, customE, customF)
```

---

## 🔍 Settings Troubleshooting

### Script Runs Too Fast/Slow
✅ Adjust Speed slider
✅ Remember changes take effect immediately

### C4 Not Placing
✅ Increase C4 Delay value
✅ Check server lag
✅ Verify you have permissions

### Auto Loop Not Working
✅ Check if enabled in settings
✅ Verify mission is available
✅ Check cooldown timer

### Settings Not Saving
✅ Enable "Save Config" in UI
✅ Check file permissions
✅ Verify config folder exists

---

## 📈 Performance Impact

```
Speed Setting Impact:
50   → ████████░░ 80% CPU
150  → ██░░░░░░░░ 20% CPU ✅ Recommended
300  → ██░░░░░░░░ 25% CPU

C4 Delay Impact:
0.1  → ████████░░ 80% CPU
0.5  → ██░░░░░░░░ 20% CPU ✅ Recommended  
2.0  → █░░░░░░░░░ 10% CPU
```

---

**Last Updated:** 2026-05-09
