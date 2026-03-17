# Mobile Menu Button (Web Component)

## Description

Accessible, mobile-only, floating navigation menu button that appears at viewport widths ≤640px. Built with vanilla JavaScript as a standalone Web Component. Features an animated SVG "hamburger menu" icon that transforms into an X-shaped "Close" icon when toggled. Adheres to a11y standards and offers customizable options like icon color, background shape color, border (corner) radius, and drop-shadow.

## Features

- Mobile-only (visible at ≤640px viewport width)
- Fully accessible (ARIA attributes, keyboard navigation)
- Customizable colors and border radius
- Zero dependencies
- Framework-agnostic (works anywhere)
- Shadow DOM encapsulation
- Lightweight (~3KB minified)
- Production-ready

## Installation

### Using NPM

```bash
npm install mobile-menu-button
```

### Using Yarn

```bash
yarn add mobile-menu-button
```

### Via CDN

```html
<script type="module" src="https://unpkg.com/@mattdanielbrown/mobile-menu-button"></script>
```

## Usage

### Basic
```html
<menu-button>Menu</menu-button>

<script type="module">
  import 'mobile-menu-button';
</script>
```

### Custom Controls
```html
<menu-button controls="nav-menu">Menu</menu-button>
```

### Custom Styling
```html
<menu-button 
  background="#1a202c" 
  color="#fff"
  radius="1rem"
>Navigation</menu-button>
```

### Programmatic Control
```javascript
const menuButton = document.querySelector('menu-button');

// Toggle state
menuButton.toggle();

// Expand
menuButton.expand();

// Collapse
menuButton.collapse();

// Listen to events
menuButton.addEventListener('menu-button-toggle', (event) => {
  console.log('Expanded:', event.detail.expanded);
  console.log('Controls:', event.detail.controls);
});
```

## API

### Attributes

| Attribute | Type | Default | Description |
|-----------|------|---------|-------------|
| `background` | string | `#E2E8F0` | Button background color (CSS color) |
| `color` | string | `#45556C` | Button text color (CSS color) |
| `controls` | string | `navigation-menu` | ID of controlled element (aria-controls) |
| `radius` | string | `.5em` | Button border radius (CSS length) |

### Properties

| Property | Type | Default | Read-only | Description |
|----------|------|---------|-----------|-------------|
| `background` | string | `#E2E8F0` | No | Background color |
| `color` | string | `#45556C` | No | Text color |
| `controls` | string | `navigation-menu` | No | Controlled element ID |
| `radius` | string | `.5em` | No | Border radius |
| `expanded` | boolean | `false` | No | Expansion state |

### Methods

| Method | Parameters | Returns | Description |
|--------|------------|---------|-------------|
| `toggle()` | none | `void` | Toggle expanded state |
| `expand()` | none | `void` | Expand menu |
| `collapse()` | none | `void` | Collapse menu |

### Events

| Event | Detail | Description |
|-------|--------|-------------|
| `menu-button-toggle` | `{ expanded: boolean, controls: string }` | Fired when button is clicked |

### CSS Custom Properties

```css
menu-button {
  /* Colors */
  --menu-button-bg: #e5e7eb;
  --menu-button-bg-hover: #dcdee2;
  --menu-button-bg-focus: #d7d9dc;
  --menu-button-bg-active: #d0d2d6;
  --menu-button-bg-expanded: #ff6467;
  --menu-button-bg-expanded-hover: #fb2c36;
  --menu-button-bg-expanded-focus: #e7000b;
  --menu-button-bg-expanded-active: #c10007;
  --menu-button-color: #6a7282;
  --menu-button-color-expanded: white;
  --menu-button-outline-focus: #51a2ff;
  
  /* Sizing */
  --menu-button-radius: 0.5em;
  --menu-button-padding: 0.5em 1em;
  --menu-button-font-size: 1em;
  --menu-button-font-weight: 600;
  
  /* Positioning (when visible) */
  bottom: 2rem;
  right: 2rem;
}
```

### CSS Parts

```css
/* Style internal button */
menu-button::part(button) {
  /* custom styles */
}

/* Style text span */
menu-button::part(text) {
  /* custom styles */
}

/* Style icon span */
menu-button::part(icon) {
  /* custom styles */
}
```

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

**Requires support for:**

- Custom Elements v1
- Shadow DOM v1
- ES Modules

## License

MIT &copy; Matt Daniel Brown

## Contributing

Contributions welcome — please open an issue or submit a pull request.
