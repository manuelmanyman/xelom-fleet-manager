# Eta.html - Visual Comparison Guide

## Before (Zeta.html) - Individual List View

### Warehouse Equipment Display
```
📦 Stored Equipment (8)

🚜 GR-001
   groomer
   Serial: GR-001

🚜 GR-002
   groomer
   Serial: GR-002

🔌 CH-001
   charger
   Serial: CH-001

⚙️ Blades - Model A (x5)
   blades

🔧 Tillers - Model B (x3)
   tillers
```

### Adding Equipment
```
➕ Add Equipment
[Dropdown: Groomer ▼]
[Input: Serial number...]
[Button: Add Equipment]
```

---

## After (Eta.html) - Grouped Expandable View

### Warehouse Equipment Display
```
📦 Stored Equipment (8)

[groomer.png] Groomers (2)    ▶
[charger.png] Chargers (1)    ▶
[blade.png] Blades (3)        ▶
[tiller.png] Tillers (2)      ▶
```

### When Expanded (Example: Groomers)
```
[groomer.png] Groomers (2)    ▼
  SN: GR-001 | Size: 320 | Tracks: Rubber | Tiller: T100
  SN: GR-002 | Size: 280 | Tracks: Aluminum | Blade: B50
```

### Adding Groomer Equipment
```
➕ Add Equipment
[Dropdown: Groomer ▼]

Serial number (required)...
Size (optional) [280/320/350 ▼]
Tracks Mounted (optional) [None/Rubber/Aluminum/High ALU ▼]
Tiller (optional)...
Blade (optional)...
Cross Country Tracks (optional) [None/Track Plates/Track Tiller/Removed ▼]

[Button: Add Equipment]
```

### Adding Charger Equipment
```
➕ Add Equipment
[Dropdown: Charger ▼]

Serial number (required)...
Power (optional) [150 kW/30 kW/Hypercharger ▼]
Status [Working/Issue ▼]

[Button: Add Equipment]
```

### Adding Tracks Equipment
```
➕ Add Equipment
[Dropdown: Tracks ▼]

Serial number (required)...
Type (optional) [Rubber/Aluminum/High ALU ▼]

[Button: Add Equipment]
```

### Adding Blade/Tiller Equipment
```
➕ Add Equipment
[Dropdown: Blade ▼]

Serial number (required)...
Type/Model (optional)...

[Button: Add Equipment]
```

### Adding Cross Country Tracks
```
➕ Add Equipment
[Dropdown: Cross Country Tracks ▼]

Serial number (required)...
Type (optional) [Track Plates/Track Tiller/Removed ▼]

[Button: Add Equipment]
```

---

## Key Improvements

### 1. Better Organization
- **Before:** All items listed individually, long scrolling
- **After:** Items grouped by type, compact view

### 2. Detailed Tracking
- **Before:** Quantity field for generic items (e.g., "Blades x5")
- **After:** Each item tracked individually with unique serial and details

### 3. Visual Hierarchy
- **Before:** Flat list with emoji icons
- **After:** Grouped with professional icons and expandable sections

### 4. Comprehensive Details
- **Before:** Limited to serial number and type
- **After:** Full details including size, tracks, power, status, model, etc.

### 5. Interaction Design
- **Before:** Static list
- **After:** Interactive expand/collapse for better space utilization

---

## Equipment Type Comparison

| Equipment | Zeta.html Fields | Eta.html Fields |
|-----------|-----------------|-----------------|
| Groomer | Serial, (Quantity) | Serial*, Size, Tracks Mounted, Tiller, Blade, CC Tracks |
| Charger | Serial, (Quantity) | Serial*, Power, Status |
| Tiller | Model, Quantity | Serial*, Type/Model |
| Blade | Model, Quantity | Serial*, Type/Model |
| Tracks | Type, Quantity | Serial*, Type |
| Cross Country | Type, Quantity | Serial*, Type |

\* = Required field

---

## Use Cases

### Scenario 1: Track Multiple Groomers
**Before:** "3 Groomers" - no individual details  
**After:** 
- GR-001: Size 320, Rubber tracks, Tiller T100
- GR-002: Size 280, Aluminum tracks, Blade B50  
- GR-003: Size 350, High ALU tracks

### Scenario 2: Monitor Charger Status
**Before:** "2 Chargers" - no status tracking  
**After:**
- CH-001: 150 kW, Working
- CH-002: 30 kW, Issue

### Scenario 3: Inventory Management
**Before:** Scroll through long list to find equipment  
**After:** Click "Groomers (3)" to see only groomers, expand to see details

---

## Implementation Notes

1. All changes apply to both **Warehouse** and **Ski Area** equipment sections
2. Equipment history/archive also uses grouped display
3. Icon images referenced (tiller.png, blade.png, tracks.png, finisher.png need to be added)
4. Fallback to emoji icons if image files are missing
5. Maintains all existing functionality from Zeta.html
