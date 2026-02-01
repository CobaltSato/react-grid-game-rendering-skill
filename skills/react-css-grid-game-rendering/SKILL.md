---
description: "Grid-based game rendering patterns using React + CSS Grid. Use for grid game UI implementation, CSS Grid layout design, dynamic object placement, and game UI styling/animation."
---

# React + CSS Grid Game Rendering Skill

DOM-based game rendering patterns using React + CSS Grid. Implements game boards with grid layouts instead of Canvas/WebGL.

## When to Use

- Grid-based game UI implementation
- CSS Grid layout design
- Dynamic object placement
- Game UI styling and animation

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **React** | UI component rendering |
| **CSS Grid** | Grid layout |
| **CSS Variables** | Centralized size and color management |
| **Inline Styles** | Dynamic positioning |
| **CSS Animations** | Visual effects |

## Basic Patterns

### Grid Layout Setup

**Manage sizes with CSS variables:**
```css
:root {
  --tile-size: 50px;
  --grid-size: 10;
  --grid-gap: 2px;
}

.board {
  display: grid;
  grid-template-columns: repeat(var(--grid-size), var(--tile-size));
  grid-template-rows: repeat(var(--grid-size), var(--tile-size));
  gap: var(--grid-gap);
  position: relative;  /* Reference point for absolute positioning */
}
```

### Tile Rendering

**Generate tiles from a 2D array:**
```tsx
{gridData.map((row, y) =>
  row.map((tile, x) => (
    <div key={`${y}-${x}`} className={`tile tile-${tile}`} />
  ))
)}
```

### Dynamic Object Placement

**Place by grid position (Important: Grid is 1-based):**
```tsx
<div
  className="object"
  style={{
    position: 'absolute',
    gridColumnStart: position.x + 1,  // Array is 0-based, Grid is 1-based
    gridRowStart: position.y + 1,
  }}
/>
```

**Center alignment calculation:**
```css
.object {
  transform: translate(
    calc(var(--tile-size) * offset-ratio),
    calc(var(--tile-size) * offset-ratio)
  );
}
```

## Key Considerations

### Grid Position Indexing

- **CSS Grid is 1-based**: `gridColumnStart: 1` is the first column
- **Arrays are 0-based**: `array[0][0]` is the first element
- **Conversion required**: `gridColumnStart: x + 1`

### Absolute Positioning Reference

- Parent element requires `position: relative`
- Use `gridColumnStart`/`gridRowStart` to specify grid position
- Fine-tune with `transform: translate()`

### Performance

- No issues for small grids (~10x10)
- Consider virtualization for large grids (100x100+)
- Migration to Canvas/WebGL is also an option

## Best Practices

### Leverage CSS Variables

- Centralize sizes with CSS variables
- Use `calc()` for dynamic calculations
- Enables easy responsive design

### Performance Optimization

- Set `key` props appropriately
- Eliminate unnecessary elements with conditional rendering
- Memoize with `useCallback`/`useMemo`

### Type Safety

- Add type definitions to props
- Define position data types explicitly

## Troubleshooting

### Objects not appearing in the correct position

- Verify grid position indexing (0-based to 1-based conversion)
- Check `transform` calculations

### Tiles overlapping

- Verify `gap` property is set
- Check tile size values

### Animations not smooth

- Verify `transition` is set
- Enable hardware acceleration with `will-change: transform`
