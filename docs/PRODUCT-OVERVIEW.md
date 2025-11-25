# **PRODUCT OVERVIEW (CANONICAL)**

**Last Updated:** 2025-11-25
**Status:** Locked for MVP Build (2–3 weeks)

---

## **1. WHAT WE'RE BUILDING**

A daily AI action library for small business owners that delivers industry-specific, copy-paste prompts for recurring operational problems.

**Product Type:** Pain-point browser (NOT a chatbot, NOT automation, NOT a workflow tool)

**Core Experience:**
1. User picks their industry
2. Sees 1 featured action + 3–4 recent actions (full scenario cards)
3. Copies prompt into ChatGPT
4. Gets reliable, industry-accurate output
5. Upgrades to pro for full library access

---

## **2. THE PROBLEM WE SOLVE**

Small business owners deal with the same stressful customer situations every week:
- Cancellations
- Price objections
- Refund requests
- No-shows
- Scope creep
- Quote negotiations

They want to use AI (they're already using ChatGPT) but **they don't know how to prompt it properly**.

Result: Generic outputs, wrong tone, wasted time, or just doing it manually.

**Our Solution:** Industry-specific, tested prompts that reliably produce the right output. No prompting skill required.

---

## **3. OUR MOAT: THE INDUSTRY OS**

The Industry OS is a structured knowledge system for each industry, built by AI agents.

### **3 Layers:**

**Layer 1: Scenarios (20–40 per industry)**
- Atomic units of value
- Each scenario = 1 high-friction moment
- Examples: "Client wants discount after quote", "Customer cancels 1 hour before"

**Layer 2: Business Logic Blocks**
- Reusable facts and rules
- Examples: pricing norms, cancellation policies, scope boundaries, safety rules
- Ensures consistency and accuracy

**Layer 3: Tone Model**
- Industry-specific communication style
- Examples: Trades = direct/practical, Hospitality = polite/guest-first
- Makes outputs feel "exactly like how we talk"

### **Why This Is Defensible:**

Every scenario is **agent-tested** before going live:
- 3+ LLM runs to check output stability
- Hallucination checks
- Tone matching
- Structure compliance

We're not a prompt library. We're a **tested, accurate, industry-intelligent system**.

---

## **4. MVP SCOPE (LOCKED)**

### **Industries: 3**
1. Home Services (contractors/trades)
2. Retail/E-commerce
3. Hospitality (restaurants, small hotels)

### **Scenarios: 60 total (20 per industry)**

### **Pages:**
1. **Landing** – industry selector
2. **Daily Feed** – 1 featured + 3–4 recent actions
3. **Pro Library** – all 60 scenarios, password-protected

### **Monetization:**
- **Free:** Daily feed (4–5 scenarios visible)
- **Pro:** $29/mo or $99 lifetime (full library access)
- **Paywall:** Gumroad + password gate (MVP) → Stripe later

### **Tech:**
- Static site (Astro or Next.js)
- No backend, no database, no auth
- JSON files for scenarios
- Vercel/Netlify hosting

---

## **5. THE CANONICAL SCENARIO STRUCTURE**

Every scenario card has this **exact structure** (non-negotiable):

```
[Industry Badge]
Day X • 3–5 min • Works with ChatGPT

THE SITUATION:
[1-sentence trigger]

THE AI ACTION:
[Benefit-focused explanation]

COPY & PASTE THIS:
[Prompt box with logic blocks baked in]

MAKE IT YOURS (optional):
1. [Specific customization note]
2. [Specific customization note]
3. [Specific customization note]

WHAT YOU'LL GET:
[2–3 sentence example output]

TIME SAVED:
~3 min per request
```

### **Why This Structure Never Changes:**
- Ensures stable LLM output
- Makes testing repeatable
- Creates predictable UX
- Builds user trust

---

## **6. AGENT WORKFLOW (HIGH-LEVEL)**

For MVP, agents run **locally/manually**. Post-MVP, they run automatically.

### **7 Stages:**

**1. Data Collection (Manual Agent-Assisted)**
- Scrape public Reddit, FB groups, Google reviews, FAQs, pricing pages
- 50–100 examples per industry

**2. Pattern Extraction**
- Agent clusters data into 20 recurring scenarios per industry
- Agent identifies frequency, pain level, importance

**3. Logic Block Extraction**
- Agent extracts business rules: pricing, cancellation policies, scope, tone patterns
- Creates reusable blocks per industry

**4. Scenario Generation**
- Agent creates 20 scenario cards per industry using canonical structure
- References logic blocks, not made-up facts

**5. Tone Encoding**
- Agent builds tone model per industry from communication patterns
- Defines greeting style, politeness level, phrases to use/avoid

**6. Self-Testing**
- Agent runs each scenario prompt 3x through OpenAI API
- Checks: no hallucinations, tone match, output stability, structure compliance
- Fails → regenerate → retest

**7. Manual Review**
- Human scans for: obvious bullshit, cringe, generic fluff, industry mismatch
- Approval threshold: 90% feel "suspiciously accurate"

---

## **7. ACCEPTANCE CRITERIA FOR SCENARIOS**

### **Agent Self-Test (Automated):**
- ✅ No hallucinations (no invented facts)
- ✅ Output stability (3 runs = similar results)
- ✅ Tone match (uses industry-appropriate language)
- ✅ Structure compliance (follows canonical format)

### **Manual Review (Human):**
- ✅ Reality check: "Would a real operator say 'yes, I deal with this'?"
- ✅ Cringe check: No corporate jargon, no over-explaining
- ✅ Usefulness check: "Can I copy-paste this right now and get value?"
- ✅ Trust check: "Would I send this output to a customer without heavy editing?"

### **Pass Threshold:**
- Agent: 100% pass on automated tests
- Manual: 90% of scenarios feel accurate

---

## **8. UX PRINCIPLES (NON-NEGOTIABLE)**

1. **Zero ambiguity** – User instantly knows: what problem this solves, what to paste, what they'll get
2. **Zero prompting required** – This is a browser of solutions, not a playground
3. **Zero friction** – No hidden content, no expanding cards, no "view details"
4. **Zero doubt** – Every card must feel like "I had this exact problem last week"

### **Design Inspiration:**
- **IdeaBrowser** – clean grid, depth through scroll, no chat interface
- **SaaS success dashboards** – show value immediately, no setup required

---

## **9. WHAT WE'RE NOT BUILDING (FOR MVP)**

- ❌ Chat interface
- ❌ Personalization or user input beyond industry selection
- ❌ Search functionality
- ❌ Category filters (maybe post-MVP)
- ❌ User accounts or auth
- ❌ Usage tracking
- ❌ Automation or workflows
- ❌ Email integration
- ❌ More than 3 industries
- ❌ More than 20 scenarios per industry

**Hard Rule:** NO new features until 10 paying customers.

---

## **10. MVP BUILD TIMELINE**

### **Week 1: OS Generation + Scenario Creation**
- Days 1–2: Data collection (scraping/manual)
- Days 3–4: Pattern extraction + logic blocks
- Days 5–7: Scenario generation + agent testing + manual review
- **Output:** 60 production-ready scenarios

### **Week 2: UI Build + Monetization**
- Days 8–10: Build static site (landing, daily feed, pro library)
- Day 11: Weighted rotation logic
- Day 12: Monetization setup (Gumroad + password gate)
- **Output:** Deployed MVP

### **Week 3: Polish + Launch**
- Days 13–14: Quality pass (test all prompts in ChatGPT)
- Day 15: Optional operator validation (2–3 real users)
- Days 16–17: Copy/design polish
- Days 18–19: Pre-launch testing
- Days 20–21: Launch
- **Output:** Live product, first users

---

## **11. TECH STACK**

### **Static Site:**
- **Framework:** Astro (recommended) or Next.js
- **Styling:** Tailwind CSS
- **Deployment:** Vercel or Netlify
- **Scenario storage:** JSON files in `/data` folder

### **Agent Stack:**
- **OS generation:** Claude 3.5 Sonnet API
- **Scenario testing:** GPT-4 API (cheaper for bulk)
- **Orchestration:** Node.js or Python scripts

### **Scraping:**
- **Reddit:** Pushshift API or manual
- **Reviews:** Outscraper
- **Web pages:** Firecrawl or manual copy-paste

### **Monetization:**
- **MVP:** Gumroad + password gate
- **Post-MVP:** Stripe Checkout + URL tokens

### **Analytics:**
- Plausible or Simple Analytics (privacy-friendly)

---

## **12. MONETIZATION STRUCTURE**

### **Free Tier (No Login):**
- 1 Featured Action (full scenario card) – rotates daily
- 3–4 Recent Actions (full cards)
- Ability to switch industries freely
- Copy prompts
- CTA: "Unlock Full Library"

### **Pro Tier ($29/mo or $99 lifetime):**
- Full library (60+ scenarios across 3 industries)
- Password-protected static page
- No dashboards, no sync, no accounts
- Instant access after payment

### **Paywall Flow:**
1. User sees free scenarios
2. Clicks "Unlock Full Library"
3. Gumroad checkout ($29/mo or $99 lifetime)
4. Payment confirmation includes password
5. User enters password on `/pro` page
6. Sees full grid of 60 scenarios

---

## **13. DAILY ROTATION LOGIC (SIMPLE FOR MVP)**

Each scenario has metadata:
```json
{
  "id": "home-services-discount-objection",
  "industry": "home-services",
  "situation": "Client asks for discount...",
  "importance": 9,
  "frequency": 8,
  "painScore": 9
}
```

**Featured Action = highest (importance + frequency + painScore)**

**Recent 3–4 = random sample from top 10**

For MVP, can hardcode rotation (Day 1 = scenario X, Day 2 = scenario Y).

---

## **14. RISK MITIGATION**

### **Risk 1: Scenarios feel generic**
- **Mitigation:** Test 5 scenarios with 2–3 real operators (Reddit DMs)
- **Fallback:** Regenerate with stricter prompts emphasizing specificity

### **Risk 2: Agent output quality varies**
- **Mitigation:** Run self-test 3x per scenario + manual review
- **Fallback:** Write 5–10 gold standard examples manually, use to improve agent

### **Risk 3: No conversions**
- **Mitigation:** Free tier must deliver "holy shit" value
- **Fallback:** Make library free temporarily, collect emails, validate demand

### **Risk 4: Scope creep**
- **Mitigation:** Hard rule – NO new features until 10 paying customers

---

## **15. POST-MVP ROADMAP (WEEK 4+)**

Only after hitting **10 paying customers** or **$500 MRR**:

1. Add 2 more industries (real estate, beauty/wellness)
2. Add search to pro library
3. Automate agent cycles (weekly OS updates)
4. Migrate to Stripe (better analytics)
5. Add usage tracking
6. Improve scenarios based on user feedback

---

## **16. SUCCESS METRICS**

### **Week 1 (Launch Week):**
- 100+ landing page visits
- 20+ industry selections
- 5+ "holy shit this is real" Reddit comments

### **Month 1:**
- 500+ landing visits
- 50+ daily active users
- 5 paying customers ($145 MRR minimum)
- 10% conversion rate (free → pro)

### **Month 3:**
- $1,000 MRR
- 50 paying customers
- 80% retention rate
- Clear demand for 2 additional industries

---

## **17. KEY PRINCIPLES (NEVER COMPROMISE ON THESE)**

1. **Pattern-level accuracy > word-for-word precision**
   - Operators need to feel understood, not perfectly matched

2. **The Industry OS is the moat**
   - Everything else is replaceable

3. **Consistency = trust = retention**
   - Never let scenario structure drift

4. **Simple > clever**
   - Static site beats complex backend
   - Password gate beats auth system
   - Manual agent runs beat automated pipelines (for MVP)

5. **Quality > quantity**
   - 20 great scenarios > 40 mediocre ones

6. **Ship fast, learn faster**
   - MVP in 3 weeks, iterate based on real usage

---

## **18. WHAT MAKES THIS WORK**

**Not the UI.**
Not the daily mechanic.
Not the monetization model.

**The Industry OS.**

If scenarios feel suspiciously accurate → users trust → users pay → we win.
If scenarios feel generic → users leave → we fail.

Spend 60% of time on scenario quality.

---

## **19. ONE-LINE PRODUCT VISION**

**A pattern-driven AI action library that gives small business owners instantly usable, industry-specific operational solutions — built entirely through AI agents that encode each industry's real-world business logic.**

---

## **20. WHEN TO USE THIS DOC**

Use this doc to align:
- New AI agents starting work
- Your own context when resuming after a break
- Any collaborators or advisors
- Decision-making (does this align with the vision?)

**If something conflicts with this doc, the doc wins.**

---

**END OF PRODUCT OVERVIEW**

*This is the canonical source of truth. All other docs are context or history.*
