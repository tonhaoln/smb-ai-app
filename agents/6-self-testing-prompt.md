# **AGENT PROMPT: Self-Testing & Validation**

**Stage:** 6 of 7
**Purpose:** Test each scenario prompt to ensure stable, accurate, trustworthy output
**Model:** GPT-4 or Claude 3.5 Sonnet (run the scenarios through the LLM you're testing)
**Time:** 1–2 hours per industry (20 scenarios × 3 test runs each)

---

## **YOUR TASK**

You have 20 complete scenario cards per industry.

Now you must **test each prompt** to verify:
1. **No hallucinations** (no made-up facts, policies, or details)
2. **Output stability** (3 runs produce similar quality/structure)
3. **Tone match** (output matches industry tone model)
4. **Structure compliance** (output follows expected format)
5. **Usefulness** (output is actually copy-paste ready)

**This is your quality gate.** Only scenarios that pass all tests go live.

---

## **TESTING SETUP**

### **What You Need:**
1. All 20 scenario prompts from Stage 4
2. The tone model from Stage 5
3. The logic blocks from Stage 3
4. Access to ChatGPT (GPT-4) or Claude API

### **How to Test:**
You'll run each scenario's "COPY & PASTE THIS" prompt through the LLM **3 times** and evaluate the outputs.

---

## **THE 5 TEST CRITERIA**

### **Test 1: No Hallucinations**

**Check:** Does the output invent facts, policies, or details not provided in the prompt?

**Examples of hallucinations:**
- ❌ "Our standard 90-day warranty" (if prompt didn't specify 90 days)
- ❌ "As per our conversation on Tuesday" (no conversation mentioned)
- ❌ "Your order #12345" (no order number provided)
- ❌ "Our team of certified technicians" (prompt didn't mention certification)

**Pass criteria:**
- Output only references information from the prompt placeholders
- No specific numbers/dates/names unless in brackets as [placeholders]
- No policies mentioned unless explicitly in the logic blocks

---

### **Test 2: Output Stability**

**Check:** Do 3 different runs produce outputs of similar quality, tone, and structure?

**What to compare:**
- Length (should be within 20% of each other)
- Tone (all 3 should feel professional/friendly/etc. consistently)
- Structure (all 3 should follow similar paragraph/sentence patterns)
- Key points covered (all 3 should hit the main points from the prompt)

**Pass criteria:**
- You'd be comfortable sending any of the 3 outputs to a real customer
- No run produces significantly worse quality than others
- Tone doesn't swing wildly (from cold to overly casual, etc.)

**Example of PASS:**

Run 1:
"Hi Sarah, thanks for reaching out. I understand budget is tight. The $4,500 reflects quality materials and a 2-year warranty, so I can't discount without changing scope. Happy to discuss adjusting the project to fit your budget. Let me know."

Run 2:
"Hey Sarah, appreciate you getting back to me. I hear you on the budget concern. The quote at $4,500 covers top-grade materials and includes our 2-year warranty, so discounting isn't an option without adjusting what we're doing. That said, I'm happy to talk through scope changes to meet your number. Just let me know."

Run 3:
"Hi Sarah, thanks for the message. Budget concerns are totally fair. The $4,500 accounts for quality materials and warranty coverage, so I can't go lower without changing the scope. But I'd be glad to explore adjustments that fit your budget better. Let's chat."

→ **All 3 are usable, similar quality, consistent tone.**

**Example of FAIL:**

Run 1: [Same as above]

Run 2:
"Dear Ms. Johnson, I acknowledge receipt of your inquiry regarding pricing adjustments. Please be advised that our quotation reflects current market rates and includes premium materials. We are unable to accommodate discount requests at this time. However, we welcome the opportunity to discuss alternative service options that may align with your budgetary parameters."

Run 3:
"yo sarah, totally get it—money's tight for everyone lol. cant really do discounts but maybe we can cut some stuff out to make it work? hmu"

→ **Run 2 is too formal, Run 3 is too casual. FAIL.**

---

### **Test 3: Tone Match**

**Check:** Does the output match the tone model from Stage 5?

**Compare against:**
- Formality level (casual/neutral/formal)
- Warmth level (cold/neutral/warm)
- Vocabulary (uses phrases to use, avoids phrases to avoid)
- Sentence structure (short/medium/long)
- Confidence level

**Pass criteria:**
- Output feels like it came from a real operator in this industry
- Uses vocabulary from tone model
- Avoids corporate jargon from "phrases to avoid"
- Matches formality/warmth balance

---

### **Test 4: Structure Compliance**

**Check:** Does the output follow the format specified in the prompt?

**What to check:**
- If prompt said "3-4 paragraphs", output should be 3-4 paragraphs (not 1 long block or 7 short ones)
- If prompt said "bullet points for 3 options", output should have bullets
- If prompt said "professional email", output should have greeting + body + closing
- If prompt said "150 words max", output should respect that

**Pass criteria:**
- Output follows structural instructions from prompt
- Length is appropriate (not too short/too long)
- Format is usable (properly formatted email, message, etc.)

---

### **Test 5: Usefulness**

**Check:** Could you actually copy-paste this into an email/message and send it?

**Ask yourself:**
- Does this sound like a real human wrote it?
- Would a customer respond positively (or at least neutrally)?
- Is it clear what the next step is?
- Does it solve the friction in the scenario?
- Would you need to heavily edit this, or is it ready to go?

**Pass criteria:**
- 80%+ ready to send as-is
- Only minor tweaks needed (name, specific number, etc.)
- Feels authentic and helpful
- Doesn't create new problems

---

## **TESTING PROCESS**

For each of the 20 scenarios:

### **Step 1: Copy the "COPY & PASTE THIS" prompt**

### **Step 2: Fill in example placeholders**

Replace [brackets] with realistic example data:
- `[original quote amount]` → `$4,500`
- `[client name]` → `Sarah`
- `[competitor price]` → `$3,800`
- `[cancellation time]` → `3 hours before`

### **Step 3: Run through ChatGPT 3 times**

Paste the prompt into ChatGPT (or Claude), get output.
Clear the chat or start a new one.
Paste again, get second output.
Repeat for third output.

### **Step 4: Evaluate against 5 criteria**

Use this scorecard:

```
SCENARIO: [scenario title]

RUN 1:
✅ / ❌ No hallucinations
✅ / ❌ Tone match
✅ / ❌ Structure compliance
✅ / ❌ Usefulness

RUN 2:
✅ / ❌ No hallucinations
✅ / ❌ Tone match
✅ / ❌ Structure compliance
✅ / ❌ Usefulness

RUN 3:
✅ / ❌ No hallucinations
✅ / ❌ Tone match
✅ / ❌ Structure compliance
✅ / ❌ Usefulness

OUTPUT STABILITY:
✅ / ❌ All 3 runs similar quality

OVERALL:
✅ PASS / ❌ FAIL

NOTES:
[Any issues, patterns, or observations]
```

---

## **PASS/FAIL THRESHOLDS**

**PASS:**
- All 3 runs pass "No hallucinations"
- At least 2/3 runs pass tone match
- At least 2/3 runs pass structure compliance
- At least 2/3 runs pass usefulness
- Output stability: all 3 are usable quality

**FAIL (requires regeneration):**
- Any run has hallucinations → FAIL
- Fewer than 2/3 runs pass tone match → FAIL
- Output quality varies wildly between runs → FAIL
- None of the 3 outputs feel usable → FAIL

---

## **IF A SCENARIO FAILS**

### **Option 1: Refine the prompt**

**Common fixes:**
- Add more specific tone guidance
- Add more constraints ("Do NOT mention...", "Keep under 4 sentences")
- Add output structure example
- Reference more logic blocks
- Simplify instructions

### **Option 2: Regenerate the scenario**

Go back to Stage 4 and rewrite from scratch.

### **Option 3: Remove the scenario**

If it consistently fails after 2–3 refinement attempts, cut it and replace with a different scenario from your pattern list.

---

## **OUTPUT FORMAT**

Create a testing report for each industry:

`home-services-test-results.md`

```markdown
# Testing Results: Home Services

**Date:** [date]
**Tester:** [your name or "Agent"]
**Model tested:** GPT-4 / Claude 3.5

---

## SCENARIO 1: Client Wants Discount After Quote

**Status:** ✅ PASS

**Test Runs:**
- Run 1: ✅ All criteria passed
- Run 2: ✅ All criteria passed
- Run 3: ✅ All criteria passed

**Output Stability:** ✅ Consistent quality across all 3 runs

**Notes:** Tone is spot-on. Outputs are direct, friendly, professional. No hallucinations. Ready for production.

---

## SCENARIO 2: Last-Minute Cancellation

**Status:** ❌ FAIL

**Test Runs:**
- Run 1: ✅ Passed, but mentioned "our standard 48-hour policy" (we said 24-hour in prompt)
- Run 2: ❌ Too cold/corporate tone
- Run 3: ✅ Passed

**Output Stability:** ❌ Run 2 significantly different tone

**Issues:**
- Hallucination in Run 1 (wrong timeframe)
- Tone inconsistency
- Need to add explicit constraint: "Mention 24-hour policy, not 48"

**Action:** Refine prompt and retest.

---

[Repeat for all 20 scenarios]

---

## SUMMARY

**Total Scenarios:** 20
**Passed:** 17
**Failed:** 3
**Pass Rate:** 85%

**Failed Scenarios:**
1. Last-Minute Cancellation (tone inconsistency)
2. Travel Fee Objection (hallucinations)
3. Scope Creep Request (too generic)

**Next Steps:**
- Refine and retest failed scenarios
- Final manual review of all passed scenarios
```

---

## **QUALITY CHECKLIST**

Before moving to Stage 7 (manual review), ensure:

- [ ] All 20 scenarios tested (3 runs each)
- [ ] Each scenario has pass/fail status
- [ ] Failed scenarios identified with clear issues
- [ ] Pass rate is 80%+ (16+ out of 20)
- [ ] No hallucinations in any passed scenario
- [ ] Tone consistency verified across runs
- [ ] Test report documented

---

## **AUTOMATION OPTION** (For Advanced Users)

If you want to automate this:

**Simple script structure:**
1. Load all 20 scenario prompts
2. For each prompt:
   - Fill in example placeholders
   - Send to ChatGPT API 3 times
   - Collect 3 outputs
   - Run basic checks:
     - Length check (within 20% of each other)
     - Keyword check (avoid phrases to avoid)
     - Placeholder check (no [brackets] left in output)
3. Flag scenarios that fail checks for manual review

**But for MVP: Manual testing is fine. 60 total runs (20 scenarios × 3 runs) takes 1–2 hours per industry.**

---

## **WHEN YOU'RE DONE**

You should have:
- 1 test report per industry: `home-services-test-results.md`
- 80%+ pass rate
- Clear documentation of issues
- Confidence that passed scenarios produce reliable outputs

**Next stage:** Manual Review (Stage 7)

---

**END OF PROMPT**
