# 201-Reading_05

# Images, Accessibility, and CSS Styling

## Approaching Accessibility-Centered Design

This topic matters because images, color, and text styling are core parts of how users experience a website. As I continue learning HTML and CSS, understanding accessibility ensures that what I build can be used by as many people as possible, including users who rely on assistive technologies. Styling choices such as color, fonts, and spacing also directly affect readability, usability, and the overall professionalism of a site.

---

## Images & Accessibility

### What is a real-world use case for the `alt` attribute being used in a website?

A real-world use case for the `alt` attribute is assisting users who rely on screen readers. For example, on an e-commerce website, an image of a product should include alt text describing the item so visually impaired users understand what is being displayed. Alt text is also helpful when images fail to load, as it provides meaningful information in place of the image.

---

### How can you improve accessibility of images in an HTML document?

You can improve accessibility of images by:
- Adding clear, descriptive `alt` text to all meaningful images
- Using empty alt attributes (`alt=""`) for purely decorative images
- Ensuring sufficient color contrast between images and backgrounds
- Using semantic elements such as `<figure>` and `<figcaption>` when context is needed
- Making images responsive so they scale properly when users zoom in

---

### Provide an example of when the `figure` element would be useful in an HTML document

The `figure` element is useful when an image needs additional explanation. For example, in a blog post displaying a chart or photograph, the image can be wrapped in a `<figure>` element with a `<figcaption>` describing what the image represents. This helps users understand the purpose of the image, especially those using screen readers.

---

### Describe the difference between a GIF image and an SVG image (explained simply)

A GIF is like a short animated flipbook made from pictures. It works well for simple animations but can look blurry and take up more space.

An SVG is more like a drawing created with math instead of pixels. It stays sharp at any size and is ideal for logos and icons. SVGs do not lose quality when zoomed in.

---

### What image type would you use to display a screenshot on your website and why?

I would use a PNG image for a screenshot because it preserves sharp text and interface details. Screenshots often contain text, and PNG files maintain clarity without compression artifacts.

---

## Learn CSS: Using Color and Styling Text

### Describe the difference between foreground and background colors (non-technical explanation)

The foreground color is the color of the text you read, while the background color is the surface the text sits on. For example, black words on a white page use black as the foreground color and white as the background color. Good contrast between the two makes content easier to read.

---

### How would you use color to give a colorless blog some character?

To add character to a colorless blog, I would:
- Choose an accent color for headings and links
- Use a soft background color instead of pure white
- Add hover effects to links for visual feedback
- Use subtle color highlights for quotes or section dividers

This approach adds personality without overwhelming the reader.

---

### What should you consider when choosing fonts for an HTML document?

When choosing fonts, you should consider:
- Readability on different devices and screen sizes
- Accessibility and legibility
- The tone and purpose of the content
- Browser compatibility and fallback fonts
- Limiting the number of fonts to keep the design consistent

---

### What do `font-size`, `font-weight`, and `font-style` do?

- `font-size` controls how large or small the text appears
- `font-weight` controls how bold or light the text is
- `font-style` controls stylistic changes such as italics

These properties help organize content and emphasize important information.

---

### Describe two ways to add spacing around the characters displayed in an `h1` element

Two ways to add spacing around characters in an `h1` element are:
1. Using `letter-spacing` to increase space between individual characters
2. Using `padding` to add space around the text inside the heading element

## Sources & Notes

- Course readings and assigned videos for this module
- Web Accessibility and CSS fundamentals 

**Sources:**

- [Deque University](https://dequeuniversity.com)
- [Harvard University Accessibility](https://accessibility.harvard.edu/)
- [Section508.gov](https://www.section508.gov)

## Accessibility Tools & Guidelines

Based on accessibility best practices from Deque University, Harvard, and Section508.gov, alternative (alt) text for visually impaired users should be concise (1–2 sentences), context-driven, and avoid phrases like “image of.” Alt text should communicate the image’s purpose or essential information rather than only describing visual details.

### Visual Impairment Simulations (Deque University)

Deque University provides visual impairment simulations that help non-visually impaired designers and developers understand how users with low vision or color blindness experience the web. These simulations are useful for building empathy and making more informed design decisions.

- [Deque University – Visual Impairment Simulations](https://dequeuniversity.com/class/visual-impairments)

---

### Web Content Accessibility Guidelines (WCAG)

The Web Content Accessibility Guidelines (WCAG) define international standards for making web content more accessible to people with disabilities. These guidelines are widely used in professional and legal accessibility requirements.

- [WCAG 2.2 – Latest Version (W3C)](https://www.w3.org/TR/WCAG22/)

---

### Lighthouse Accessibility Meter

Lighthouse is an automated auditing tool built into Chrome DevTools that evaluates a website’s accessibility, performance, and best practices. The accessibility score highlights issues such as missing alt text, low color contrast, and improper semantic structure.

- [Google Lighthouse – Accessibility Audits](https://developer.chrome.com/docs/lighthouse/accessibility/)

---

### These Tools Matter

Using accessibility guidelines alongside testing tools helps ensure that websites are usable by a wide range of people. Visual simulations build empathy, WCAG provides standards, and Lighthouse offers measurable feedback during development.

## Additional Accessibility Resources for Coders

The following websites provide tools, guidelines, and practical examples to help developers build more accessible websites and applications.

### WebAIM (Web Accessibility In Mind)
WebAIM is a widely respected accessibility organization that offers clear explanations, checklists, and testing tools for developers.

- https://webaim.org
- https://webaim.org/resources/contrastchecker/

---

### W3C Web Accessibility Initiative (WAI)
The W3C WAI develops accessibility standards and educational resources, including ARIA documentation and accessibility tutorials.

- https://www.w3.org/WAI/
- https://www.w3.org/WAI/tutorials/

---

### MDN Web Docs — Accessibility
MDN provides developer-friendly documentation on accessibility built directly into HTML, CSS, and JavaScript practices.

- https://developer.mozilla.org/en-US/docs/Web/Accessibility

---

### A11y Project
The A11y Project offers a practical, community-driven checklist and pattern library for building accessible web interfaces.

- https://www.a11yproject.com
- https://www.a11yproject.com/checklist/

---

### Axe by Deque Systems
Axe provides automated accessibility testing tools commonly used in professional development workflows.

- https://www.deque.com/axe/
- https://www.deque.com/axe/devtools/

---

### Section 508 (U.S. Government Accessibility Standards)
Section 508 outlines legal accessibility requirements for federal websites and contractors.

- https://www.section508.gov

---

### Inclusive Design Principles
This site focuses on designing for diverse users and real-world accessibility scenarios.

- https://inclusivedesignprinciples.org

---

### Google Accessibility
Google provides accessibility guidelines and tools for web, Android, and general UI development.

- https://www.google.com/accessibility/
- https://web.dev/accessibility/

---

### Screen Reader Resources (Testing & Understanding)
Learning how screen readers work helps developers test real-world accessibility.

- NVDA (Free, Windows): https://www.nvaccess.org/
- VoiceOver (Built into macOS & iOS): https://support.apple.com/guide/voiceover/

## Reading_05 Web Accessibility 101

### How This Presentation Will Change My Career Approach

Dezireé Teague’s *Web Accessibility 101* presentation reframed how I approach accessibility as I transition into a career in tech. Rather than treating accessibility as an optional feature or compliance task, this session emphasized its role as a core part of ethical, user-centered development. Going forward, I plan to integrate accessibility considerations into my workflow from the beginning of each project, particularly when writing semantic HTML and designing user interactions.

### Key Takeaways

- Accessibility improves usability for all users, not only those with disabilities.
- Semantic HTML is essential for screen readers and assistive technologies.
- Thoughtful design choices such as color contrast, labels, and heading structure have a significant impact.
- Building accessibility into projects early reduces technical debt.
- Inclusive design reflects professionalism and empathy in software development.

### Professional Outreach

- Sent a LinkedIn connection request

