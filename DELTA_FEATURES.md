# Delta.html - New Features Documentation

This document describes all the new features added to Delta.html compared to index.html.

## ✅ Feature 1: Charger Status Field
**Status:** Implemented

- Added "Status" dropdown in charger popup with options: "Working" and "Issue"
- When "Issue" is selected, charger icon changes to `chargerissue.png`
- When "Working" is selected, uses normal `charger.png`
- Status is saved with charger data in Firebase

**Location in code:**
- Lines ~1568-1577: Charger popup HTML with status dropdown
- Lines ~1770-1779: Charger status change handler
- Lines ~2347-2350: Icon selection logic

## ✅ Feature 2: Reworks Tab in Groomer AND Charger Menus
**Status:** Implemented

Both groomer and charger popups now have a "Reworks" tab that includes:
- A list of all reworks assigned to that machine with checkboxes to mark complete
- An input field and "Add" button to manually add a rework
- An archive section showing completed reworks (collapsible)
- Reworks added via Settings bulk feature appear in these tabs

**Location in code:**
- Lines ~1481-1509: Groomer Reworks tab HTML
- Lines ~1587-1615: Charger Reworks tab HTML
- Lines ~1967-2059: Rework handlers and archive toggle
- Lines ~2060-2117: Archive rendering and toggle functionality

## ✅ Feature 3: Groomer Build Year Field
**Status:** Implemented

- Added "Build Year" dropdown field to groomer popup (General tab)
- Options dynamically populated from 2023 to current year using JavaScript
- JavaScript code: `for (let year = 2023; year <= new Date().getFullYear(); year++)`
- Saved with groomer data

**Location in code:**
- Lines ~1502-1513: Build Year dropdown HTML with dynamic year generation
- Line ~2552: Build year filter in rework modal

## ✅ Feature 4: Groomer Track Type Options
**Status:** Implemented

Track Type field updated with exact options:
- None
- Track Plates
- Track Tiller
- Removed

Changed from input field to dropdown select.

**Location in code:**
- Lines ~1520-1525: Track Type dropdown with new options

## ✅ Feature 5: Add Rework Button in Settings
**Status:** Implemented

Added "Add Rework" button to settings dropdown menu that opens a modal with:

### Modal Structure:
- Two tabs at top: "Groomers" and "Chargers"

### Groomers Tab:
- Input field for "Rework Name"
- Checkbox filters:
  - ☐ By Size (shows dropdown: 280, 320, 250)
  - ☐ By Build Year (shows dropdown: 2023 to current year)
  - ☐ By Track Type (shows dropdown: None, Track Plates, Track Tiller, Removed)
- If NO filters checked → applies to ALL groomers
- "Apply" button adds rework to matching groomers

### Chargers Tab:
- Input field for "Rework Name"
- Checkbox filter:
  - ☐ By Power (shows dropdown: 150 kW, 30 kW, Hypercharger)
- If NO filters checked → applies to ALL chargers
- "Apply" button adds rework to matching chargers

**Location in code:**
- Line ~1060: Settings menu button
- Lines ~1085-1164: Rework modal HTML structure
- Lines ~2541-2656: Modal JavaScript functions (open, close, tab switching, filter handlers)
- Lines ~2658-2705: Groomer rework application logic
- Lines ~2707-2741: Charger rework application logic

## ✅ Feature 6: Icon Size Limit on Zoom
**Status:** Implemented

Equipment icons have a maximum size limit when zooming:
- Icons do NOT get bigger than approximately 52-60 pixels
- When zoomed in past certain point, icons stay same size
- Keeps map overview clear when zoomed in

**Implementation:**
```javascript
function getIconSize(zoom) {
  const baseSize = 32;
  const calculatedSize = baseSize + (zoom - 10) * 3;
  const maxSize = 52;
  return Math.min(calculatedSize, maxSize);
}
```

**Location in code:**
- Lines ~1109-1114: getIconSize function
- Lines ~1116-1125: createDynamicIcon function
- Lines ~1127-1153: updateAllMarkerIcons function
- Lines ~1158-1161: Zoom event listener
- Lines ~2347-2366: addMarker function using dynamic icons

## Technical Details

### Title Change
- Changed from "Xelom Fleet Manager" to "Xelom Fleet Manager - Delta"
- Line 4

### New CSS Classes
- `.rework-modal` and related styles (lines ~1045-1229)
- `.filter-checkbox-group` and related styles
- `.rework-archive-section` and related styles
- `.rework-completed-item` for archived reworks

### Data Structure Updates
- Groomers now store: `buildYear`, `completedReworks[]`
- Chargers now store: `status`, `reworks[]`, `completedReworks[]`
- Both maintain existing data structures

### All Features Maintain:
- Dark theme (#121212 background, #ffcc00 yellow accents)
- Mobile responsive design
- Firebase/Firestore data persistence
- All existing functionality from index.html

## Testing Checklist

To test all features:

1. ✅ Open Delta.html in browser
2. ✅ Add a groomer - check Build Year dropdown has years 2023-2025
3. ✅ Add a groomer - check Track Type has 4 options (None, Track Plates, Track Tiller, Removed)
4. ✅ Add a groomer - check Reworks tab exists and works
5. ✅ Add a charger - check Status dropdown (Working/Issue) changes icon
6. ✅ Add a charger - check Reworks tab exists and works
7. ✅ Click Settings → "Add Rework" opens modal
8. ✅ Test Groomers tab filters (Size, Build Year, Track Type)
9. ✅ Test Chargers tab filter (Power)
10. ✅ Zoom in/out to verify icon size stays within limit
11. ✅ Mark reworks complete - verify they move to archive
