# **AGENT PROMPT: Data Collection**

**Stage:** 1 of 7
**Purpose:** Extract high-signal examples of real SMB pain points from public sources
**Model:** Claude 3.5 Sonnet (or manual collection)
**Time:** 2–3 hours per industry

---

## **YOUR TASK**

You are building an Industry OS for **[INDUSTRY NAME]**. Your job is to identify and extract real-world operational pain points that small business owners in this industry face repeatedly.

You will collect examples from **public sources only**:
- Public Reddit threads
- Public Facebook group posts
- Public Google reviews
- Public FAQs from service websites
- Public pricing pages
- Public policy pages

---

## **WHAT TO LOOK FOR**

Extract examples where operators or customers mention:

1. **Cancellations & no-shows**
   - "Customer canceled last minute"
   - "Guest didn't show up for reservation"

2. **Price objections & negotiation**
   - "Client wants a discount"
   - "Customer says price is too high"

3. **Scope creep & boundary issues**
   - "Client keeps asking for extras"
   - "They want more work for free"

4. **Refund requests & disputes**
   - "Customer wants money back"
   - "How do I handle refund requests?"

5. **Difficult customer communication**
   - "How do I respond to angry reviews?"
   - "Customer won't answer my messages"

6. **Scheduling & logistics problems**
   - "Client wants to reschedule again"
   - "How do I handle timeline changes?"

7. **Policy enforcement**
   - "Customer broke house rules"
   - "How do I enforce my cancellation policy?"

8. **Upselling & cross-selling moments**
   - "When should I offer premium service?"
   - "How do I suggest add-ons?"

---

## **OUTPUT FORMAT**

For each example you find, extract:

```
SOURCE: [URL or "Reddit r/contractor" or "Google Reviews"]
RAW QUOTE: [Exact text from source]
SCENARIO TYPE: [e.g., "price objection", "last-minute cancellation"]
EMOTIONAL TONE: [frustrated, anxious, confused, angry]
INDUSTRY CONTEXT: [Any specific details: "HVAC quote", "Saturday dinner reservation"]
```

---

## **COLLECTION TARGETS**

**Minimum per industry:** 50 examples
**Ideal per industry:** 100 examples
**Quality over quantity:** High-signal examples that show real pain

---

## **WHERE TO SEARCH**

### **Reddit:**
- r/smallbusiness
- r/entrepreneur
- Industry-specific subreddits:
  - Home Services: r/contractor, r/Plumbing, r/HVAC
  - Retail: r/smallretail, r/ecommerce
  - Hospitality: r/restaurateur, r/hospitality

**Search terms:**
- "customer canceled"
- "price objection"
- "wants discount"
- "refund request"
- "difficult customer"
- "scope creep"
- "no show"

### **Facebook Groups:**
Use Google search:
```
site:facebook.com "[industry]" "customer canceled"
site:facebook.com "plumber" "price too high"
site:facebook.com "restaurant" "no show reservation"
```

### **Google Reviews:**
Search for top businesses in the industry, read negative and neutral reviews (not just 5-star).

Look for patterns in customer complaints and operator responses.

### **Service Websites:**
- Visit 10–15 top-ranked businesses
- Copy their FAQ sections
- Copy pricing pages
- Copy cancellation policies
- Copy terms of service

---

## **EXAMPLE OUTPUT**

```
SOURCE: Reddit r/contractor
RAW QUOTE: "Had a client call me this morning asking for a 20% discount because 'their neighbor got a better price.' How do I handle this without losing the job?"
SCENARIO TYPE: Price objection after quote
EMOTIONAL TONE: Frustrated, worried about losing sale
INDUSTRY CONTEXT: Contracting, post-quote negotiation

---

SOURCE: Google Reviews - Joe's Plumbing
RAW QUOTE: "They wanted to charge me $150 just to show up! I canceled and went with someone else."
SCENARIO TYPE: Travel fee objection
EMOTIONAL TONE: Angry, surprised by fee
INDUSTRY CONTEXT: Plumbing service, call-out fee dispute

---

SOURCE: Facebook "Restaurant Owners Group"
RAW QUOTE: "Party of 8 didn't show up on Saturday night. No call, no show. That's 2 hours of lost revenue. Do I need a deposit policy?"
SCENARIO TYPE: No-show reservation
EMOTIONAL TONE: Frustrated, financial loss
INDUSTRY CONTEXT: Restaurant, peak time, large party
```

---

## **MANUAL COLLECTION PROCESS** (If not using agent)

1. Open a Google Doc or text file
2. Copy the OUTPUT FORMAT above
3. Search Reddit/FB/Google for each industry
4. Copy-paste 50–100 examples
5. Save as `[industry]-raw-data.txt`

**Time per industry:** 1–2 hours of focused collection

---

## **WHEN YOU'RE DONE**

You should have:
- 1 file per industry: `home-services-raw-data.txt`, `retail-raw-data.txt`, `hospitality-raw-data.txt`
- 50–100 examples per file
- Clear patterns starting to emerge

**Next stage:** Pattern Extraction (Agent Prompt 2)

---

## **QUICK START COMMANDS**

### **For Home Services:**
```
Search Reddit: "site:reddit.com/r/contractor customer discount"
Search Reddit: "site:reddit.com/r/Plumbing no show"
Search FB: "site:facebook.com plumber price objection"
Google: "plumber near me" → visit top 10 → copy FAQs
```

### **For Retail:**
```
Search Reddit: "site:reddit.com/r/ecommerce refund request"
Search Reddit: "site:reddit.com/r/smallretail difficult customer"
Google: "boutique store policies" → copy 10 examples
```

### **For Hospitality:**
```
Search Reddit: "site:reddit.com/r/restaurateur cancellation"
Search Reddit: "site:reddit.com/r/hospitality no show"
Google: "restaurant cancellation policy" → copy 10 examples
```

---

**END OF PROMPT**
