# **AGENT PROMPTS FOR INDUSTRY OS GENERATION**

This folder contains all the prompts you need to generate 60 production-ready scenario cards for your MVP.

---

## **START HERE**

### **If you're new:**
1. Read [../docs/PRODUCT-OVERVIEW.md](../docs/PRODUCT-OVERVIEW.md) first
2. Then read [0-MASTER-EXECUTION-GUIDE.md](0-MASTER-EXECUTION-GUIDE.md)
3. Then start with Stage 1

### **If you're mid-build:**
- Use [QUICK-REFERENCE.md](QUICK-REFERENCE.md) to remember structures
- Jump to the stage you're on
- Check your progress against the timeline

### **If you're stuck:**
- Re-read the specific stage prompt
- Check the QUICK-REFERENCE for pass/fail criteria
- Simplify (reduce scope, easier industry, fewer scenarios)

---

## **THE 7 STAGE PROMPTS**

Execute in this order:

| Stage | File | Purpose | Time |
|-------|------|---------|------|
| 1 | [1-data-collection-prompt.md](1-data-collection-prompt.md) | Collect raw examples | 2–3 hr |
| 2 | [2-pattern-extraction-prompt.md](2-pattern-extraction-prompt.md) | Extract 20 scenarios | 30–60 min |
| 3 | [3-logic-block-extraction-prompt.md](3-logic-block-extraction-prompt.md) | Extract business rules | 45–90 min |
| 4 | [4-scenario-generation-prompt.md](4-scenario-generation-prompt.md) | Generate 20 complete cards | 2–3 hr |
| 5 | [5-tone-modeling-prompt.md](5-tone-modeling-prompt.md) | Extract communication style | 30–45 min |
| 6 | [6-self-testing-prompt.md](6-self-testing-prompt.md) | Test prompts (3 runs each) | 1–2 hr |
| 7 | [7-manual-review-checklist.md](7-manual-review-checklist.md) | Human quality check | 30–60 min |

**Note:** Run Stage 5 (Tone Modeling) BEFORE or in parallel with Stage 4 (Scenario Generation).

---

## **SUPPORT DOCUMENTS**

- [0-MASTER-EXECUTION-GUIDE.md](0-MASTER-EXECUTION-GUIDE.md) – Day-by-day timeline for Week 1
- [QUICK-REFERENCE.md](QUICK-REFERENCE.md) – Cheat sheet for structures and criteria
- [../docs/PRODUCT-OVERVIEW.md](../docs/PRODUCT-OVERVIEW.md) – Product vision and scope

---

## **WORKFLOW OVERVIEW**

```
┌─────────────────────┐
│  1. DATA COLLECTION │
│  (manual/scraping)  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────────┐
│  2. PATTERN EXTRACTION  │
│  (Claude identifies     │
│   20 scenarios)         │
└──────────┬──────────────┘
           │
           ├──────────────────┐
           ▼                  ▼
┌────────────────────┐  ┌──────────────┐
│ 3. LOGIC BLOCKS    │  │ 5. TONE MODEL│
│ (business rules)   │  │ (comm style) │
└─────────┬──────────┘  └──────┬───────┘
          │                    │
          └────────┬───────────┘
                   ▼
        ┌──────────────────────┐
        │ 4. SCENARIO GEN      │
        │ (20 complete cards)  │
        └──────────┬───────────┘
                   │
                   ▼
        ┌──────────────────────┐
        │ 6. SELF-TESTING      │
        │ (3 runs × 20 cards)  │
        └──────────┬───────────┘
                   │
                   ▼
        ┌──────────────────────┐
        │ 7. MANUAL REVIEW     │
        │ (human QA)           │
        └──────────┬───────────┘
                   │
                   ▼
          ✅ 18–20 READY SCENARIOS
```

---

## **EXPECTED OUTPUTS**

After running all 7 stages for 3 industries, you'll have:

```
/data/
  home-services/
    raw-data.txt                    ← Stage 1
    scenarios.json                  ← Stage 2
    logic-blocks.json               ← Stage 3
    scenarios-complete.md           ← Stage 4
    tone-model.json                 ← Stage 5
    test-results.md                 ← Stage 6
    review-report.md                ← Stage 7

  retail/
    [same files]

  hospitality/
    [same files]
```

**Grand total:** 54–60 production-ready scenario cards

---

## **WHICH MODEL TO USE**

### **For OS Generation (Stages 1–5):**
**Recommended:** Claude 3.5 Sonnet
- Best at clustering patterns
- Best at extracting structured knowledge
- Best at following complex instructions

**Alternative:** GPT-4 (works but less reliable for clustering)

### **For Testing (Stage 6):**
**Recommended:** GPT-4 or ChatGPT Plus
- This is what users will actually use
- Tests real-world output quality

### **For Review (Stage 7):**
**Human only** (no model)

---

## **COST BREAKDOWN**

### **Using APIs:**
- Claude API (Stages 2–5): ~$5–10 per industry
- GPT-4 API (Stage 6): ~$2–3 per industry
- **Total for 3 industries:** $20–40

### **Using Web Interfaces:**
- Claude web: Free tier (may hit limits, upgrade to Pro $20/mo)
- ChatGPT Plus: $20/month
- **Total:** $20–40/month

### **Scraping Tools (Optional):**
- Outscraper: $10 one-time
- **Total with tools:** $30–50

**Budget-friendly total: $20–50 for entire Week 1**

---

## **QUALITY BENCHMARKS**

### **By End of Each Stage:**

**Stage 2 (Pattern Extraction):**
- 20 scenarios identified per industry
- Each appears 3+ times in raw data
- Scores assigned (importance, frequency, pain)

**Stage 3 (Logic Blocks):**
- 25–40 rules extracted
- Rules based on real industry data (not made up)
- Covers pricing, cancellation, scope, refunds, communication

**Stage 4 (Scenario Generation):**
- 20 complete scenario cards
- All follow canonical structure exactly
- All reference logic blocks (no hallucinations)

**Stage 5 (Tone Modeling):**
- Tone model covers formality, warmth, vocabulary, phrases
- Based on real operator communication
- Clear "use/avoid" lists

**Stage 6 (Self-Testing):**
- 80%+ scenarios pass all tests (16+ out of 20)
- No hallucinations in any passed scenario
- Output stable across 3 runs

**Stage 7 (Manual Review):**
- 18–20 scenarios score ✅ PASS
- All feel authentic and useful
- Confidence to ship

---

## **COMMON QUESTIONS**

### **Q: Can I skip a stage?**
**A:** No. Each stage depends on the previous ones. Skipping = lower quality.

### **Q: Can I do stages out of order?**
**A:** Only Stage 5 (Tone Modeling) can run before Stage 4. Everything else must be sequential.

### **Q: What if I only have 2 days?**
**A:** Reduce scope:
- 2 industries instead of 3
- 15 scenarios instead of 20
- 2 test runs instead of 3

### **Q: Can I automate this?**
**A:** Partially. Stages 2–6 can be scripted. Stage 1 and 7 require human judgment for MVP.

### **Q: What if scenarios fail testing?**
**A:** Refine prompt (add constraints, reference tone model) and retest. If fails 3x, replace with different scenario.

### **Q: Do I need coding skills?**
**A:** No. Copy-paste prompts into Claude/ChatGPT web interfaces. Save outputs as text/JSON files.

---

## **TROUBLESHOOTING**

### **Issue: Claude refuses to scrape data**
**Solution:** Don't ask Claude to scrape. Collect manually via Google search or use tools like Outscraper.

### **Issue: Outputs feel generic**
**Solution:**
1. Add more specific logic blocks
2. Tighten tone model with more examples
3. Add explicit "be specific" instructions to Stage 4 prompt

### **Issue: Scenarios fail testing (hallucinations)**
**Solution:**
1. Check logic blocks are comprehensive
2. Add explicit constraint: "Only use information from context, do not invent policies"
3. Reduce prompt complexity

### **Issue: Running out of time**
**Solution:**
1. Reduce to 2 industries (Home Services + Hospitality)
2. Reduce to 15 scenarios per industry
3. Skip optional operator validation

### **Issue: Agent output varies wildly in quality**
**Solution:**
1. Add more structure constraints to prompts
2. Provide example output in prompt
3. Use temperature=0 for API calls

---

## **WEEK 1 TIMELINE RECAP**

- **Day 1–2:** Data collection (all 3 industries)
- **Day 3:** Pattern extraction + Tone modeling (Industry 1)
- **Day 4:** Logic blocks + Scenario generation (Industry 1)
- **Day 5:** Testing + Review (Industry 1) ✅
- **Day 6:** Repeat for Industry 2 ✅
- **Day 7:** Repeat for Industry 3 ✅

**End state:** 54–60 scenarios ready for UI build (Week 2)

---

## **NEXT STEPS AFTER WEEK 1**

Once you have 54–60 scenarios:

1. Convert to JSON format for site
2. Build static site (Next.js/Astro)
3. Create scenario card component
4. Set up rotation logic
5. Integrate Gumroad paywall
6. Deploy to Vercel
7. Launch 🚀

**But first: Complete Week 1. One step at a time.**

---

## **REMINDER**

This is your moat. The Industry OS is what makes your product different from every other prompt library.

Quality here = trust later = revenue.

Spend the time to get this right.

**Now go build.**

---

**END OF README**
