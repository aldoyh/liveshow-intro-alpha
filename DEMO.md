# XYZ Splash Screen Demo

## Overview
This project contains a cinematic splash screen with physics-based animation featuring a plumb bob (pendulum weight) that drops, swings, and explodes to reveal the XYZ logo.

## Features

### Animation Sequence
1. **The Drop** - A plumb bob weight drops from above with a realistic bounce effect (2.8s)
2. **The Dangle** - The weight swings harmonically back and forth, gradually settling (6.8s total)
3. **The Scare** - Tension builds as the weight pulls down, then explodes dramatically (2.4s)
4. **Logo Reveal** - The XYZ logo appears with a glowing pulsing effect (infinite)

### User Experience
- **Skip Button** - Appears during the dangle phase, allows users to skip to the end
- **ESC Key** - Press ESC anytime to skip the animation
- **Keyboard Navigation** - Full keyboard support for accessibility

### Accessibility
- Respects `prefers-reduced-motion` for users with motion sensitivity
- ARIA labels for screen readers
- Keyboard navigation support
- Focus indicators on interactive elements

## How to Run

### Option 1: Simple HTTP Server (Python)
```bash
python3 -m http.server 8080
# Then open http://localhost:8080/index.html in your browser
```

### Option 2: Node.js HTTP Server
```bash
npx http-server -p 8080
# Then open http://localhost:8080/index.html in your browser
```

### Option 3: VS Code Live Server
1. Install the "Live Server" extension in VS Code
2. Right-click on `index.html`
3. Select "Open with Live Server"

### Option 4: Direct File Access
Simply open `index.html` directly in a modern web browser (Chrome, Firefox, Safari, Edge).

## Customization

### Changing the Logo
Edit line 158 to change "XYZ" to your brand name:
```html
<div id="logo" class="logo-text absolute" aria-label="XYZ Logo">XYZ</div>
```

### Adjusting Colors
Modify the CSS variables in the `:root` section (lines 22-29):
```css
:root {
    --background: #09090b;  /* Background color */
    --foreground: #fafafa;  /* Text color */
    --primary: #7c3aed;     /* Primary accent (violet) */
    --accent-bright: #a78bfa; /* Lighter accent */
}
```

### Animation Speed
All durations are already doubled for a cinematic effect. To adjust further, modify the duration values in the JavaScript timeline starting at line 225.

### Skip Speed
Change the skip acceleration by modifying line 322:
```javascript
tl.timeScale(5); // Increase number to skip faster
```

## Technical Details

### Dependencies
- **GSAP 3.12.5** - Professional animation library
- **Tailwind CSS** - Utility-first CSS framework (via CDN)
- **Inter Font** - Modern sans-serif typeface from Google Fonts

### Browser Support
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### Performance
- Optimized animations using GSAP's performance features
- Hardware-accelerated transforms
- Efficient SVG rendering
- Preconnect hints for external resources

## Troubleshooting

### Animations not working
- Check browser console for errors
- Ensure GSAP loaded successfully
- Verify internet connection (for CDN resources)

### Skip button not appearing
- Wait for the dangle phase to start (~3 seconds after page load)
- The button fades in gradually

### Logo not visible
- Check if the animation has completed
- Verify the timeline isn't paused

## Future Enhancements
- Add sound effects for drop and explosion
- Implement particle effects for the explosion
- Add progress indicator
- Create alternative animation styles
- Add configuration options via URL parameters

## License
This project is provided as-is for demonstration purposes.
