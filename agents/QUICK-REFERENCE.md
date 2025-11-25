# **QUICK REFERENCE CHEAT SHEET**

Use this when you need to remember key structures, formats, or criteria without reading full prompts.

---

## **THE 7 STAGES (IN ORDER)**

1. **Data Collection** → 50–100 examples per industry
2. **Pattern Extraction** → 20 scenarios with scores
3. **Logic Block Extraction** → 25–40 business rules
4. **Scenario Generation** → 20 complete scenario cards
5. **Tone Modeling** → Industry communication style (run before Stage 4)
6. **Self-Testing** → 3 runs per scenario, 5 criteria
7. **Manual Review** → Reality, cringe, trust, usefulness checks

---

## **CANONICAL SCENARIO STRUCTURE**

```
[Industry Badge]
Day X • 3–5 min • Works with ChatGPT

THE SITUATION:
[1-sentence trigger, 15–25 words]

THE AI ACTION:
[2–3 sentences explaining benefit, not mechanics]

COPY & PASTE THIS:
[4–8 sentence prompt with logic blocks + placeholders + tone guidance]

MAKE IT YOURS:
1. [Specific customization]
2. [Specific customization]
3. [Specific customization]

WHAT YOU'LL GET:
[2–3 sentence realistic example output]

TIME SAVED:
~X min per [occurrence]
```

---

## **LOGIC BLOCK CATEGORIES**

1. **Pricing** (service fees, travel charges, deposits, markup)
2. **Cancellation** (notice period, fees, exceptions)
3. **Scope** (what's included, excluded, add-ons)
4. **Refunds** (when given, when not, partial vs full)
5. **Communication** (tone rules, boundary-setting, empathy)
6. **Objections** (common pushbacks + how to respond)
7. **Custom** (industry-specific rules)

**Target:** 25–40 rules total across all categories

---

## **TONE MODEL COMPONENTS**

1. **Overall Style** (formality, warmth, directness, confidence)
2. **Sentence Structure** (length, complexity, paragraph length)
3. **Vocabulary** (common terms, informal phrases, professional phrases)
4. **Greeting Patterns** (how they start messages)
5. **Closing Patterns** (how they end messages)
6. **Phrases to Use** (authentic operator language)
7. **Phrases to Avoid** (corporate jargon)
8. **How to Say No** (approach + examples)
9. **How to Set Boundaries** (approach + examples)
10. **Empathy Phrases** (show understanding)
11. **Confidence Phrases** (show competence)

---

## **SELF-TEST CRITERIA (5 CHECKS)**

### **1. No Hallucinations**
Output only uses info from prompt, no invented facts

### **2. Output Stability**
3 runs produce similar quality/tone/structure

### **3. Tone Match**
Output matches industry tone model

### **4. Structure Compliance**
Output follows format specified in prompt

### **5. Usefulness**
80%+ ready to send, minimal editing needed

**Pass threshold:** All 5 criteria must pass for 2+ out of 3 runs

---

## **MANUAL REVIEW QUESTIONS (4 CHECKS)**

### **1. Reality Check**
"Would a real operator say 'Yes, I deal with this'?"

### **2. Cringe Check**
"Is anything corporate, fake, or off-putting?"

### **3. Trust Check**
"Would I send this output to a customer?"

### **4. Usefulness Check**
"Does this solve the friction in under 5 minutes?"

**Pass threshold:** All 4 questions = YES

---

## **SCENARIO METADATA STRUCTURE**

```json
{
  "id": "discount-after-quote",
  "title": "Client wants discount after receiving your quote",
  "description": "Customer asks for lower price after estimate...",
  "industry": "home-services",
  "importance": 9,
  "frequency": 8,
  "painScore": 7,
  "totalScore": 24,
  "day": 1
}
```

**Rotation order:** Sort by totalScore (highest = Day 1)

---

## **PASS/FAIL THRESHOLDS**

### **Stage 6 (Self-Testing):**
- ✅ **PASS:** 80%+ scenarios pass all tests (16+ out of 20)
- ❌ **FAIL:** Below 80%, refine and retest

### **Stage 7 (Manual Review):**
- ✅ **PASS:** All 4 checks positive
- ⚠️ **NEEDS REFINEMENT:** 3/4 checks positive
- ❌ **FAIL:** 2 or fewer checks positive

### **Overall MVP Quality Gate:**
- ✅ **Ready to ship:** 18–20 scenarios per industry passed
- ⚠️ **Needs work:** 15–17 scenarios passed, fix rest
- ❌ **Not ready:** Below 15 scenarios passed, major revision needed

---

## **FILE NAMING CONVENTION**

```
/data/
  home-services/
    raw-data.txt
    scenarios.json
    logic-blocks.json
    tone-model.json
    scenarios-complete.md
    test-results.md
    review-report.md

  retail/
    [same structure]

  hospitality/
    [same structure]
```

---

## **INDUSTRIES (PICK 3 FOR MVP)**

**Recommended:**
1. **Home Services** (contractors, plumbers, HVAC, electricians)
2. **Retail/E-commerce** (small online stores, boutiques)
3. **Hospitality** (restaurants, small hotels, cafes)

**Alternatives:**
4. Real Estate (agents, small brokerages)
5. Beauty/Wellness (salons, spas, massage therapists)

---

## **TIME ESTIMATES**

| Stage | Per Industry | For 3 Industries |
|-------|--------------|------------------|
| Data Collection | 2–3 hr | 6–9 hr |
| Pattern Extraction | 30–60 min | 1.5–3 hr |
| Logic Blocks | 45–90 min | 2–4.5 hr |
| Scenario Generation | 2–3 hr | 6–9 hr |
| Tone Modeling | 30–45 min | 1.5–2.25 hr |
| Self-Testing | 1–2 hr | 3–6 hr |
| Manual Review | 30–60 min | 1.5–3 hr |
| **TOTAL** | **8–12 hr** | **24–36 hr** |

**Spread across 7 days = 3.5–5 hours per day**

---

## **EXAMPLE PROMPTS (COPY-PASTE READY)**

### **For Pattern Extraction (Stage 2):**
```
I have collected 80 examples of operational pain points for [INDUSTRY].

Your task:
1. Read through all examples
2. Cluster them into 20 recurring high-friction scenarios
3. Title each scenario (8-12 words, action-oriented)
4. Score each: importance (1-10), frequency (1-10), painScore (1-10)
5. Output as JSON

[Paste raw data here]
```

### **For Logic Block Extraction (Stage 3):**
```
Extract business logic rules for [INDUSTRY] from the following data.

Categories:
- Pricing rules
- Cancellation policies
- Scope boundaries
- Refund policies
- Communication standards
- Common objections

Output as JSON with 25-40 total rules.

[Paste raw data + website policies here]
```

### **For Scenario Generation (Stage 4):**
```
Generate a complete scenario card for [INDUSTRY] using the canonical structure.

Input:
- Scenario: [paste from Stage 2]
- Logic blocks: [paste from Stage 3]
- Tone model: [paste from Stage 5]

Output: Full markdown scenario card following EXACTLY this structure:
[Paste canonical structure here]
```

---

## **RED FLAGS (STOP AND FIX)**

### **During Data Collection:**
❌ Less than 30 examples → Not enough signal
❌ All examples from one source → Biased data
❌ No operator perspectives → Missing authenticity

### **During Scenario Generation:**
❌ Prompts reference policies not in logic blocks → Hallucinations
❌ Example output sounds corporate → Tone mismatch
❌ Situations too vague ("handle customers") → Not specific enough

### **During Testing:**
❌ Outputs vary wildly between runs → Unstable prompt
❌ Any hallucinations → FAIL immediately
❌ Tone feels fake → Regenerate with stricter tone guidance

### **During Manual Review:**
❌ "I wouldn't send this" → Not production-ready
❌ "This feels generic" → Lacks industry specificity
❌ "Too much work to customize" → Prompt too complex

---

## **SHORTCUTS (IF RUNNING OUT OF TIME)**

### **Option 1: Reduce scenarios per industry**
- Instead of 20 → do 15 high-quality ones
- Only generate top 15 by totalScore

### **Option 2: Reduce industries**
- Instead of 3 → do 2 really well
- Pick Home Services + Hospitality (clearest pain points)

### **Option 3: Simplify testing**
- Instead of 3 runs per scenario → do 2
- Instead of testing all 20 → test top 10, spot-check rest

### **Option 4: Skip real operator validation**
- Move straight to launch
- Validate with real users post-launch

**DO NOT SKIP:**
- ❌ Logic block extraction (accuracy depends on this)
- ❌ Tone modeling (authenticity depends on this)
- ❌ Self-testing for hallucinations (trust depends on this)

---

## **WEEK 1 SUCCESS CRITERIA**

By end of Day 7, you must have:
- [ ] 54–60 total scenarios (18–20 per industry)
- [ ] All scenarios tested (no hallucinations)
- [ ] All scenarios manually reviewed (passed 4 checks)
- [ ] Logic blocks documented per industry
- [ ] Tone models documented per industry
- [ ] High confidence in quality (80%+ scenarios feel accurate)

**If yes to all → Ready for Week 2 (UI build)**
**If no → Spend 1–2 extra days refining before building**

---

## **EMERGENCY CONTACT**

If you're stuck for >2 hours on any stage:
1. Re-read the stage-specific prompt
2. Check PRODUCT-OVERVIEW.md for alignment
3. Simplify the task (reduce scope, easier industry)
4. Ask in relevant communities (show your work, ask specific questions)
5. Take a break, come back fresh

**Remember: Done > Perfect. Ship Week 1 by Day 7.**

---

**END OF QUICK REFERENCE**
