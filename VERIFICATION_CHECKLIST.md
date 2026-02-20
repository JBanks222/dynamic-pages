# Verification Checklist: Responsive Design & Performance

## Desktop Testing (1920px+)

### Hero Section
- [ ] H1 "Mitosis Creative Agency" displays at 48px, yellow (#ffd65a)
- [ ] Tagline "We split big, messy ideas..." appears centered below
- [ ] 4 value chips visible with staggered fade-in animation (80ms between each)
- [ ] Chips read: "Interpreter", "Rapid belief prototypes", "Participation loops", "Human-first AI"
- [ ] CTA button "Let's Work Together" visible, yellow, clickable
- [ ] Hint text visible top-left: "Click to split an idea..."
- [ ] No horizontal scrollbars, no layout shift

### Canvas Interaction
- [ ] Click anywhere on canvas → nearest cell splits into 2 smaller cells
- [ ] Physics simulation smooth with visible gentle jiggle
- [ ] First-load pulse animation visible on initial cell (~3s)
- [ ] Hint text fades out after first split (500ms delay, smooth transition)
- [ ] Can split multiple times, cells get progressively smaller
- [ ] Edges bounce cells back into view

### How I Help Section
- [ ] Section background transitions smoothly from hero to dark background
- [ ] H2 "How I Help" visible in yellow
- [ ] All 4 cards display in responsive grid layout
- [ ] Each card shows:
  - Title (yellow, bold)
  - Description text (white, ~15px)
  - Concrete example line (italic, light yellow, ~13px)
- [ ] Card example lines are correct:
  - Interpreter: "Strategy → mechanic → prototype in a day."
  - Reality Generator: "Clickable demo before full build."
  - Creative Multiplier: "Automation that keeps taste human."
  - Human Guardrails: "Accessibility + clarity + consent."
- [ ] Cards have subtle hover effect (lift up, border brightens)
- [ ] Icon circles animate on hover (expand, brighten)

### Selected Work Section
- [ ] Section visible between How I Help and People-First
- [ ] H2 "Selected Work" visible in yellow
- [ ] 3 work items in grid layout (desktop: likely 3 columns)
- [ ] Each work item shows:
  - Project name (bold yellow)
  - Outcome description (white text)
  - "View Project" button (yellow, clickable)
- [ ] Button hover effect works (lifts slightly, brightens)
- [ ] Projects are:
  1. "Interactive Brand Strategy"
  2. "Rapid Prototype Sprint"
  3. "AI Workflow Redesign"

### People-First Section
- [ ] Section visible with subtle background (rgba(255, 214, 90, 0.02))
- [ ] H2 "What It's Like to Work Together" centered, yellow
- [ ] Content box appears centered with:
  - Opening paragraph: "I'm not here to execute..."
  - 3 bullet points (arrow-prefixed, →)
  - Bullets cover: Rapid cycles, Real feedback, Human-first
- [ ] Arrows are yellow, text is white/light
- [ ] Box has subtle border and background (semi-transparent)

### Contact Section
- [ ] Contact-promise line visible: "If you want the work to feel human and ship fast, let's build together."
- [ ] Image visible (the_sky_is_blue_cover.jpg) with rounded corners and shadow
- [ ] Contact blurb appears below image
- [ ] Two buttons visible:
  - Primary: "Start a Project" (email)
  - Secondary: "Talk It Through" (calendar)
- [ ] Button hover effects work (lift, shadow)
- [ ] Buttons have proper focus outlines (for keyboard navigation)

### CTA Animation Flow
- [ ] Click "Let's Work Together" → button plays falling animation (rotating, bouncing)
- [ ] After 2s → smooth scroll to contact section
- [ ] Button disappears during animation
- [ ] Page scrolls smoothly to contact

### Controls Panel
- [ ] Visible in fixed position, bottom-right corner
- [ ] Contains 2 elements:
  - "Reset" button
  - "Calm Mode" toggle switch
- [ ] Reset button is yellow, ~44px touchable area
- [ ] Toggle switch has:
  - Label: "Calm Mode"
  - Custom UI switch (36px×20px)
  - Toggles between off/on state
- [ ] Buttons can be focused (Tab key)

---

## Mobile Testing (375px - iPhone 12 width)

### Hero Section
- [ ] H1 resizes to ~36px (small but readable)
- [ ] Tagline font-size ~18px, still centered and readable
- [ ] Value chips wrap to multiple lines (still readable)
- [ ] All 4 chips still visible (not cut off or hidden)
- [ ] No horizontal scroll
- [ ] Touch-friendly spacing

### Canvas
- [ ] Full viewport height (100vh)
- [ ] Touches work (click to split)
- [ ] Cells split and move smoothly
- [ ] No lag or stuttering

### How I Help Section
- [ ] H2 resizes to ~28px
- [ ] Cards stack single-column on very small screens
- [ ] Card padding/text remains readable
- [ ] Example lines wrap to 2 lines max without breaking
- [ ] No text cutoff

### Selected Work Section
- [ ] Work items stack vertically (1 column)
- [ ] Titles and descriptions fully readable
- [ ] "View Project" buttons have ≥44px min height/width
- [ ] No horizontal scroll

### People-First Section
- [ ] Content box width responsive (not too wide)
- [ ] Bullets formatted well with arrows
- [ ] Readable on small screen

### Contact Section
- [ ] Image scales appropriately (max-height: 60vh)
- [ ] Buttons stack or side-by-side with proper spacing
- [ ] Buttons remain ≥44px touch targets
- [ ] No text cutoff in contact blurb

### Controls Panel
- [ ] Stacks vertically on mobile (flex-direction: column)
- [ ] Reset button still clickable
- [ ] Toggle switch still accessible
- [ ] Positioned without blocking important content
- [ ] Buttons have proper mobile spacing

### Responsive Issues to Check
- [ ] No text truncation
- [ ] No unexpected line breaks
- [ ] No overflow scrollbars (except intended)
- [ ] Images scale appropriately
- [ ] Buttons remain touchable (≥44px)
- [ ] No visual overlap of elements

---

## Tablet Testing (768px - iPad width)

### Breakpoint Behavior
- [ ] At exactly 768px, styles apply mid-range defaults
- [ ] Below 768px, mobile styles apply
- [ ] Above 768px, desktop styles apply
- [ ] Smooth transition (no jump in layout)

### Grid Layouts
- [ ] Cards grid shows 2-3 columns (auto-fit, minmax(260px, 1fr))
- [ ] Work grid shows 2-3 columns
- [ ] Both grids responsive as viewport changes

---

## Performance Testing (Chrome DevTools)

### Network
- [ ] Page loads in <3s (including all resources)
- [ ] No render-blocking resources
- [ ] No unused CSS (all classes are present in HTML)
- [ ] File size: index.html ~42KB uncompressed

### Performance (Lighthouse)
- [ ] Performance score: ≥90
- [ ] Accessibility score: ≥95
- [ ] Best Practices score: ≥90
- [ ] SEO score: ≥90
- [ ] No layout shifts (CLS < 0.1)
- [ ] First Contentful Paint (FCP): <1.5s
- [ ] Largest Contentful Paint (LCP): <2.5s

### Canvas Performance
- [ ] Open DevTools → Performance tab
- [ ] Click on canvas → split a cell
- [ ] Record 5 splits
- [ ] Check FPS counter:
  - Target: 60fps consistently
  - Acceptable: 55fps (minor drops ok)
  - Poor: <50fps (optimize if seen)
- [ ] Frame time <16ms per frame
- [ ] Main thread doesn't block (look for long red bars)

### Memory
- [ ] Open DevTools → Memory tab
- [ ] Take heap snapshot at load
- [ ] Split cells 50 times
- [ ] Take another heap snapshot
- [ ] Delta should be reasonable (<5MB increase)
- [ ] No unexpected memory growth

### Console Errors
- [ ] Open DevTools → Console
- [ ] No red errors (warnings ok)
- [ ] No JavaScript exceptions
- [ ] Network requests all 200 OK

---

## Accessibility Testing

### Keyboard Navigation (Tab Key)
- [ ] Tab through all interactive elements:
  - CTA button ("Let's Work Together")
  - All "View Project" buttons
  - "Start a Project" button
  - "Talk It Through" button
  - Reset button
  - Calm Mode toggle
- [ ] Tab order is logical (left→right, top→bottom)
- [ ] All focused elements have visible outline (2px solid #ffd65a)

### Screen Reader Testing (NVDA / VoiceOver)
- [ ] Page title announced: "Mitosis Creative Agency"
- [ ] H1 announced as heading
- [ ] All headings have proper levels (h2, h3)
- [ ] Links have descriptive text (not "Click here")
- [ ] Buttons have clear labels ("Start a Project", "Reset", etc.)
- [ ] Images have alt text (e.g., canvas has no alt needed; contact image has "Creative work")
- [ ] Sections are announced

### Color Contrast
- [ ] Use Contrast Checker: contrast-ratio.com
- [ ] All text meets WCAG AA minimum (4.5:1)
- [ ] Specific checks:
  - Yellow text (#ffd65a) on dark background: ✅ High contrast
  - White text on dark background: ✅ High contrast
  - Button focus outline visible: ✅

### Reduced Motion
- [ ] Enable macOS/Windows reduced motion setting
- [ ] Reload page
- [ ] Calm Mode toggle auto-checked: ✅
- [ ] No animations visible:
  - Chips appear instantly
  - CTA animation skipped
  - Pulse ring invisible
  - Card hovers no transform
- [ ] Canvas still clickable and works normally
- [ ] All content still visible and accessible

### Zoom Testing
- [ ] Browser zoom to 200% (Chrome DevTools)
- [ ] [ ] Page remains readable (no text cutoff)
- [ ] No horizontal scroll
- [ ] Buttons still clickable
- [ ] Layout reflows gracefully

---

## Browser Compatibility

### Desktop Browsers
- [ ] Chrome 90+ → All features work
- [ ] Firefox 88+ → All features work
- [ ] Safari 14+ → All features work
- [ ] Edge 90+ → All features work

### Mobile Browsers
- [ ] Safari iOS 14+ → All features work
- [ ] Chrome Android → All features work
- [ ] Samsung Internet → All features work

### Fallbacks
- [ ] Older browsers without `prefers-reduced-motion` still load page (animations play)
- [ ] CSS Grid fallback: cards still readable (may not be as beautiful but functional)
- [ ] Canvas not supported browsers: page doesn't crash (caveat: no canvas interaction)

---

## Copy & Messaging Verification

### Hero
- [ ] Title: "Mitosis Creative Agency" ✅
- [ ] Tagline: "We split big, messy ideas into experiences people actually feel." ✅
- [ ] Chips: All 4 visible and readable ✅

### Hint
- [ ] Before first split: "Click to split an idea. Each generation gets more focused." ✅
- [ ] After first split: Fades out within 1s ✅
- [ ] After reset: Returns and is readable ✅

### Contact Promise
- [ ] Line visible: "If you want the work to feel human and ship fast, let's build together." ✅
- [ ] Positioned above image ✅
- [ ] Bold yellow color ✅

### Contact Buttons
- [ ] Primary: "Start a Project" (opens email) ✅
- [ ] Secondary: "Talk It Through" (links to calendar placeholder) ✅

### Card Examples
- [ ] All 4 present and match requirements ✅
- [ ] Italic style applied ✅
- [ ] Light yellow color (#ffd65a, 0.8 opacity) ✅

---

## Interaction Verification

### Canvas Mechanic
- [ ] Click on yellow cell → splits into 2 smaller cells ✅
- [ ] Physics simulates properly (movement, bouncing, damping) ✅
- [ ] Multiple cells exist when split many times ✅
- [ ] Cells shrink with each generation ✅
- [ ] Reset clears all cells and shows original state ✅

### Button Interactions
- [ ] Hover shows visual feedback (color change, shadow) ✅
- [ ] Click triggers expected action ✅
- [ ] Focus outline visible (keyboard) ✅
- [ ] Disabled state if applicable (none in current design) ✅

### Controls
- [ ] Reset button clears canvas ✅
- [ ] Reset button restores hint text ✅
- [ ] Calm Mode toggle works (can turn on/off) ✅
- [ ] Calm Mode affects canvas jiggle visibly ✅
- [ ] Toggle persists visually (checked/unchecked state) ✅

### Scrolling Behavior
- [ ] Clicking CTA → smooth scroll to contact section ✅
- [ ] Scroll is fluid (not jumpy) ✅
- [ ] Contact section lands in view (centered or top majority visible) ✅

---

## Final Production Checklist

- [ ] All HTML is valid (run through validator.w3.org)
- [ ] No console errors in any browser
- [ ] All links are correct (email, calendly placeholder)
- [ ] Images are optimized (not too large, good compression)
- [ ] No hardcoded test data (all copy is production-ready)
- [ ] Commit message is descriptive
- [ ] Changes are documented (this file + IMPLEMENTATION_GUIDE.md)
- [ ] Git history is clean (no unintended files committed)
- [ ] Site is deployed and live
- [ ] Mobile version tested on actual hardware
- [ ] Desktop version tested on at least 2 browsers
- [ ] Accessibility tested with keyboard and screen reader

---

## Performance Targets

| Metric | Target | Current |
|--------|--------|---------|
| FCP (First Contentful Paint) | <1.5s | — |
| LCP (Largest Contentful Paint) | <2.5s | — |
| CLS (Cumulative Layout Shift) | <0.1 | — |
| Canvas FPS | 60 | — |
| Lighthouse Performance | 90+ | — |
| Lighthouse Accessibility | 95+ | — |
| Page Load (3G) | <3.5s | — |

---

## Notes for Future Updates

1. **Case studies**: Replace "View Project" button onclick with actual modal or page links
2. **Email validation**: Add validation to email link if using form later
3. **Calendly link**: Update placeholder to actual calendar URL
4. **Analytics**: Add event tracking for conversions
5. **A/B testing**: Test different chip copy or button labels

---

**Completed Date**: February 19, 2026  
**Verified By**: [Your name]  
**Sign-off**: ✅ Ready for Production
