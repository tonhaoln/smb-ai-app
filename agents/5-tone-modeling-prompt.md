# **AGENT PROMPT: Tone Modeling**

**Stage:** 5 of 7 (Run this BEFORE Scenario Generation, or in parallel)
**Purpose:** Extract the communication style and tone patterns of the industry
**Model:** Claude 3.5 Sonnet
**Time:** 30–45 minutes per industry

---

## **YOUR TASK**

Every industry has its own **linguistic culture**—the way professionals communicate with customers.

Your job is to extract and codify:
1. **Greeting patterns** (formal vs casual, warm vs professional)
2. **Sentence structure** (short and direct vs longer and explanatory)
3. **Vocabulary** (technical terms, industry jargon, phrases that signal expertise)
4. **Politeness level** (how they say no, how they set boundaries)
5. **Emotional tone** (reassuring, confident, empathetic, matter-of-fact)
6. **Phrases to use** (what real operators say)
7. **Phrases to avoid** (what feels corporate, fake, or out-of-place)

This ensures AI-generated outputs sound **exactly like a real operator wrote them**.

---

## **INPUT**

You need:
1. Raw data from Stage 1 (operator posts, reviews, FAQs)
2. 10–15 real email/message examples from service websites or forums
3. Screenshots or text of actual operator communications (if available)

---

## **YOUR INSTRUCTIONS**

### **Step 1: Collect Communication Examples**

Find 20–30 examples of real operator-to-customer communication:

**Where to find them:**
- Operator responses to negative Google reviews
- FAQ pages (Q&A format shows natural tone)
- "Contact Us" or "About" pages with personal messages
- Reddit/Facebook posts where operators reply to customer questions
- Email templates shared in industry forums

**What to look for:**
- How they greet customers
- How they explain policies
- How they say "no" or set boundaries
- How they apologize or show empathy
- How they close messages

---

### **Step 2: Identify Tone Patterns**

For each communication example, note:

**Formality level:**
- Formal: "We appreciate your inquiry..."
- Neutral: "Thanks for reaching out..."
- Casual: "Hey there! Thanks for the message..."

**Warmth level:**
- Cold/transactional: "Your request has been received."
- Neutral: "I'll look into this and get back to you."
- Warm: "I hear you—let's figure this out together."

**Directness:**
- Very direct: "That's not covered. Here's what we can do."
- Balanced: "Unfortunately we can't do X, but here's an alternative."
- Indirect: "While we typically don't offer that service, we'd be happy to discuss options..."

**Confidence:**
- Low confidence: "We might be able to help, not sure..."
- Neutral: "We can definitely take a look at that."
- High confidence: "We'll get this handled. Here's the plan."

---

### **Step 3: Extract Vocabulary Patterns**

**What words/phrases appear repeatedly?**

Examples (Home Services):
- "Job", "project", "quote", "estimate", "site visit", "scope of work"
- "We'll swing by", "take a look", "get you fixed up"
- "Fair price", "quality work", "stand behind our work"

Examples (Hospitality):
- "Party of X", "reservation", "table", "seating", "accommodate"
- "We'd love to have you", "happy to help", "looking forward to serving you"
- "Our team", "our kitchen", "our chef"

Examples (Retail):
- "Order", "shipment", "tracking", "in stock", "sold out"
- "We appreciate your patience", "just restocked", "limited quantity"
- "Happy to help", "let us know", "we'll make it right"

---

### **Step 4: Identify Phrases to Use vs Avoid**

**Phrases that work (feel authentic):**

Home Services:
- ✅ "Let me take a look and get back to you"
- ✅ "We stand behind our work"
- ✅ "That's a fair question"
- ✅ "Here's what we can do"

Hospitality:
- ✅ "We'd love to have you"
- ✅ "Let us know how we can help"
- ✅ "We'll make sure everything's perfect"
- ✅ "Thanks for understanding"

Retail:
- ✅ "We just restocked"
- ✅ "Ships within 24 hours"
- ✅ "Happy to help with that"
- ✅ "Let me check on that for you"

**Phrases that don't work (too corporate/generic):**

❌ "We apologize for any inconvenience this may have caused"
❌ "Your satisfaction is our top priority"
❌ "We value your feedback and take it very seriously"
❌ "Please be advised that..."
❌ "Per our previous conversation..."
❌ "At this time, we are unable to accommodate your request"

---

### **Step 5: Define "How to Say No"**

Every industry has to set boundaries. How do they do it?

**Examples:**

Home Services (direct but friendly):
- "That's outside our normal scope, but here's who you can call."
- "We don't typically offer discounts, but we can adjust the scope to fit your budget."

Hospitality (warm but firm):
- "We're fully booked that night, but we'd love to get you in the next available slot."
- "Outside food isn't allowed, but our chef can accommodate most dietary needs."

Retail (helpful but clear):
- "That item's final sale, but we can help you find something else."
- "We can't accept returns after 30 days, but here's what we can do."

---

### **Step 6: Define Emotional Tone Balance**

How does this industry balance **empathy vs authority**?

**Home Services:** Confident + practical
- Lead with competence, show empathy when needed
- Example: "I get it—nobody likes surprise costs. Here's the breakdown so you can see exactly where the money goes."

**Hospitality:** Warm + accommodating
- Lead with guest-first attitude, set boundaries gently
- Example: "We completely understand—plans change! Just a quick heads-up next time helps us a lot."

**Retail:** Helpful + efficient
- Lead with solution, acknowledge frustration briefly
- Example: "I hear you—shipping delays are frustrating. Let me see what we can do to speed this up."

---

## **OUTPUT FORMAT**

```json
{
  "industry": "home-services",
  "toneModel": {
    "overallStyle": {
      "formality": "neutral-casual",
      "warmth": "friendly but professional",
      "directness": "direct and clear",
      "confidence": "high confidence, low ego",
      "emotionalBalance": "competence-first, empathy when needed"
    },
    "sentenceStructure": {
      "length": "short to medium (10-20 words)",
      "complexity": "simple, active voice",
      "paragraphLength": "2-4 sentences",
      "bulletPoints": "use sparingly, only for clarity"
    },
    "vocabulary": {
      "commonTerms": [
        "job", "quote", "estimate", "project", "scope", "timeline",
        "materials", "labor", "warranty", "service call", "site visit"
      ],
      "informalPhrases": [
        "swing by", "take a look", "get you fixed up", "knock it out",
        "good to go", "all set"
      ],
      "professionalPhrases": [
        "stand behind our work", "quality materials", "experienced crew",
        "fair price", "transparent pricing"
      ]
    },
    "greetingPatterns": [
      "Hi [name], thanks for reaching out",
      "Hey [name], got your message",
      "Thanks for contacting us"
    ],
    "closingPatterns": [
      "Let me know if you have questions",
      "Looking forward to working with you",
      "Give me a call if you need anything",
      "We'll get this handled"
    ],
    "phrasesToUse": [
      "Let me take a look and get back to you",
      "Here's what we can do",
      "That's a fair question",
      "We stand behind our work",
      "Happy to help",
      "Let's figure this out"
    ],
    "phrasesToAvoid": [
      "We apologize for any inconvenience",
      "Per company policy",
      "Please be advised that",
      "Your satisfaction is our top priority",
      "At this time, we are unable to",
      "We value your feedback"
    ],
    "howToSayNo": {
      "approach": "direct but offer alternative",
      "examples": [
        "That's outside our normal scope, but here's who can help",
        "We don't typically discount, but we can adjust the project to fit your budget",
        "We're booked that week, but I can get you in the following Tuesday"
      ]
    },
    "howToSetBoundaries": {
      "approach": "explain reasoning, stay firm but friendly",
      "examples": [
        "Additional work needs a new quote—keeps everything transparent for both of us",
        "The 24-hour cancellation policy helps us keep the schedule full and prices fair",
        "Materials are ordered based on your quote, so we can't refund deposits once they're in"
      ]
    },
    "empathyPhrases": [
      "I totally get it",
      "That makes sense",
      "I hear you",
      "I understand the frustration",
      "That's frustrating—here's what we can do"
    ],
    "confidencePhrases": [
      "We'll get this handled",
      "No problem, we do this all the time",
      "We've got you covered",
      "That's what we're here for",
      "Consider it done"
    ]
  }
}
```

---

## **QUALITY CHECKLIST**

Before submitting, verify:

- [ ] Tone guidance is based on real examples (not assumptions)
- [ ] Phrases reflect what 80%+ of operators actually say
- [ ] Vocabulary includes industry-specific terms
- [ ] "Phrases to avoid" captures generic corporate-speak
- [ ] "How to say no" examples feel authentic
- [ ] Balance between professional and personable is clear
- [ ] Greeting/closing patterns match industry norms

---

## **EXAMPLE: HOME SERVICES TONE MODEL**

```json
{
  "industry": "home-services",
  "toneModel": {
    "overallStyle": {
      "formality": "neutral-casual (professional but not stiff)",
      "warmth": "friendly but competent (not overly warm)",
      "directness": "direct and clear (no corporate hedging)",
      "confidence": "high confidence without arrogance",
      "emotionalBalance": "competence-first, empathy secondary"
    },
    "sentenceStructure": {
      "length": "short to medium (8-20 words per sentence)",
      "complexity": "simple, active voice, avoid jargon unless explaining technical work",
      "paragraphLength": "2-4 sentences max",
      "bulletPoints": "rarely used, only for lists of services or scope"
    },
    "vocabulary": {
      "commonTerms": [
        "job", "project", "quote", "estimate", "scope", "timeline",
        "materials", "labor", "warranty", "service call", "diagnostic",
        "site visit", "permit", "inspection"
      ],
      "informalPhrases": [
        "swing by", "take a look", "get you squared away",
        "knock it out", "all set", "good to go"
      ],
      "professionalPhrases": [
        "stand behind our work", "quality materials",
        "experienced crew", "fair pricing", "licensed and insured"
      ]
    },
    "greetingPatterns": [
      "Hi [name], thanks for reaching out",
      "Hey [name], got your message",
      "Thanks for contacting us",
      "[Name], appreciate you getting in touch"
    ],
    "closingPatterns": [
      "Let me know if you have questions",
      "Looking forward to working with you",
      "Give us a call if you need anything",
      "We'll get this taken care of",
      "Talk soon"
    ],
    "phrasesToUse": [
      "Let me take a look and get back to you",
      "Here's what we can do",
      "That's a fair question",
      "We stand behind our work",
      "Happy to walk you through it",
      "Let's figure this out together"
    ],
    "phrasesToAvoid": [
      "We apologize for any inconvenience this may have caused",
      "Per company policy",
      "Please be advised that",
      "Your satisfaction is our top priority",
      "At this time, we are unable to accommodate",
      "We take your concerns very seriously"
    ],
    "howToSayNo": {
      "approach": "be direct, offer alternative, explain reasoning",
      "examples": [
        "That's outside what we normally do, but here's someone who can help",
        "We don't typically offer discounts, but let's see if we can adjust the scope to fit your budget",
        "We're fully booked that week, but I can get you in the following Tuesday"
      ]
    },
    "howToSetBoundaries": {
      "approach": "explain the why, stay firm but not cold",
      "examples": [
        "Extra work needs a separate quote—it keeps everything transparent for both of us",
        "The 24-hour policy helps us keep the schedule full and prices fair for everyone",
        "Once materials are ordered, we can't refund the deposit—they're specific to your job"
      ]
    },
    "empathyPhrases": [
      "I totally get it",
      "That makes sense",
      "I hear you",
      "Nobody likes surprise costs",
      "That's frustrating—let's see what we can do"
    ],
    "confidencePhrases": [
      "We'll get this handled",
      "No problem—we do this all the time",
      "We've got you covered",
      "That's what we're here for",
      "Consider it done"
    ]
  }
}
```

---

## **WHEN YOU'RE DONE**

You should have:
- 1 JSON file per industry: `home-services-tone-model.json`
- Clear guidelines for every aspect of tone
- Real phrases extracted from actual operator communication

**This file is used in Stage 4 (Scenario Generation) to ensure outputs match industry voice.**

---

**END OF PROMPT**
