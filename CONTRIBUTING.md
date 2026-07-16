# Contributing to MudraFX Ultra

Thank you for your interest in contributing to MudraFX Ultra! This document provides guidelines and information for contributors.

## 🌟 Ways to Contribute

- 🐛 **Report bugs** - Help us find and fix issues
- 💡 **Suggest features** - Share your ideas for new gestures or effects
- 📝 **Improve documentation** - Fix typos, clarify instructions, add examples
- 🎨 **Add new themes** - Create custom color themes
- ✨ **Add new gestures** - Implement new hand gesture effects
- 🔧 **Fix bugs** - Submit pull requests with bug fixes
- 🧪 **Write tests** - Add unit tests for gesture detection
- 📸 **Share screenshots** - Show off your creations

## 🚀 Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- A code editor (VS Code, Sublime Text, etc.)
- Basic knowledge of HTML, CSS, and JavaScript
- A webcam for testing

### Setup

1. **Fork the repository**
   ```bash
   # Click "Fork" on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/MudraFX-Ultra.git
   cd MudraFX-Ultra
   ```

2. **Start a local server** (required for camera access)
   ```bash
   # Python 3
   python3 -m http.server 8000
   
   # Node.js (if you have http-server installed)
   npx http-server -p 8000
   
   # PHP
   php -S localhost:8000
   ```

3. **Open in browser**
   ```
   http://localhost:8000
   ```

4. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## 📝 Code Style Guidelines

### JavaScript

- Use `const` and `let` instead of `var`
- Use arrow functions where appropriate
- Keep functions small and focused
- Add comments for complex logic
- Use meaningful variable names

```javascript
// Good
const detectGesture = (landmarks) => {
  const indexExtended = isFingerExtended(landmarks, 'index');
  // ...
};

// Avoid
var g = function(lm) {
  var ie = fExt(lm, 'index');
  // ...
};
```

### CSS

- Use BEM-like naming for custom classes
- Keep specificity low
- Use CSS variables for theme colors
- Comment sections clearly

```css
/* Good */
.gesture-card { }
.gesture-card__icon { }
.gesture-card--active { }

/* Use variables */
:root {
  --accent: #00e5ff;
  --bg-glass: rgba(6, 6, 24, 0.58);
}
```

### HTML

- Use semantic HTML where possible
- Keep accessibility in mind (ARIA labels)
- Indent with 2 spaces

## 🎨 Adding a New Theme

1. **Add theme colors** to the `TH` object:

```javascript
const TH = {
  // ... existing themes
  mythemename: {
    p: '#ff00ff',  // Primary color
    s: '#00ffff',  // Secondary color
    t: '#ffff00',  // Tertiary color
    w: '#ffffff'   // White/highlight
  }
};
```

2. **Add theme button** to the HTML panel:

```html
<div class="tb" data-theme="mythemename">
  <span class="em">🎨</span>My Theme
</div>
```

3. **Test thoroughly** with all 17 gestures

## ✨ Adding a New Gesture

### Step 1: Define Detection Logic

Add your gesture detection in the `detect()` function:

```javascript
function detect(lm) {
  // ... existing checks
  
  // Your new gesture
  if (/* your condition */) {
    return 'MY_GESTURE';
  }
}
```

### Step 2: Create Effect Function

Add a new drawing function:

```javascript
function drawMyGesture(lm, alpha) {
  if (alpha < 0.05) return;
  
  const t = T();
  c.save();
  c.globalCompositeOperation = 'lighter';
  c.globalAlpha = alpha;
  
  // Your effect code here
  
  c.restore();
}
```

### Step 3: Register in Dispatcher

Add to `drawGestureEffect()`:

```javascript
case 'MY_GESTURE':
  drawMyGesture(lm, alpha);
  break;
```

### Step 4: Update UI

Add to the gesture label mapping:

```javascript
const m = {
  // ... existing gestures
  MY_GESTURE: '🎯 My Gesture'
};
```

### Step 5: Update Documentation

- Add to README.md gesture table
- Add to onboarding screen
- Add to bottom bar guide

## 🐛 Reporting Bugs

When reporting bugs, please include:

1. **Browser and version** (e.g., Chrome 120.0.6099.109)
2. **Operating System** (e.g., macOS 14.2, Windows 11)
3. **Steps to reproduce**
   ```
   1. Open the app
   2. Click "Launch Camera"
   3. Make a Peace gesture
   4. Observe that...
   ```
4. **Expected behavior**
5. **Actual behavior**
6. **Screenshots or videos** (if applicable)
7. **Console errors** (open DevTools → Console)

## 💡 Suggesting Features

When suggesting features:

1. **Check existing issues** first
2. **Describe the use case** - Why would someone want this?
3. **Provide examples** - Mockups, sketches, or references
4. **Consider performance** - Will it run at 120 FPS?
5. **Think about accessibility** - Can everyone use it?

## 📤 Submitting Pull Requests

### Before Submitting

- [ ] Test your changes thoroughly
- [ ] Ensure no console errors
- [ ] Check performance (maintain 60+ FPS)
- [ ] Update documentation if needed
- [ ] Follow code style guidelines

### PR Checklist

- [ ] Clear, descriptive title
- [ ] Detailed description of changes
- [ ] Reference related issues (e.g., "Fixes #123")
- [ ] Include screenshots for visual changes
- [ ] Test on multiple browsers if possible

### PR Template

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix (non-breaking change that fixes an issue)
- [ ] New feature (non-breaking change that adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Testing
Describe how you tested your changes

## Screenshots
If applicable, add screenshots to show the changes

## Performance Impact
- [ ] No performance impact
- [ ] Improves performance
- [ ] May impact performance (explain below)

## Checklist
- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings or errors
- [ ] I have tested my changes in multiple browsers
```

## 🧪 Testing

### Manual Testing Checklist

- [ ] All 17 gestures work correctly
- [ ] All 12 themes display properly
- [ ] Camera initializes without errors
- [ ] Settings persist after reload
- [ ] Keyboard shortcuts work
- [ ] Screenshot export works
- [ ] Fullscreen mode works
- [ ] Performance stays above 60 FPS
- [ ] No console errors
- [ ] Works on mobile (if applicable)

### Browser Testing

Test in at least:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest, if on macOS)

## 📚 Documentation

When updating documentation:

- Use clear, simple language
- Include code examples where helpful
- Add screenshots for visual features
- Keep the README.md up to date
- Update inline code comments

## 🤝 Code of Conduct

### Our Pledge

We pledge to make participation in our project a harassment-free experience for everyone, regardless of age, body size, disability, ethnicity, gender identity and expression, level of experience, nationality, personal appearance, race, religion, or sexual identity and orientation.

### Our Standards

Examples of behavior that contributes to a positive environment:

- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

Examples of unacceptable behavior:

- Trolling, insulting/derogatory comments, and personal or political attacks
- Public or private harassment
- Publishing others' private information without explicit permission
- Other conduct which could reasonably be considered inappropriate

## 📞 Getting Help

- **Questions?** Open a [Discussion](https://github.com/jashgandhi/MudraFX-Ultra/discussions)
- **Bugs?** Open an [Issue](https://github.com/jashgandhi/MudraFX-Ultra/issues)
- **Email?** [jashvs7gandhi@gmail.com](mailto:jashvs7gandhi@gmail.com)

## 🎉 Recognition

Contributors will be:

- Listed in the README.md
- Mentioned in release notes
- Credited in commit messages
- Invited to the contributors team (for significant contributions)

## 📄 License

By contributing to MudraFX Ultra, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to MudraFX Ultra! 🖐️✨
