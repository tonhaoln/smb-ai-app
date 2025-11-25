# **AGENT PROMPT: Scenario Generation**

**Stage:** 4 of 7
**Purpose:** Generate complete scenario cards using canonical structure + logic blocks
**Model:** Claude 3.5 Sonnet
**Time:** 2–3 hours per industry (20 scenarios)

---

## **YOUR TASK**

You have:
1. 20 scenario patterns with scores
2. Logic blocks (business rules)
3. Raw data examples

Now generate **complete, production-ready scenario cards** using the canonical structure.

---

## **INPUT**

You need these 3 files:
1. `[industry]-scenarios.json` (from Stage 2)
2. `[industry]-logic-blocks.json` (from Stage 3)
3. `[industry]-tone-model.json` (from Stage 5 - run Stage 5 first, or use basic tone guidelines)

---

## **THE CANONICAL STRUCTURE (NON-NEGOTIABLE)**

Every scenario card must have these exact sections:

```
[Industry Badge]
Day X • 3–5 min • Works with ChatGPT

THE SITUATION:
[1-sentence trigger]

THE AI ACTION:
[Benefit-focused explanation of what the prompt does]

COPY & PASTE THIS:
[Complete prompt template with logic blocks embedded]

MAKE IT YOURS (optional):
1. [Specific customization note]
2. [Specific customization note]
3. [Specific customization note]

WHAT YOU'LL GET:
[2–3 sentence example output showing realistic result]

TIME SAVED:
~X min per [occurrence]
```

---

## **INSTRUCTIONS FOR EACH SECTION**

### **Section 1: Industry Badge + Metadata**

```
[Industry Badge: Home Services / Retail / Hospitality]
Day [1-20] • [Time estimate] • Works with ChatGPT
```

**Rules:**
- Day number corresponds to rotation order (highest totalScore = Day 1)
- Time estimate: "3–5 min" for most, "5–10 min" for complex ones
- Always mention "Works with ChatGPT" (or "Works with ChatGPT, Claude")

---

### **Section 2: THE SITUATION**

**Purpose:** 1-sentence trigger that makes operator think "yep, had this yesterday"

**Format:**
- Start with "A customer/client/guest [action]"
- Include key friction point
- 15–25 words max
- Active voice, present or recent past tense

**Examples:**

✅ **Good:**
- "A client calls asking for a 20% discount after receiving your quote, citing a lower competitor price."
- "A customer cancels their appointment just 3 hours before the scheduled time."
- "A guest leaves a negative review claiming your cancellation policy wasn't clearly stated."

❌ **Bad:**
- "Pricing issues" (too vague)
- "When a customer who has received a quote from your business decides to engage in price negotiation..." (too wordy)
- "You need to respond to discount requests" (not a situation, it's a task)

---

### **Section 3: THE AI ACTION**

**Purpose:** Explain the BENEFIT, not just what the prompt does

**Format:**
- 2–3 sentences
- Focus on outcome: "This prompt helps you..."
- Mention what it handles automatically
- Include emotional benefit when relevant

**Examples:**

✅ **Good:**
"This prompt helps you craft a response that holds your pricing with confidence while keeping the door open for the sale. It references your value, sets professional boundaries, and offers a path forward without devaluing your work. Perfect for maintaining profit margins while staying customer-friendly."

✅ **Good:**
"This prompt generates a cancellation response that acknowledges the inconvenience, references your policy clearly, and offers to reschedule—all while maintaining a professional tone. It saves you from writing under stress and ensures you enforce boundaries without burning bridges."

❌ **Bad:**
"This prompt creates a response to discount requests."

❌ **Bad:**
"Use this when customers want lower prices. It will help you say no."

---

### **Section 4: COPY & PASTE THIS**

**Purpose:** The actual prompt the user pastes into ChatGPT

**CRITICAL RULES:**
1. **Reference logic blocks** directly (don't make up policies)
2. **Include context placeholders** [in brackets] for user to customize
3. **Specify output format** ("Write a professional response that...")
4. **Embed tone rules** from tone model
5. **Keep it 4–8 sentences** (not too short, not a novel)
6. **Make it copy-paste ready** (no "Hey ChatGPT..." just direct instructions)

**Template Structure:**

```
You are helping a [industry] professional respond to [situation].

Context:
- [Key detail placeholder]
- [Key detail placeholder]
- [Relevant policy from logic blocks]

Write a professional [email/message/response] that:
1. [Specific instruction based on logic blocks]
2. [Specific instruction based on logic blocks]
3. [Specific instruction based on logic blocks]

Tone: [Tone guidance from tone model]

Length: [X] sentences, [Y] paragraphs.
```

**Example (Home Services - Discount Request):**

```
You are helping a contractor respond to a client who wants a discount after receiving a quote.

Context:
- The quoted price is [original quote amount]
- The client mentioned [competitor/reason for discount request]
- Your standard policy is that quotes are firm for 30 days, and discounts are not typically offered unless scope changes

Write a professional email response that:
1. Acknowledges their budget concern without being defensive
2. Briefly reinforces the value: quality materials, experienced crew, warranty coverage
3. Explains that your pricing is competitive and reflects true cost + fair profit
4. Offers an alternative: discuss scope adjustments to meet their budget, or flexible payment terms
5. Ends by reaffirming your interest in working with them

Tone: Confident but friendly. Direct without being cold. Professional but personable.

Length: 3-4 short paragraphs. Keep it concise and easy to read on mobile.
```

---

### **Section 5: MAKE IT YOURS**

**Purpose:** 2–3 specific, actionable customization notes

**Rules:**
- Max 3 bullets
- Each bullet is 1 sentence
- Focus on placeholders user needs to fill in
- Don't explain obvious things ("use your name")
- Don't over-explain ("you might want to adjust tone...")

**Examples:**

✅ **Good:**
1. "Replace '[original quote amount]' with your actual quote (e.g., '$4,500')."
2. "If you offer payment plans, mention that as an alternative to discounting."
3. "Adjust the warranty timeframe to match what you actually offer (30 days, 90 days, etc.)."

❌ **Bad:**
1. "Personalize this to match your brand voice and style."
2. "Make sure you fill in the customer's name."
3. "You can adjust the tone if you want it to sound more formal or casual."

**If you can't think of 3 specific customizations, use 2 or even 1. Quality over quantity.**

---

### **Section 6: WHAT YOU'LL GET**

**Purpose:** Show realistic example output so user knows what to expect

**Rules:**
- 2–3 sentences (or 2 short paragraphs for longer responses)
- Use realistic names, numbers, details
- Match the tone model exactly
- Show actual email/message format if relevant
- Make it feel like something a real operator would send

**Example (Home Services - Discount Request):**

```
"Hi Sarah, thanks for getting back to me. I understand budget is a consideration—it is for all of us. The $4,500 quote reflects quality materials, a 2-year warranty, and 15 years of experience, so I'm not able to discount without changing the scope. That said, I'm happy to discuss adjusting the project scope to fit your budget, or we can set up a payment plan. Let me know what works best, and we'll figure it out."
```

**Example (Hospitality - No-Show Reservation):**

```
"Hi there, we had a reservation for your party of 6 last night at 7:30pm but didn't see you. We completely understand that plans change—we just ask for a quick heads-up when possible so we can offer the table to other guests. If you'd like to reschedule, we'd love to have you. Just give us a call or reply here. Thanks for understanding."
```

---

### **Section 7: TIME SAVED**

**Purpose:** Concrete metric of value

**Rules:**
- Be realistic (don't exaggerate)
- Format: "~X min per [occurrence]"
- Consider: time to write from scratch, emotional labor, back-and-forth
- Range: 2–10 minutes for most scenarios

**Examples:**
- "~3 min per request"
- "~5 min per cancellation"
- "~7 min per negotiation"
- "~4 min per complaint response"

---

## **COMPLETE EXAMPLE OUTPUT**

```markdown
# Scenario: Client Wants Discount After Receiving Quote

---

**Industry:** Home Services
**Day 1** • 3–5 min • Works with ChatGPT

---

## THE SITUATION:

A client calls or emails asking for a 20% discount after receiving your quote, often citing a lower competitor price or budget constraints.

---

## THE AI ACTION:

This prompt helps you craft a response that holds your pricing with confidence while keeping the door open for the sale. It references your value, sets professional boundaries, and offers alternatives without devaluing your work. Perfect for maintaining profit margins while staying customer-friendly.

---

## COPY & PASTE THIS:

```
You are helping a contractor respond to a client who wants a discount after receiving a quote.

Context:
- The quoted price is [original quote amount]
- The client mentioned [competitor price/reason for discount request]
- Your standard policy is that quotes are firm for 30 days, and discounts are not typically offered unless scope changes

Write a professional email response that:
1. Acknowledges their budget concern without being defensive
2. Briefly reinforces the value: quality materials, experienced crew, warranty coverage
3. Explains that your pricing is competitive and reflects true cost + fair profit
4. Offers an alternative: discuss scope adjustments to meet their budget, or flexible payment terms if available
5. Ends by reaffirming your interest in working with them

Tone: Confident but friendly. Direct without being cold. Professional but personable.

Length: 3-4 short paragraphs. Keep it concise and easy to read on mobile.
```

---

## MAKE IT YOURS:

1. Replace '[original quote amount]' with your actual quote (e.g., '$4,500').
2. If you don't offer payment plans, remove that option and focus on scope adjustments.
3. Adjust the warranty timeframe to match what you actually offer (1 year, 2 years, etc.).

---

## WHAT YOU'LL GET:

"Hi Sarah, thanks for getting back to me. I understand budget is a consideration—it is for all of us. The $4,500 quote reflects quality materials, a 2-year warranty, and 15 years of experience, so I'm not able to discount without changing the scope. That said, I'm happy to discuss adjusting the project details to fit your budget, or we can set up a payment plan if that helps. Let me know what works best, and we'll make it happen."

---

## TIME SAVED:

~5 min per price negotiation
```

---

## **OUTPUT FORMAT**

Generate all 20 scenarios in markdown format, one file per industry:

`home-services-scenarios-complete.md`

Each scenario separated by:
```
---
---
```

---

## **QUALITY CHECKLIST**

Before submitting, verify each scenario:

- [ ] Follows canonical structure exactly
- [ ] THE SITUATION is 1 sentence, specific, recognizable
- [ ] THE AI ACTION explains benefits, not just mechanics
- [ ] COPY & PASTE prompt references logic blocks (no made-up policies)
- [ ] COPY & PASTE prompt specifies output format
- [ ] COPY & PASTE prompt includes tone guidance
- [ ] MAKE IT YOURS has 1–3 specific, actionable points
- [ ] WHAT YOU'LL GET feels realistic and industry-accurate
- [ ] TIME SAVED is realistic
- [ ] Tone matches industry standards
- [ ] No typos, no placeholder text left in

---

## **GENERATION ORDER**

Generate scenarios in order of **totalScore** (highest first):

1. Day 1 = highest totalScore
2. Day 2 = second highest
3. ...
4. Day 20 = 20th highest

This ensures the most important scenarios rotate first.

---

## **WHEN YOU'RE DONE**

You should have:
- 1 markdown file per industry: `home-services-scenarios-complete.md`
- 20 complete scenario cards
- Each following canonical structure exactly

**Next stage:** Self-Testing (Agent Prompt 6)

---

**END OF PROMPT**
