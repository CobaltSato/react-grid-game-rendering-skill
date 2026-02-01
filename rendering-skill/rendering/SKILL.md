---
name: rendering
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

<h2>Best Practices</h2>

<h3>Leverage CSS Variables</h3>

<ul>
<li>Centralize sizes with CSS variables</li>
<li>Use <code>calc()</code> for dynamic calculations</li>
<li>Enables easy responsive design</li>
</ul>

<h3>Performance Optimization</h3>

<ul>
<li>Set <code>key</code> props appropriately</li>
<li>Eliminate unnecessary elements with conditional rendering</li>
<li>Memoize with <code>useCallback</code>/<code>useMemo</code></li>
</ul>

<h3>Type Safety</h3>

<ul>
<li>Add type definitions to props</li>
<li>Define position data types explicitly</li>
</ul>

<h2>Troubleshooting</h2>

<h3>Objects not appearing in the correct position</h3>

<ul>
<li>Verify grid position indexing (0-based to 1-based conversion)</li>
<li>Check <code>transform</code> calculations</li>
</ul>

<h3>Tiles overlapping</h3>

<ul>
<li>Verify <code>gap</code> property is set</li>
<li>Check tile size values</li>
</ul>

<h3>Animations not smooth</h3>

<ul>
<li>Verify <code>transition</code> is set</li>
<li>Enable hardware acceleration with <code>will-change: transform</code></li>
</ul>
