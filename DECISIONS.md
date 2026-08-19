# DECISIONS.md

| | |
|---|---|
| **Candidate** | Risika Kumari |
| **Course** | BCA (Data Science), Lovely Professional University |
| **Track** | Part 2 — The Premium Home Page |
| **Project** | Fix My City — civic issue reporting home page |

---

## 1. Why this approach over the alternative I rejected

I considered a straightforward "generic SaaS" landing page — hero, feature grid, testimonials — and rejected it because the brief's own grading criteria call that out directly: it wants a page that shows the product, not just claims about it, and it explicitly bans fake testimonials and fake numbers.

So instead of a features list, I built the hero around a working interaction: you click the photo box and watch it actually run through the classification and routing steps — *Analyzing → Detected: Streetlight → Routed to department → Complaint #48291 created*. That's harder to build than a static hero, but it's the difference between telling someone the app is smart and showing them.

I also rejected filling the page with invented stats ("10,000+ tickets resolved") to make it look more mature. Since this is a pre-launch concept, I labeled the live-tickets map as illustrative rather than pretending it's real traffic.

> I'd rather the page read as honest and early-stage than dishonest and "finished."

---

## 2. One trade-off under the time limit, and what I'd do with a real week

**Trade-off:** the "AI classification" in the demo is scripted — it always detects the same streetlight issue with the same ticket number, rather than actually running an image classifier or connecting to a backend.

**With a real week**, I'd wire this to a real model — even a small pretrained image classifier for the 7 categories — and a lightweight backend so the ticket number, location, and department routing were generated dynamically instead of hardcoded. I'd also replace the mock map with real geolocation and a persistence layer so tickets submitted in the demo actually showed up on the map.

---

## 3. Where I used AI tools, and what I personally verified or changed

I used Claude to generate the majority of the HTML/CSS/JS for this page — the layout, the interactive demo card, the animated ticket pipeline, and the map mockup. The timeline for this assignment was tight, and I wanted the visual and interaction quality to be as strong as possible within that window.

**What I personally checked and adjusted:**

- Reviewed every section against the brief's requirements line by line — hero + CTA, a section that shows the product not just claims, one deliberate micro-interaction, working dark mode, mobile at 390px / desktop at 1440px — to confirm nothing was missing.
- Tested the interactive demo, the pipeline animation, the map tooltips, and the dark/light toggle myself in the browser to confirm they actually worked, not just looked right in code.
- Checked the copy for anything that could read as a fake stat or fake testimonial, and rewrote the "honesty" section myself to describe the map accurately as illustrative — the one thing I didn't want to get wrong given how much the rubric emphasizes it.
- Can walk through and explain every CSS/JS decision in the follow-up call: the color and type choices, why the pipeline uses a scroll-triggered animation instead of autoplay, and why the map is SVG-based rather than a real map API (no API key, and it wasn't necessary to prove the interaction pattern).
