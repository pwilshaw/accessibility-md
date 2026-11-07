# Accessibility

How we design, build and write so everyone can use what we make. This file is for every person and every AI agent who works on this project.

**Our bar:** WCAG 2.2 level AA on every page, in every release. Where we go further than AA, the rule says so.

## Why it matters

- **1 in 6 people.** 1.3 billion people, 16% of the world, live with significant disability (WHO, 2023). That's not an edge case.
- **Over 1 in 4 people.** At least 2.2 billion people have a near or distance vision impairment. For at least 1 billion of them, it could have been prevented or hasn't been treated yet (WHO).
- **1.5 billion people.** Over 1.5 billion people live with some hearing loss, and 430 million with disabling hearing loss (WHO).
- **Eyes age for everyone.** Almost everyone needs reading glasses by their mid-40s to 50s. Perfect eyesight is temporary, so don't design for it.
- **It's not just disability.** A broken arm, bright sunlight, a noisy train or a phone on mute limits anyone. Accessibility helps everyone.
- **It's the law.** US: Americans with Disabilities Act (ADA). EU: European Accessibility Act (Directive 2019/882), in force since 28 June 2025. UK: Equality Act 2010 and the Public Sector Bodies Accessibility Regulations 2018.

There's no neutral ground. If you're not including people, you're excluding them. **#NoUserLeftBehind**

## The basics

- **POUR.** Every WCAG rule sits under one of four principles: Perceivable, Operable, Understandable and Robust. Fail one and someone is shut out.
- **A, AA and AAA.** A is the bare minimum. AA is what most laws and policies ask for, and it's our bar. AAA is the highest.
- **It's not just colour contrast and screen readers.** Plan for vision, hearing, motor, cognitive and situational needs.

## Colour and contrast

- Text has a contrast ratio of at least 4.5:1 against its background. Large text (24px, or 18.66px bold) needs at least 3:1. *(1.4.3, AA)*
- Buttons, inputs, icons, focus outlines and chart lines have a contrast ratio of at least 3:1 against what's next to them. *(1.4.11, AA)*
- Never use colour alone to carry meaning. *(1.4.1, A)*
- Don't show status with coloured text alone. Red for error and green for success also need an icon and a text label.
- In charts, put labels next to the data and use patterns as well as colour. Avoid legends that only use colour.
- Check both themes. In light themes, light grey on white is the most common failure. In dark themes, pure white text glares, so use a slightly warm off-white that still passes.
- Pages still work in Windows High Contrast (forced colours) mode. Don't rely only on background images or box shadows for borders, icons or focus. *(Best practice)*

## Text and reading

- Body text is at least 16px, set in relative units (rem). *(Best practice)*
- Use tested, readable typefaces such as Inter, Open Sans or Atkinson Hyperlegible. No decorative, multicoloured or highly stylised fonts for reading text.
- No walls of text. Most people scan and read only about a fifth of the words on a page, so use short paragraphs, headings and lists, and put key information first.
- Use real text, not pictures of text. *(1.4.5, AA)*
- Text can be zoomed to 200% without losing content or features. Never turn off pinch zoom (`user-scalable=no`, `maximum-scale=1`). *(1.4.4, AA)*
- Nothing is cut off or overlaps when people increase spacing to these values: line height 1.5×, paragraph spacing 2×, letter spacing 0.12× and word spacing 0.16× the font size. *(1.4.12, AA)*
- Set the page language (`<html lang="en-GB">`), and mark any passage in another language with its own `lang`. *(3.1.1, A; 3.1.2, AA)*

## Layout, zoom and orientation

- Content reflows into one column at 320 CSS pixels wide (400% zoom on a 1280px screen), with no sideways scrolling. *(1.4.10, AA)*
- Work in both portrait and landscape unless one is essential. *(1.3.4, AA)*
- The visual order matches the order in the code. Screen readers follow the code, not the pixels. *(1.3.2, A)*
- Content that appears on hover or focus, like tooltips and popovers, can be closed with Esc, can be hovered over, and stays until it's dismissed. *(1.4.13, AA)*

## Motion, flashing and time limits

- Nothing flashes more than three times a second. Getting this wrong can cause seizures. *(2.3.1, A)*
- Anything that moves, blinks or scrolls by itself for more than 5 seconds has a pause, stop or hide control. That includes carousels and tickers. *(2.2.2, A)*
- Honour `prefers-reduced-motion` and keep movement to a minimum when it's on. *(2.3.3, AAA, which we treat as required)*
- Avoid time limits. Where one is needed, people can turn it off, adjust it or extend it. *(2.2.1, A)*

## Images

- Alt text describes what an image is for, not what it looks like: "Submit", not "blue rectangle with white text". *(1.1.1, A)*
- Decorative images get empty alt text (`alt=""`) so screen readers skip them. Don't add alt text to everything; only describe images that add information.
- Icon-only buttons and links have an accessible name, such as `aria-label` or visually hidden text. *(4.1.2, A)*
- Complex images like charts and diagrams have the data or a longer description close by.

## Audio and video

- Pre-recorded video has captions. A human checks auto-captions. *(1.2.2, A)*
- Live video has live captions. *(1.2.4, AA)*
- Audio-only content, like podcasts, has a text transcript. *(1.2.1, A)*
- If a video shows something important that nobody says out loud, add audio description. *(1.2.5, AA)*
- Never rely on sound alone. Pair every sound alert with something visible.
- Audio that plays by itself for more than 3 seconds can be paused, stopped or turned down. *(1.4.2, A)*

## Keyboard and focus

- Everything works with a keyboard alone. No exceptions. *(2.1.1, A)*
- Focus never gets trapped. People can always tab or Esc out of a component. *(2.1.2, A)*
- Don't build anything mouse-only. Hover-only tooltips, right-click menus and drag-only actions need a keyboard alternative.
- A "Skip to main content" link is the first thing that gets focus. *(2.4.1, A)*
- Tab order follows a logical reading order. Never use a positive `tabindex`. *(2.4.3, A)*
- Focus is always visible. Never remove the outline without a clear, high-contrast replacement. *(2.4.7, AA)*
- Sticky headers, cookie banners and chat widgets never fully hide the focused element. *(2.4.11, AA)*
- When a dialog opens, focus moves into it and stays there. Esc closes it, and focus goes back to whatever opened it.
- Keyboard shortcuts are welcome, but single-key shortcuts can be turned off or remapped, or only work when their component has focus. *(2.1.4, A)*

## Pointer, touch and voice

- Support every input: keyboard, mouse, touch, switches, voice control and eye tracking.
- Targets are at least 24×24 CSS pixels, or spaced so a 24px circle round each one doesn't overlap another. *(2.5.8, AA)* Aim for 44×44 on touch screens. *(2.5.5, AAA)*
- Anything you can drag can also be done with single taps or clicks. *(2.5.7, AA)*
- Pinch, swipe and multi-finger gestures have a single-tap alternative. *(2.5.1, A)*
- Actions happen on release, not on press, so people can slide off to cancel. *(2.5.2, A)*
- A control's accessible name includes its visible label, so voice users can say what they see. *(2.5.3, A)*
- Anything triggered by shaking or tilting the device also has a button, and the motion can be turned off. *(2.5.4, A)*

## Forms

- Every field has a visible label tied to it in code. Placeholder text isn't a label. *(3.3.2, A; 1.3.1, A)*
- Only ask for what you really need. Mark the optional fields, not the required ones.
- Personal-detail fields have the right `autocomplete` values so browsers and password managers can fill them in. *(1.3.5, AA)*
- Error messages say what went wrong and how to fix it, in text, next to the field. "Enter a date like 21/04/1990", not "Invalid input". *(3.3.1, A; 3.3.3, AA)*
- Don't make people re-enter something they've already given in the same process. *(3.3.7, A)*
- Before anything legal, financial or hard to undo is submitted, people can check, correct or cancel it. *(3.3.4, AA)*
- Focusing a field or choosing an option never submits the form or jumps to a new page by itself. *(3.2.1, A; 3.2.2, A)*
- Signing in never needs memory tests or puzzles. Allow pasting and password managers, or offer passkeys or email links. *(3.3.8, AA)*
- Split complex tasks into clear stages. Show progress, and let people save and come back.

## Structure and semantics

- Use the right HTML element for the job. A `div` with an `onClick` isn't a button. Native elements give you accessibility for free.
- Use headings in order (one `h1`, then `h2`, `h3`…) and landmarks: `header`, `nav`, `main`, `aside` and `footer`. *(1.3.1, A)*
- Headings and labels describe their topic or purpose. *(2.4.6, AA)*
- Every page has its own descriptive `<title>`. *(2.4.2, A)*
- Link text makes sense on its own. Avoid a bare "click here" or "read more". *(2.4.4, A)*
- Data tables use `<th>`, `scope` and `<caption>`. Never use tables for layout. *(1.3.1, A)*
- Custom components expose their name, role and state (expanded, selected, checked) to assistive technology. *(4.1.2, A)*
- There's more than one way to find a page, such as navigation, search or a sitemap. *(2.4.5, AA)*
- Instructions don't rely on shape, position or sound alone. "Select Continue", not "press the round button on the right". *(1.3.3, A)*

## ARIA and live updates

- No ARIA is better than bad ARIA. If a native element does the job, use it. ARIA changes what assistive technology announces, not how things behave.
- Content that changes without a page load, like a basket total or a new chat message, is in an `aria-live` region.
- Status messages like "Saved" or "3 results found" reach screen readers without moving focus. Use `role="status"`, or `role="alert"` for urgent messages. *(4.1.3, AA)*

## Content and clarity

- Write in plain language: short sentences and everyday words. GOV.UK aims for a reading age of 9, and experts prefer it too because it's quicker to read.
- Spell out acronyms and specialist terms the first time, or link to a glossary. *(3.1.3 and 3.1.4, AAA, which we treat as required)*
- Make it obvious what to do. Use explicit labels, clear calls to action and step-by-step guidance.
- Make interactive things look interactive (affordance). People shouldn't have to guess.
- Use clear states. People always know where they are, what just happened and what to do next, both visually and non-visually.
- Help people feel sure of what they did, with confirmation, undo and clear feedback.
- Offer fewer choices. Decision time grows with every option (Hick's Law).
- Keep it simple. Every extra layer of complexity is a possible barrier: "as simple as possible, but not simpler".
- Repeated navigation stays in the same place and order on every page. *(3.2.3, AA)*
- Things that do the same job have the same name and icon everywhere. *(3.2.4, AA)*
- Help, like a phone number, chat or FAQs, is in the same place on every page. *(3.2.6, A)*
- PDFs and other downloads are accessible too (tagged, with headings and a reading order), or have an HTML version.

## Testing

Automated checkers like axe and Lighthouse can't tell whether alt text makes sense, whether focus order is logical or whether a journey works. Run them, then test by hand.

1. **Keyboard.** Complete the task with only Tab, Shift+Tab, Enter, Space, the arrow keys and Esc.
2. **Screen reader.** Do a key task without looking, using VoiceOver, NVDA or TalkBack. Ten minutes teaches more than a checklist.
3. **Zoom and spacing.** Try 200% text zoom, 400% page zoom (320px wide) and increased text spacing.
4. **Preferences.** Turn on reduced motion, forced colours, and both light and dark mode.
5. **People.** Simulations aren't lived experience. Pay disabled people to take part in research and testing, from the start. *Nothing about us without us.*

## Definition of Done

If accessibility isn't in the Definition of Done, it gets left for later. A story isn't done until:

- [ ] It works with a keyboard alone, with visible focus and a logical order
- [ ] Text has at least 4.5:1 contrast, and controls and icons have at least 3:1
- [ ] Nothing relies on colour, sound, shape or position alone
- [ ] Images have the right alt text (or `alt=""`), and icon buttons have names
- [ ] Fields have visible labels and helpful error messages
- [ ] It works at 200% zoom and 320px wide
- [ ] Motion respects reduced motion, and nothing flashes
- [ ] It makes sense with a screen reader, including status messages
- [ ] Automated checks pass with no new issues

## Statements and procurement

- **Accessibility statement.** Say how accessible the service is, what doesn't work yet and how to get help. UK public sector sites must publish one.
- **VPAT and ACR.** A VPAT is a template. Once it's filled in, it becomes an Accessibility Conformance Report (ACR) showing how a product meets WCAG. Buyers ask for them.

## Sources

- WHO: [Blindness and vision impairment](https://www.who.int/news-room/fact-sheets/detail/blindness-and-visual-impairment) fact sheet
- WHO: World Report on Vision (via Down To Earth)
- WHO: [Disability](https://www.who.int/news-room/fact-sheets/detail/disability-and-health) fact sheet
- WHO: [Deafness and hearing loss](https://www.who.int/news-room/fact-sheets/detail/deafness-and-hearing-loss) fact sheet
- W3C: [Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/)
- GOV.UK: content design guidance (writing for a reading age of 9)
- Nielsen Norman Group: How Little Do Users Read? (people read about 20% of the words on a page)
- [Accessibility for Humans](https://cards.designedforhumans.tech): every card

---

From [Designed for Humans](https://designedforhumans.tech). Get the latest version at [github.com/pwilshaw/accessibility-md](https://github.com/pwilshaw/accessibility-md). Licensed CC BY 4.0.
