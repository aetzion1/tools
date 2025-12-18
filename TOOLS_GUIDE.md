# Tools Repository Guide for Building HTML Tools

## Repository Overview

**Location**: `/home/user/tools/`  
**Type**: Static HTML/JavaScript web tools  
**Hosting**: TBD

---

## Technical Constraints

All tools in this repository must follow these constraints:

- **Single file**: One HTML file containing all HTML, CSS (`<style>`), and JavaScript (`<script>`)
- **No frameworks**: No React, Vue, or any framework
- **No build step**: No bundlers, transpilers, or compilation
- **No dependencies**: Pure vanilla JS/CSS/HTML. If absolutely needed, load from CDN only
- **Modern standards**: Use latest JS (ES6+), CSS3, and HTML5 best practices
- **Mobile-friendly**: responsive design
- **Keep it simple**: Minimal code, small functions, clean structure

---

## 1. Repository Structure

```
/home/user/tools/
├── TOOLS_GUIDE.md            # This guide
├── my-tool.html              # Example tool
└── my-tool.docs.md           # Tool documentation
```

---

## 2. Tool File Naming Convention

- **HTML file**: `{tool-name}.html` (e.g., `query-string-stripper.html`)
- **Docs file**: `{tool-name}.docs.md` (e.g., `query-string-stripper.docs.md`)
- **Docs format**: Brief description + auto-generated commit comment (see python script)

### Example docs.md:

```markdown
A spinning wheel for random item selection. Add items to the wheel, spin it,
and let chance decide. Items are stored in localStorage for persistence across
sessions. Features a canvas-based wheel with smooth rotation animation.

<!-- Generated from commit: [commit-hash] -->
```

---

## 3. Common Patterns

### Data Persistence

**From wheel-picker.html:**

```javascript
const STORAGE_KEY = "wheelPickerItems";

function saveItems(items) {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(items));
}

function loadItems() {
  const data = localStorage.getItem(STORAGE_KEY);
  return data ? JSON.parse(data) : [];
}

// Load on page load
let items = loadItems();

// Save after every change
function addItem(text) {
  items.push({ text, color: generateColor() });
  saveItems(items);
  render();
}
```

---

## 4. Starting Template

Minimal template for a new tool (customize as needed):

```html
TBD

```

