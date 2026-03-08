# Vi-Well
The Vi-Well package contains three new sections for the Vivirion website: an AI-powered mental health resource, a place where users can make informed decisions finding their personal mental health professional, and a landing page to sell the experience to those looking for help.
----------------------------
OUR PROCESS:
----------------------------

Update 1: Used a multi-layered prompt generation process to create a prompt for Antigravity to create a website for Vi-Well. Our initial prompt was:


----------------------------

Build a full mental health support page for Vivirion (vivirion.com) — a healthcare empowerment platform for professionals and patients. This page should feel warm, safe, and clinically grounded. It is NOT a therapy app; it is a bridge between patients in need and qualified professionals affiliated with Vivirion.

---

BRAND CONTEXT:
- Vivirion's tone: empowering, human, modern, evidence-informed
- Audience: patients seeking mental health support (broad age range, varying familiarity with mental health language)
- Color palette: use calm, grounding tones — deep teal, soft sage, warm off-white, with muted gold accents
- Typography: a humanist serif for headings (trust + warmth), a clean sans-serif for body (readability)
- The page should feel like a safe room, not a clinical form

---

PAGES & SECTIONS TO BUILD:

ASSESSMENT PAGE:
1. HERO SECTION
   - Headline: "You Don't Have to Navigate This Alone"
   - Subheading: A one-liner about Vivirion connecting patients with the right mental health support, tailored to them
   - Two CTAs side by side: "Take the Assessment" (primary) and "Find a Professional" (secondary)
   - Subtle animated background — soft breathing gradient or gentle particle field in teal/sage tones
   - Add a small trust signal strip below hero: "Confidential | Evidence-Informed | Matched to You"

2. HOW IT WORKS (3-step horizontal strip)
   - Step 1: "Share What You're Experiencing" — answer a few guided questions
   - Step 2: "Get Your Personal Snapshot" — receive an AI-generated summary of your needs
   - Step 3: "Connect With the Right Support" — matched Vivirion professionals + external resources
   - Clean icon + label + short description layout, connected by a subtle progress line

3. AI-POWERED MENTAL HEALTH ASSESSMENT MODULE
   This is a multi-step conversational intake, NOT a form dump. Build it as a step-by-step card flow with progress indicator.

   ASSESSMENT LOGIC (build as sequential screens):

   Screen 1 — Emotional Check-In
   "How have you been feeling lately, overall?"
   Options (tap to select): Anxious / Low or depressed / Overwhelmed / Disconnected / Burnt out / Not sure / A mix of things

   Screen 2 — Duration
   "How long have you been feeling this way?"
   Options: A few days / A few weeks / A few months / Longer than 6 months / It comes and goes

   Screen 3 — Impact
   "Is this affecting your daily life?" (multi-select)
   Options: Sleep / Work or study / Relationships / Appetite / Motivation / Concentration / Physical health / I'm managing okay

   Screen 4 — Support History
   "Have you spoken to a professional about this before?"
   Options: Never / Yes, in the past / Currently seeing someone / I tried but it didn't help / Not sure where to start

   Screen 5 — What You're Looking For
   "What kind of support feels right for you right now?" (multi-select)
   Options: Someone to talk to / Practical strategies / Medication guidance / Crisis support / I don't know yet / Just want to understand what I'm feeling

   Screen 6 — Safe Space Check
   "Are you currently having thoughts of harming yourself or others?"
   Options: No / Sometimes / Yes, right now
   — If "Yes, right now" is selected: immediately surface crisis resources (988 Lifeline, Crisis Text Line, local emergency services) with a warm, non-alarmist message: "Thank you for telling us. Please reach out to one of these right now — support is available 24/7."
   — If "Sometimes": surface crisis resources AND continue assessment with a care note

   RESULTS SCREEN:
   After completion, display:
   - A personalized summary paragraph based on their answers (use AI to generate this dynamically, written in warm second-person: "Based on what you've shared, it sounds like you may be experiencing...")
   - A non-diagnostic label (e.g., "Signs of anxiety-related stress" / "Burnout indicators" / "Low mood patterns") — clearly labeled as informational, not diagnostic
   - Recommended next step (e.g., "We recommend connecting with one of our licensed therapists who specializes in anxiety and work-related stress")
   - Two CTAs: "Match Me With a Professional" and "Explore Self-Help Resources"

PROFESSIONAL MATCHING & RESOURCES PAGE:
4. PROFESSIONAL MATCHING MODULE
   - Triggered from the assessment results OR accessible standalone via "Find a Professional" CTA
   - Display 3–4 Vivirion-affiliated professional cards (placeholder data for now) showing:
     • Name, photo, credentials (e.g., "Licensed Psychotherapist | CBT Specialist")
     • Areas of focus (e.g., Anxiety, Trauma, Burnout, Adolescent Mental Health)
     • Availability badge (e.g., "Accepting new patients")
     • A "Connect" button that opens a contact/booking modal
   - Include a subtle filter row above cards: filter by specialty, session type (virtual/in-person), language
   - Below the cards, add: "Don't see the right fit? Our team will personally match you." + email CTA

5. EXTERNAL RESOURCES LIBRARY
   Build as a clean card grid (3 columns desktop, 1 column mobile):
   
   Category tags to include:
   - Crisis Support: 988 Suicide & Crisis Lifeline, Crisis Text Line (Text HOME to 741741), International Association for Suicide Prevention directory
   - Apps & Tools: Woebot (AI CBT), Headspace, Calm, Wysa
   - Self-Assessment Tools: PHQ-9 (depression), GAD-7 (anxiety), link to NAMI screening tools
   - Communities & Peer Support: 7 Cups, NAMI peer groups, Mental Health America
   - For Healthcare Professionals: Physician Support Line, Therapist Aid worksheets, APA resources
   
   Each card: icon, title, one-line description, category tag, "Visit Resource" link
   Add a note at the top: "These resources are curated by Vivirion's clinical team. We update them regularly."

6. DESTIGMATIZATION STRIP
   A full-width emotional section with a soft gradient background
   Headline: "Mental health is health. Asking for help is strength."
   Below: 2–3 short anonymous patient quotes (placeholder) in a carousel or static layout
   Keep this section visually distinct — warmer, softer, more human than the rest of the page

---

DESIGN & UX REQUIREMENTS:
- Mobile-first, fully responsive
- Assessment module must feel conversational — animate between screens with a smooth slide/fade, show a progress bar at top
- All AI-generated result text include a disclaimer: "This is not a medical diagnosis. Please consult a qualified professional."
- WCAG AA accessibility compliance (contrast, focus states, aria labels)
- Crisis detection in Screen 6 is never skipped or hidden; resources are always displayed if triggered
- Smooth anchor navigation from hero CTAs to relevant sections
- Page should load with a subtle fade-in stagger on hero elements

---

COPY TONE GUIDELINES:
- Never clinical or cold
- Never dismissive or minimizing ("just anxiety", "try to relax")
- Always validating and human
- Use second person ("you", "your") throughout
- Avoid jargon — write for someone who has never seen a therapist before
- Encourage action without pressure

---

TECHNICAL NOTES:
- Assessment logic should be component-based so each screen is independently editable
- Professional cards should be data-driven (array of objects) for easy real-data swap
- Resource library should be filterable by category tag
- Use localStorage to save assessment progress so users don't lose answers on refresh
- The AI summary on the results screen should call an LLM API endpoint (placeholder: /api/mental-health-summary) with the user's answer payload
