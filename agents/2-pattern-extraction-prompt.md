# **AGENT PROMPT: Pattern Extraction**

**Stage:** 2 of 7
**Purpose:** Cluster raw data into 20 recurring high-friction scenarios per industry
**Model:** Claude 3.5 Sonnet (required for clustering logic)
**Time:** 30–60 minutes per industry

---

## **YOUR TASK**

You have collected 50–100 raw examples of operational pain points for **[INDUSTRY NAME]**.

Your job is to:
1. **Cluster** these examples into recurring scenario types
2. **Identify** the 20 most frequent, high-impact scenarios
3. **Score** each scenario by importance, frequency, and pain level

---

## **INPUT**

Paste the raw data file from Stage 1:
```
[Paste contents of home-services-raw-data.txt or equivalent]
```

---

## **YOUR INSTRUCTIONS**

### **Step 1: Identify Recurring Patterns**

Read through all examples. Look for situations that appear multiple times with slight variations.

**Example:**
- "Customer wants 20% off after seeing quote"
- "Client asked for discount because neighbor paid less"
- "How do I handle price negotiation after estimate?"

→ These cluster into: **"Client wants discount after receiving quote"**

### **Step 2: Create Scenario List**

Extract exactly **20 scenarios** that:
- Appear at least 3–5 times in the data
- Cause real friction (time, stress, money, or reputation loss)
- Are specific enough to be actionable
- Are general enough to apply to 80%+ of operators

**Bad scenario (too vague):** "Handle difficult customer"
**Good scenario:** "Customer demands refund after service is complete"

**Bad scenario (too narrow):** "Client wants discount on Tuesday afternoon for HVAC repair under $500"
**Good scenario:** "Client wants discount after receiving quote"

### **Step 3: Write Scenario Titles**

Each title should be **8–12 words**, starting with:
- "Customer [action]"
- "Client [action]"
- "Guest [action]"

**Examples:**
- "Customer cancels appointment less than 24 hours before scheduled time"
- "Client wants additional work included for free after accepting quote"
- "Guest leaves negative review due to misunderstanding about policy"
- "Customer objects to travel fee or service call charge"

### **Step 4: Score Each Scenario**

For each scenario, assign scores (1–10):

**Importance:** How much does this impact the business?
- 10 = Major revenue/reputation impact
- 5 = Moderate impact
- 1 = Minor annoyance

**Frequency:** How often does this happen?
- 10 = Weekly or more
- 5 = Monthly
- 1 = Rarely

**Pain Score:** How stressful/difficult is this to handle?
- 10 = High emotional/financial stress
- 5 = Moderate discomfort
- 1 = Easy to handle

---

## **OUTPUT FORMAT**

Return exactly 20 scenarios in this format:

```json
{
  "industry": "home-services",
  "scenarios": [
    {
      "id": "discount-after-quote",
      "title": "Client wants discount after receiving your quote",
      "description": "A customer or client asks for a lower price after you've provided an estimate, often citing competitor pricing or budget constraints.",
      "importance": 9,
      "frequency": 8,
      "painScore": 7,
      "totalScore": 24,
      "relatedExamples": [
        "Had a client call asking for 20% off because neighbor got better price",
        "Customer says my quote is too high and wants me to match competitor",
        "How do I handle discount requests without devaluing my work?"
      ]
    },
    {
      "id": "cancellation-last-minute",
      "title": "Customer cancels appointment less than 24 hours before scheduled time",
      "description": "A scheduled appointment is canceled with little notice, leaving you with lost time, travel costs, or an empty slot.",
      "importance": 8,
      "frequency": 9,
      "painScore": 8,
      "totalScore": 25,
      "relatedExamples": [
        "Client texted 2 hours before saying they don't need service anymore",
        "Customer no-showed, didn't answer phone, lost half a day",
        "How do I enforce cancellation policy without losing future business?"
      ]
    }
  ]
}
```

---

## **QUALITY CHECKLIST**

Before submitting your 20 scenarios, verify:

- [ ] Each scenario appears at least 3 times in the raw data
- [ ] Titles are 8–12 words and action-oriented
- [ ] No duplicate scenarios (check for overlap)
- [ ] Scores reflect reality (not all 10s)
- [ ] Total coverage: these 20 scenarios represent ~80% of operator pain
- [ ] Each scenario is specific enough to be useful
- [ ] Each scenario is general enough to apply broadly

---

## **EXAMPLE CLUSTERING PROCESS**

**Raw examples:**
1. "Customer canceled morning of the appointment"
2. "Client called night before to reschedule"
3. "No-show, didn't answer phone"
4. "Canceled 3 hours before, now I have empty slot"

**Pattern identified:** Last-minute cancellations (within 24 hours)

**Scenario title:** "Customer cancels appointment less than 24 hours before scheduled time"

**Scores:**
- Importance: 8 (lost revenue, wasted prep time)
- Frequency: 9 (happens weekly for most operators)
- Pain: 8 (frustrating, hard to fill slot)
- Total: 25

---

## **COMMON SCENARIO CATEGORIES** (Use as inspiration, not a template)

### **For Home Services:**
- Price objections / discount requests
- Last-minute cancellations / no-shows
- Scope creep / extra work requests
- Travel fee objections
- Timeline disputes
- Post-service complaints
- Payment delays
- Emergency vs routine pricing confusion
- Weather-related rescheduling
- Access/entry issues

### **For Retail:**
- Return/refund outside policy window
- Price matching requests
- Stockout/backorder frustration
- Shipping delay complaints
- Product damage claims
- Bulk/wholesale discount requests
- Gift card/coupon disputes
- Sizing/fit issues
- Order modification after checkout
- Negative review over shipping time

### **For Hospitality:**
- Reservation no-shows (especially large parties)
- Last-minute party size changes
- Dietary restriction miscommunication
- Noise/behavior complaints
- Split check requests
- Menu substitution demands
- Wait time frustration
- Special occasion expectation mismatch
- Pricing confusion (service charge, gratuity)
- Review threats during dispute

---

## **WHEN YOU'RE DONE**

You should have:
- 1 JSON file per industry: `home-services-scenarios.json`
- Exactly 20 scenarios per industry
- Each with clear scores and examples

**Next stage:** Logic Block Extraction (Agent Prompt 3)

---

**END OF PROMPT**
