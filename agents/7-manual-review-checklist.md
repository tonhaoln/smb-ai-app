# **MANUAL REVIEW CHECKLIST**

**Stage:** 7 of 7 (Final Quality Gate)
**Purpose:** Human verification that scenarios are production-ready
**Time:** 30–60 minutes per industry

---

## **YOUR TASK**

Agent testing (Stage 6) verified technical quality.

Now **you** (the human) verify:
1. **Reality check** – Does this match real operator life?
2. **Cringe check** – Is anything fake, corporate, or off-putting?
3. **Trust check** – Would I send this output to a real customer?
4. **Usefulness check** – Does this actually solve the friction?

**This is your last chance to catch issues before launch.**

---

## **REVIEW PROCESS**

For each of the 20 scenarios in an industry:

### **Step 1: Read the complete scenario card**

Don't skim. Read every section:
- THE SITUATION
- THE AI ACTION
- COPY & PASTE THIS
- MAKE IT YOURS
- WHAT YOU'LL GET
- TIME SAVED

### **Step 2: Ask yourself 4 questions**

#### **Question 1: Reality Check**

**"Would a real operator in this industry say 'Yes, I deal with this'?"**

- [ ] The situation is specific and recognizable
- [ ] The friction point is real (not manufactured)
- [ ] The frequency makes sense (not too rare, not every day)
- [ ] The scenario title accurately describes the situation

**Red flags:**
- Too vague ("handle difficult customer")
- Too narrow ("client cancels Tuesday morning HVAC appointments under $500")
- Feels invented (no one actually deals with this)

---

#### **Question 2: Cringe Check**

**"Is there anything corporate, fake, or off-putting?"**

Read "THE AI ACTION" section:
- [ ] No marketing fluff ("game-changing solution", "unlock potential")
- [ ] No over-promising ("never lose a sale again")
- [ ] No condescension ("this easy trick will help you")
- [ ] Language feels natural, not salesy

Read "COPY & PASTE THIS" prompt:
- [ ] Instructions are clear, not overwritten
- [ ] Tone guidance feels authentic to industry
- [ ] No phrases from the "avoid" list in tone model
- [ ] Prompt doesn't sound like a corporate training manual

Read "WHAT YOU'LL GET" example output:
- [ ] Sounds like a real human wrote it
- [ ] Not overly polished or robotic
- [ ] Not too casual or unprofessional
- [ ] Matches industry tone model

**Red flags:**
- "We apologize for any inconvenience"
- "Your satisfaction is our top priority"
- "Per company policy"
- Emoji overload
- Overuse of exclamation marks

---

#### **Question 3: Trust Check**

**"Would I actually send this output to a customer?"**

Copy the "COPY & PASTE THIS" prompt.
Paste it into ChatGPT with example placeholders filled in.
Read the output.

Ask:
- [ ] Would I send this without heavy editing?
- [ ] Does this accurately represent the business?
- [ ] Is the tone appropriate?
- [ ] Does it solve the problem without creating new ones?
- [ ] Would a customer respond positively (or at least neutrally)?

**Red flags:**
- Output feels generic (could apply to any industry)
- Output is too long (walls of text)
- Output doesn't address the core friction
- Output sounds defensive or cold
- Output creates confusion about next steps

---

#### **Question 4: Usefulness Check**

**"Does this actually solve the friction in under 5 minutes?"**

Imagine you're the operator dealing with this scenario right now.

- [ ] I can copy-paste this prompt immediately
- [ ] I know what placeholders to fill in
- [ ] The output is genuinely helpful
- [ ] This saves me time vs writing from scratch
- [ ] This reduces emotional labor (no staring at blank screen)
- [ ] The "MAKE IT YOURS" section is actually useful

**Red flags:**
- Too many customization points (overwhelming)
- Unclear what to fill in for placeholders
- Output requires heavy editing to be usable
- Easier to just write it myself
- Doesn't actually address the stress of the situation

---

## **SCORING SYSTEM**

For each scenario, use this simple score:

### **✅ PASS (Ready for Production)**
- All 4 questions answered positively
- No major red flags
- Minor tweaks acceptable (typos, placeholder examples)

### **⚠️ NEEDS REFINEMENT**
- 3/4 questions answered positively
- 1–2 minor red flags
- Fixable with small edits

### **❌ FAIL (Regenerate or Remove)**
- 2 or fewer questions answered positively
- Multiple red flags
- Fundamental issues with scenario, tone, or usefulness

---

## **REFINEMENT ACTIONS**

### **If Scenario Scores ⚠️ NEEDS REFINEMENT:**

**Issue: Situation too vague**
→ Make it more specific ("client" → "client who just received quote")

**Issue: Tone too corporate**
→ Rewrite "AI ACTION" and "WHAT YOU'LL GET" sections using tone model

**Issue: Prompt too complex**
→ Simplify instructions, reduce to 3–5 key points

**Issue: "MAKE IT YOURS" too generic**
→ Replace with specific placeholders or cut to 1–2 bullets

**Issue: Time saved unrealistic**
→ Adjust to more conservative estimate

---

### **If Scenario Scores ❌ FAIL:**

**Option 1: Regenerate**
- Go back to Stage 4 (Scenario Generation)
- Use stricter prompt with more tone guidance
- Reference tone model explicitly

**Option 2: Replace**
- Remove this scenario
- Pick next highest-scored scenario from pattern list (Stage 2)
- Generate new card

**Option 3: Cut entirely**
- If you already have 18–19 strong scenarios
- Don't force a weak one into production
- Better to launch with 18 great scenarios than 20 mediocre ones

---

## **REVIEW TEMPLATE**

Use this template for each scenario:

```markdown
## SCENARIO: [Title]

### Reality Check:
✅ / ❌ Situation feels real and specific
✅ / ❌ Friction point is genuine
✅ / ❌ Frequency makes sense

### Cringe Check:
✅ / ❌ No corporate jargon
✅ / ❌ Prompt feels natural
✅ / ❌ Example output sounds human

### Trust Check:
✅ / ❌ I'd send this output to a customer
✅ / ❌ Tone is appropriate
✅ / ❌ Solves problem without creating new ones

### Usefulness Check:
✅ / ❌ Copy-paste ready
✅ / ❌ Clear placeholders
✅ / ❌ Saves real time and emotional labor

### SCORE: ✅ PASS / ⚠️ NEEDS REFINEMENT / ❌ FAIL

### NOTES:
[Issues, suggested fixes, observations]

---
```

---

## **COMPLETE REVIEW REPORT FORMAT**

```markdown
# Manual Review Report: Home Services

**Date:** [date]
**Reviewer:** [your name]
**Scenarios Reviewed:** 20

---

## SUMMARY

**✅ Ready for Production:** 17
**⚠️ Needs Refinement:** 2
**❌ Failed:** 1

**Pass Rate:** 85%

---

## DETAILED RESULTS

### ✅ PASSED (17 scenarios)

1. Client Wants Discount After Quote
2. Last-Minute Cancellation
3. Scope Creep Request
[... list all passed scenarios]

---

### ⚠️ NEEDS REFINEMENT (2 scenarios)

#### Scenario: Travel Fee Objection

**Issues:**
- Tone in example output slightly too defensive
- "MAKE IT YOURS" section has 4 bullets (should be 3 max)

**Fixes:**
- Rewrite example output to be more confident, less apologetic
- Combine last 2 bullets into one

**Estimated time to fix:** 5 minutes

---

#### Scenario: Weather Delay Communication

**Issues:**
- Situation could be more specific (what kind of weather?)
- Time saved seems high (listed as ~10 min, probably ~5 min)

**Fixes:**
- Add weather example to situation: "due to heavy rain/snow"
- Adjust time saved to ~5 min

**Estimated time to fix:** 3 minutes

---

### ❌ FAILED (1 scenario)

#### Scenario: Upselling Premium Service

**Issues:**
- Situation feels manufactured (operators don't talk about "upselling")
- Prompt is too sales-focused, sounds corporate
- Example output is too pushy
- Doesn't match tone model (too aggressive)

**Action:** REMOVE and replace with "Post-Service Follow-Up Message" from backup scenario list

---

## FINAL CHECKLIST

- [ ] All scenarios reviewed
- [ ] Refinement actions documented
- [ ] Failed scenarios removed or replaced
- [ ] Final count: 18–20 production-ready scenarios

---

## READY FOR LAUNCH?

✅ YES – 18+ scenarios passed, ready to deploy
❌ NO – Need to fix refinements first

**Next Step:**
- Implement refinements (30 min)
- Final review of changes
- Export to production format (JSON/Markdown)
- Deploy to site
```

---

## **REALITY CHECK: OPERATOR VALIDATION** (Optional but Powerful)

If you have time, validate 3–5 scenarios with real operators:

### **How to do it:**

1. **Pick 3–5 highest-priority scenarios** (top totalScore)
2. **Create a simple Google Doc** with:
   - Scenario situation
   - Example output
   - 3 questions:
     - "Do you deal with this situation?"
     - "Would you send this message to a customer?"
     - "Any changes you'd make?"
3. **Share with 2–3 real operators** via:
   - Reddit DM (find operators in industry subreddits)
   - Facebook group post
   - LinkedIn outreach
4. **Incorporate feedback** into final scenarios

**Time investment:** 1–2 hours (setup + outreach + review feedback)

**ROI:** Massive. Real validation before launch = higher conversion later.

---

## **COMMON ISSUES & FIXES**

### **Issue: Too many scenarios feel generic**

**Cause:** Not enough logic blocks referenced, or tone model too vague

**Fix:**
- Go back to Stage 3, add more specific rules
- Go back to Stage 5, tighten tone model
- Regenerate scenarios with explicit "be specific" instruction

---

### **Issue: Outputs vary too much in quality**

**Cause:** Prompts don't constrain output enough

**Fix:**
- Add more structure constraints to prompts
- Specify exact paragraph count, sentence length
- Add example structure in prompt

---

### **Issue: Scenarios solve wrong problems**

**Cause:** Pattern extraction (Stage 2) missed actual pain points

**Fix:**
- Go back to raw data, look for higher-signal examples
- Re-cluster with focus on "what costs time/money/stress"
- Replace weak scenarios with new patterns

---

## **FINAL APPROVAL**

Once all scenarios score ✅ PASS or refinements complete:

- [ ] 18–20 scenarios ready for production
- [ ] All scenarios match tone model
- [ ] All prompts reference logic blocks accurately
- [ ] All example outputs feel authentic
- [ ] No corporate jargon or cringe
- [ ] Each scenario solves real friction
- [ ] Confident these will make operators say "holy shit, this is real"

---

## **WHEN YOU'RE DONE**

You should have:
- 1 review report per industry: `home-services-review-report.md`
- 18–20 approved scenarios per industry
- Clear confidence in quality
- Ready to build the UI (Week 2)

**Total time for all 7 stages:** ~6–10 hours per industry (3 industries = 18–30 hours for Week 1)

---

**END OF MANUAL REVIEW CHECKLIST**
