# **AGENT PROMPT: Logic Block Extraction**

**Stage:** 3 of 7
**Purpose:** Extract reusable business rules and facts that make scenarios accurate
**Model:** Claude 3.5 Sonnet
**Time:** 45–90 minutes per industry

---

## **YOUR TASK**

You have 20 scenario patterns for **[INDUSTRY NAME]**.

Now you need to extract the **business logic** that makes responses accurate, realistic, and trustworthy.

These are the **reusable facts and rules** that operators actually follow in this industry.

---

## **WHAT ARE LOGIC BLOCKS?**

Logic blocks are structured pieces of knowledge that ensure your prompts produce **industry-accurate** outputs.

**Example:**

❌ **Without logic blocks:** "Respond politely to the cancellation"
✅ **With logic blocks:** "Acknowledge cancellation. Reference 24-hour policy. Offer to reschedule within 48 hours. Waive fee if first-time client and weather-related."

Logic blocks prevent hallucinations and generic outputs.

---

## **INPUT**

1. The raw data file from Stage 1
2. The 20 scenarios from Stage 2
3. Additional research:
   - 10–15 service websites from this industry
   - Their FAQ pages
   - Their pricing pages
   - Their cancellation/refund policies
   - Their terms of service

---

## **YOUR INSTRUCTIONS**

### **Step 1: Extract Pricing Rules**

What are the common pricing patterns in this industry?

**Examples:**
- "Service call fee: $75–150, typically waived if work is performed"
- "Travel charges apply beyond 15–20 mile radius"
- "Emergency rates (after-hours): 1.5x–2x normal rate"
- "Deposit required for jobs over $500"
- "Material markup: typically 20–30% above cost"

**Output format:**
```json
{
  "category": "pricing",
  "rules": [
    "Service call fee ranges from $75-$150, typically waived if customer proceeds with work",
    "Travel fees apply for distances over 15-20 miles from base location",
    "After-hours/emergency pricing is typically 1.5x-2x standard rates"
  ]
}
```

---

### **Step 2: Extract Cancellation & Scheduling Rules**

What are standard policies around cancellations, no-shows, and rescheduling?

**Examples:**
- "24-48 hour cancellation notice required"
- "Cancellation fee: 50% for <24hr notice, 100% for no-shows"
- "Weather exceptions: fee waived for severe weather"
- "First-time clients: often given one-time courtesy waiver"
- "Rescheduling preferred over refunds"

**Output format:**
```json
{
  "category": "cancellation",
  "rules": [
    "Standard cancellation notice: 24-48 hours",
    "Cancellation fees: 50% within 24hr, 100% for no-shows",
    "Weather-related cancellations: typically fee waived",
    "First-time customers: often given one courtesy waiver",
    "Rescheduling within 1 week: generally no fee"
  ]
}
```

---

### **Step 3: Extract Scope & Service Boundaries**

What's typically included vs. excluded in services?

**Examples (Home Services):**
- "Standard cleaning: surfaces, floors, bathrooms, kitchen"
- "NOT included unless specified: windows, inside oven, inside fridge, garage"
- "Deep clean adds: baseboards, inside appliances, window tracks"
- "Inspection includes X, Y, Z but does not include repair"

**Examples (Hospitality):**
- "Reservation includes table for stated duration (90–120 min)"
- "Special requests accommodated when possible, not guaranteed"
- "Outside food/drink prohibited"
- "Gratuity: 18-20% for parties of 6+"

**Output format:**
```json
{
  "category": "scope",
  "rules": [
    "Standard service includes: [specific list]",
    "Excluded unless specifically requested: [specific list]",
    "Common add-ons: [specific list with typical pricing]",
    "Timeline: typical job takes X hours/days"
  ]
}
```

---

### **Step 4: Extract Refund & Dispute Rules**

How do operators handle refunds, complaints, and disputes?

**Examples:**
- "Refunds: full refund if service not started, partial if in-progress, none if completed"
- "Satisfaction guarantee: will re-do work if issue identified within 7 days"
- "Material costs non-refundable"
- "Deposits: non-refundable unless canceled by operator"
- "Complaints: addressed within 24-48 hours"

**Output format:**
```json
{
  "category": "refunds",
  "rules": [
    "Full refund if service not yet started",
    "Partial refund if work in progress, evaluated case-by-case",
    "No refund after service completion, but will address issues",
    "Material costs are non-refundable",
    "Satisfaction guarantee: re-service within 7 days if issue"
  ]
}
```

---

### **Step 5: Extract Communication & Boundary Standards**

How do professionals communicate? What's the standard tone and approach?

**Examples:**
- "Always acknowledge customer's concern first"
- "Explain policy clearly without being defensive"
- "Offer alternatives when saying no (reschedule vs refund)"
- "Set expectations upfront: timeline, cost, what's included"
- "Follow up within 24 hours of inquiry"

**Output format:**
```json
{
  "category": "communication",
  "rules": [
    "Acknowledge customer concern before explaining policy",
    "Offer alternative solution when declining request",
    "Set clear expectations: timeline, cost, inclusions",
    "Respond within 24 hours to inquiries",
    "Maintain professional but friendly tone"
  ]
}
```

---

### **Step 6: Extract Common Objections & Responses**

What do customers commonly object to, and how do pros respond?

**Examples:**
- "Price objection: Explain value, materials quality, expertise, warranty"
- "Timeline objection: Set realistic expectations, explain factors (weather, permits, supply chain)"
- "Deposit objection: Explain it secures materials/time, standard practice"
- "Travel fee objection: Explain costs (fuel, time, vehicle wear)"

**Output format:**
```json
{
  "category": "objections",
  "rules": [
    "Price objection response: emphasize quality, warranty, expertise, long-term value",
    "Timeline concerns: set realistic expectations, explain variables",
    "Deposit resistance: explain it's standard, secures slot and materials",
    "Travel fee pushback: explain actual costs, fair compensation for time/distance"
  ]
}
```

---

## **COMPLETE OUTPUT FORMAT**

```json
{
  "industry": "home-services",
  "logicBlocks": [
    {
      "category": "pricing",
      "rules": [...]
    },
    {
      "category": "cancellation",
      "rules": [...]
    },
    {
      "category": "scope",
      "rules": [...]
    },
    {
      "category": "refunds",
      "rules": [...]
    },
    {
      "category": "communication",
      "rules": [...]
    },
    {
      "category": "objections",
      "rules": [...]
    },
    {
      "category": "custom",
      "rules": [
        "Industry-specific rule 1",
        "Industry-specific rule 2"
      ]
    }
  ]
}
```

---

## **QUALITY CHECKLIST**

Before submitting logic blocks, verify:

- [ ] Rules are based on real industry standards (not made up)
- [ ] Each rule is specific enough to be actionable
- [ ] Rules reflect what 80%+ of operators actually do
- [ ] No contradictory rules within same category
- [ ] Rules reference actual numbers/ranges when relevant ($, %, hours, miles)
- [ ] Communication rules match industry tone (formal vs casual, direct vs warm)
- [ ] 25–40 total rules across all categories

---

## **RESEARCH SOURCES**

To extract accurate logic blocks:

1. **Visit 10–15 service websites** in this industry
   - Read their "Services" pages
   - Read their FAQ sections
   - Copy pricing structures
   - Copy cancellation policies

2. **Read operator forums**
   - See what operators say about industry standards
   - Note common practices they mention

3. **Analyze the raw data** from Stage 1
   - Look for repeated rules mentioned by multiple operators
   - Note what operators say they "always do" or "never do"

4. **Google: "[industry] standard pricing structure"**
5. **Google: "[industry] cancellation policy template"**
6. **Google: "[industry] service agreement template"**

---

## **EXAMPLE: HOME SERVICES LOGIC BLOCKS**

```json
{
  "industry": "home-services",
  "logicBlocks": [
    {
      "category": "pricing",
      "rules": [
        "Service call/diagnostic fee: $75-$150, typically waived if customer proceeds with repair",
        "Travel charges: $25-$75 for distance over 15-20 miles from service area",
        "After-hours rates: 1.5x-2x normal rate (evenings, weekends, holidays)",
        "Deposit for larger jobs: 25-50% upfront for jobs over $500",
        "Material markup: 15-30% over cost to cover procurement, handling, warranty"
      ]
    },
    {
      "category": "cancellation",
      "rules": [
        "Cancellation notice requirement: 24-48 hours",
        "Cancellation fee: 50% of quoted price if canceled within 24hr, 100% for no-show",
        "Weather exceptions: severe weather cancellations typically fee-waived",
        "First-time customer courtesy: one-time waiver often extended",
        "Rescheduling within same week: often no fee if adequate notice given"
      ]
    },
    {
      "category": "scope",
      "rules": [
        "Standard service includes: specific scope defined in estimate",
        "Additional work discovered on-site: requires new quote/approval before proceeding",
        "Permits and inspections: customer responsibility unless otherwise agreed",
        "Prep work: customer typically responsible for clearing work area",
        "Warranty: 30-90 days on labor, 1 year+ on parts (manufacturer warranty)"
      ]
    },
    {
      "category": "refunds",
      "rules": [
        "Full refund: only if service not yet started or operator cancels",
        "Partial refund: rare, evaluated case-by-case if work incomplete",
        "Completed work: no refund, but will address legitimate issues",
        "Deposits: non-refundable once materials ordered or slot reserved",
        "Redo guarantee: will return to address issues within 7-30 days at no charge"
      ]
    },
    {
      "category": "communication",
      "rules": [
        "Acknowledge customer concern first before explaining policy",
        "Offer alternative solutions when declining a request (reschedule vs refund)",
        "Set clear expectations upfront: timeline, what's included, final cost",
        "Respond to inquiries within 24 hours, preferably same day",
        "Professional but personable tone: confident, helpful, not defensive"
      ]
    },
    {
      "category": "objections",
      "rules": [
        "Price objection: emphasize quality, expertise, warranty, materials, long-term value",
        "Timeline pushback: explain variables (weather, supply chain, permits, inspection)",
        "Deposit resistance: explain it's industry standard, secures materials and schedule",
        "Travel fee objection: explain real costs (fuel, vehicle wear, travel time = work time)",
        "Scope creep requests: politely explain additional work requires new quote, protects both parties"
      ]
    }
  ]
}
```

---

## **WHEN YOU'RE DONE**

You should have:
- 1 JSON file per industry: `home-services-logic-blocks.json`
- 25–40 total rules across 6–7 categories
- Rules that are specific, actionable, and industry-accurate

**Next stage:** Scenario Generation (Agent Prompt 4)

---

**END OF PROMPT**
