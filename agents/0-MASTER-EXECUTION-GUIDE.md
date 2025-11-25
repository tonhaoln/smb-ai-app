# **MASTER EXECUTION GUIDE**

**Purpose:** Step-by-step instructions to generate 60 production-ready scenario cards
**Timeline:** Week 1 (Days 1–7)
**Output:** 3 industries × 20 scenarios = 60 complete, tested scenario cards

---

## **OVERVIEW**

You'll run 7 stages for each of 3 industries:

1. **Data Collection** (2–3 hours per industry)
2. **Pattern Extraction** (30–60 min per industry)
3. **Logic Block Extraction** (45–90 min per industry)
4. **Scenario Generation** (2–3 hours per industry)
5. **Tone Modeling** (30–45 min per industry) – *Run before or parallel to Stage 4*
6. **Self-Testing** (1–2 hours per industry)
7. **Manual Review** (30–60 min per industry)

**Total time per industry:** 8–12 hours
**Total time for 3 industries:** 24–36 hours across 7 days

---

## **RECOMMENDED SCHEDULE**

### **Day 1–2: Data Collection (All 3 Industries)**

**Goal:** Collect 50–100 examples per industry

**Actions:**
1. Read [1-data-collection-prompt.md](1-data-collection-prompt.md)
2. For each industry (Home Services, Retail, Hospitality):
   - Search Reddit, Facebook, Google Reviews
   - Copy-paste 50–100 pain point examples
   - Save as: `home-services-raw-data.txt`, `retail-raw-data.txt`, `hospitality-raw-data.txt`
3. Visit 10–15 service websites per industry
   - Copy FAQs, pricing pages, cancellation policies
   - Save as: `home-services-website-data.txt`, etc.

**Time:** 2–3 hours per industry (6–9 hours total)

**Tip:** Do all 3 industries in one sitting to maintain momentum.

---

### **Day 3: Pattern Extraction + Tone Modeling (Industry 1)**

**Goal:** Extract 20 scenarios + tone model for Industry 1 (Home Services)

**Actions:**
1. Read [2-pattern-extraction-prompt.md](2-pattern-extraction-prompt.md)
2. Paste raw data into Claude
3. Run pattern extraction prompt
4. Get 20 scenarios with scores
5. Save as: `home-services-scenarios.json`

6. Read [5-tone-modeling-prompt.md](5-tone-modeling-prompt.md)
7. Run tone modeling prompt with same raw data
8. Get tone model JSON
9. Save as: `home-services-tone-model.json`

**Time:** 1–1.5 hours total

---

### **Day 4: Logic Blocks + Scenario Generation (Industry 1)**

**Goal:** Extract logic blocks and generate 20 complete scenarios for Industry 1

**Actions:**
1. Read [3-logic-block-extraction-prompt.md](3-logic-block-extraction-prompt.md)
2. Run logic block extraction prompt
3. Save as: `home-services-logic-blocks.json`

4. Read [4-scenario-generation-prompt.md](4-scenario-generation-prompt.md)
5. Input: scenarios.json + logic-blocks.json + tone-model.json
6. Run scenario generation for all 20 scenarios
7. Save as: `home-services-scenarios-complete.md`

**Time:** 3–4 hours

---

### **Day 5: Testing + Review (Industry 1)**

**Goal:** Test and validate all 20 scenarios for Industry 1

**Actions:**
1. Read [6-self-testing-prompt.md](6-self-testing-prompt.md)
2. For each scenario:
   - Copy prompt
   - Fill in placeholders
   - Run through ChatGPT 3 times
   - Check against 5 criteria
3. Save results: `home-services-test-results.md`

4. Read [7-manual-review-checklist.md](7-manual-review-checklist.md)
5. Manually review each scenario
6. Mark as: PASS / NEEDS REFINEMENT / FAIL
7. Fix refinements
8. Save: `home-services-review-report.md`

**Time:** 2–3 hours

**Outcome:** 18–20 production-ready scenarios for Home Services ✅

---

### **Day 6: Repeat for Industry 2 (Retail)**

Run Stages 2–7 for Retail:
- Pattern extraction + tone modeling (1–1.5 hr)
- Logic blocks + scenario generation (3–4 hr)
- Testing + review (2–3 hr)

**Output:** 18–20 scenarios for Retail ✅

---

### **Day 7: Repeat for Industry 3 (Hospitality)**

Run Stages 2–7 for Hospitality:
- Pattern extraction + tone modeling (1–1.5 hr)
- Logic blocks + scenario generation (3–4 hr)
- Testing + review (2–3 hr)

**Output:** 18–20 scenarios for Hospitality ✅

---

## **END OF WEEK 1**

**You should have:**

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
    [same files]
  hospitality/
    [same files]

TOTAL: 54–60 production-ready scenario cards
```

---

## **QUALITY GATES**

Before moving to Week 2 (UI build), verify:

- [ ] Each industry has 18–20 PASSED scenarios
- [ ] All scenarios tested (3 runs each)
- [ ] All scenarios manually reviewed
- [ ] No hallucinations in any scenario
- [ ] Tone matches industry norms
- [ ] Logic blocks are accurate (not made up)
- [ ] Example outputs feel authentic
- [ ] 80%+ confidence in quality

**If pass rate is below 80%, spend 1–2 extra days refining before building UI.**

---

## **TOOLS YOU NEED**

### **Required:**
- Claude API access (or ChatGPT Plus for web interface)
- Text editor (VS Code, Sublime, or even Google Docs)
- ChatGPT account (for testing prompts)

### **Optional but helpful:**
- Outscraper or Apify (for review scraping)
- Pushshift API (for Reddit data)
- Firecrawl (for website scraping)

### **Can be done manually:**
- Reddit search via Google: `site:reddit.com/r/contractor "customer canceled"`
- Copy-paste from websites
- Manual testing (just paste into ChatGPT web)

---

## **COST ESTIMATE**

### **If using APIs:**
- Claude API (Stages 2–5): ~$5–10 per industry
- ChatGPT API (Stage 6): ~$2–3 per industry
- **Total for 3 industries:** $20–40

### **If using web interfaces:**
- ChatGPT Plus: $20/month
- Claude web: Free tier may suffice
- **Total:** $20

### **Optional tools:**
- Outscraper: ~$10 for review scraping
- **Total with tools:** $30–50

**Budget-friendly MVP cost:** $20–50 total for entire Week 1

---

## **EXECUTION TIPS**

### **1. Start with Home Services**
It's the easiest to research and has the clearest pain points.

### **2. Don't aim for perfection**
80% quality on Day 7 is better than 100% quality on Day 21.

### **3. Batch similar tasks**
Do all data collection at once, all pattern extraction at once, etc.

### **4. Trust the agent (but verify)**
Let Claude do heavy lifting, you catch the obvious issues.

### **5. If you get stuck for >30 min**
- Skip to next stage
- Come back later
- Or ask in a community (DM me if needed)

### **6. Keep the end goal in sight**
You're building 60 scenarios to validate the product, not to win awards.

---

## **COMMON PITFALLS**

### **Pitfall 1: Collecting too much data**
**Fix:** 50 examples is enough. Stop at 100 max.

### **Pitfall 2: Over-refining scenarios**
**Fix:** If it's 80% good, move on. You can improve post-launch.

### **Pitfall 3: Testing every edge case**
**Fix:** Test happy path only. Real users will find edge cases.

### **Pitfall 4: Trying to build 5 industries**
**Fix:** Stick to 3. You can add more after validation.

### **Pitfall 5: Writing scenarios manually instead of using agents**
**Fix:** Let Claude generate, you review. 10x faster.

---

## **DECISION TREE: WHEN TO USE AGENTS VS MANUAL**

### **Use Agent (Claude) for:**
- ✅ Pattern extraction (clustering 100 examples)
- ✅ Logic block extraction (synthesizing rules)
- ✅ Scenario generation (writing 20 cards)
- ✅ Tone modeling (extracting communication patterns)

### **Do Manually:**
- ✅ Data collection (or use simple scraping tools)
- ✅ Self-testing (paste into ChatGPT, evaluate)
- ✅ Final review (reality check, cringe check)

### **Hybrid (Agent + Human):**
- ✅ Refinements (agent generates, human approves)
- ✅ Edge case handling (agent suggests, human decides)

---

## **PROGRESS TRACKING**

Use this checklist:

```markdown
## WEEK 1 PROGRESS

### Industry 1: Home Services
- [x] Data collection
- [x] Pattern extraction
- [x] Logic blocks
- [x] Tone modeling
- [x] Scenario generation
- [x] Self-testing
- [x] Manual review
- [x] Final scenarios: 19 ready ✅

### Industry 2: Retail
- [x] Data collection
- [x] Pattern extraction
- [x] Logic blocks
- [x] Tone modeling
- [x] Scenario generation
- [x] Self-testing
- [x] Manual review
- [x] Final scenarios: 20 ready ✅

### Industry 3: Hospitality
- [x] Data collection
- [x] Pattern extraction
- [x] Logic blocks
- [x] Tone modeling
- [x] Scenario generation
- [x] Self-testing
- [x] Manual review
- [x] Final scenarios: 18 ready ✅

### TOTAL: 57 scenarios ready for production ✅
```

---

## **READY TO START?**

1. Read this guide fully
2. Pick Industry 1 (recommend: Home Services)
3. Open [1-data-collection-prompt.md](1-data-collection-prompt.md)
4. Start collecting data
5. Follow the 7-stage process
6. Track progress daily
7. Ship Week 1 with 54–60 scenarios

---

## **WEEK 2 PREVIEW**

Once Week 1 is done, you'll:
1. Convert scenarios to JSON format
2. Build static site (Next.js or Astro)
3. Create scenario card component
4. Set up daily rotation logic
5. Integrate Gumroad paywall
6. Deploy to Vercel

**But that's Week 2. Focus on Week 1 first.**

---

## **NEED HELP?**

If you get stuck:

1. **Re-read the specific stage prompt** (they're detailed)
2. **Check PRODUCT-OVERVIEW.md** for vision alignment
3. **Simplify:** Cut scope, reduce scenarios, pick easier industry
4. **Ask for feedback:** Post in communities, DM mentors
5. **Keep shipping:** Done is better than perfect

---

**Good luck. You've got this. Ship Week 1 by Day 7.**

---

**END OF MASTER EXECUTION GUIDE**
