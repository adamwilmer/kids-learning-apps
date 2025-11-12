# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a collection of standalone, single-file educational web applications designed for children. Each application is entirely self-contained with no external dependencies - all HTML, CSS, and JavaScript are embedded in a single file.

**Applications:**
- `index.html` - Spelling Bee practice app for Year 1 students
- `addition-subtraction.html` - Math practice for addition/subtraction with configurable max number (10-100)
- `times-tables.html` - Multiplication and division practice with configurable max multiplier (6-24)
- `guitar-learning.html` - Interactive guitar chord learning tool

## Architecture

### Self-Contained Design
Each HTML file follows an identical architecture pattern:
1. **No external dependencies** - No build tools, frameworks, or libraries
2. **Inline styles** - All CSS is in `<style>` tags within `<head>`
3. **Inline scripts** - All JavaScript is in `<script>` tags before `</body>`
4. **Mobile-responsive** - Media queries handle screens down to 600px width

### Common Structure Pattern
All applications share this structure:
- **Progress tracking** - Displays correct/incorrect/total scores
- **Quiz flow** - Question display → User interaction → Feedback → Next question
- **Completion screen** - Shows final score and lists items to practice
- **Reset functionality** - Returns to initial state or mode selection

### State Management
Each application uses simple global JavaScript variables:
- `currentIndex` - Tracks position in shuffled question array
- `correctCount` / `incorrectCount` - Score tracking
- `incorrectItems` - Array of wrong answers for review
- `shuffledArray` - Randomized questions/words/problems

### Quiz Flow Pattern
```javascript
startQuiz() → shuffleArray() → showCurrent() → handleAnswer() → updateDisplay() → showComplete()
```

## Development

### Opening Applications
Simply open any HTML file directly in a web browser. No server or build process required.

### Testing Changes
1. Make edits to the HTML file
2. Refresh the browser (Ctrl+R / Cmd+R)
3. Test on mobile by resizing browser or using device emulation

### Adding New Content
- **Spelling words**: Edit the `words` array in `index.html`
- **Chord data**: Modify the `chordData` object in `guitar-learning.html`
- **Math ranges**: Use the built-in sliders in both math apps (addition-subtraction and times-tables)
- **Quiz length**: Both math apps limit quizzes to 20 random questions regardless of range setting

## Code Style

### Consistent Patterns Across All Files
- Purple gradient background: `linear-gradient(135deg, #667eea 0%, #764ba2 100%)`
- Primary color scheme: `#667eea` (purple-blue) and `#764ba2` (purple)
- Button hover effects: `translateY(-2px)` with box-shadow
- Border radius: `10px` (buttons), `15px` (cards), `20px` (containers)

### CSS Organization
1. Reset/base styles
2. Layout containers
3. Mobile responsive media queries (@media max-width: 600px)
4. Component-specific styles (progress, buttons, displays)
5. State-specific classes (.hidden, .correct, .incorrect)

### JavaScript Conventions
- Fisher-Yates shuffle algorithm for randomization
- Event listeners prefer `onclick` attributes over `addEventListener`
- No ES6 modules (keeping it simple for single-file structure)
- Percentage calculations: `Math.round((correct / total) * 100)`

## Important Constraints

1. **Maintain single-file architecture** - Never split into separate CSS/JS files
2. **No external dependencies** - No CDN links, npm packages, or build tools
3. **Child-friendly design** - Large fonts, clear buttons, encouraging language
4. **Accessibility** - Ensure sufficient color contrast and keyboard navigation works
5. **Mobile-first** - Test all changes at 600px width and below
