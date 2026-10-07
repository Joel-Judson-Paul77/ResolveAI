# ResolveAI: Pitch Script (Round 4: Transform, 5-7 min)

**Theme:** "Take something from yesterday, rethink it today, build it for tomorrow."
**One-line pitch:** *Ticket in, resolution out. A human only when needed.*

Total time: ~6 minutes + Q&A. Speak slowly. One idea per slide.

---

## Slide 1: Title (15 sec)
**On slide:** ResolveAI | Autonomous AI Customer Support | Team name

**Say:**
"Good morning judges. We're [team]. Our problem statement is Customer Support, and our solution is ResolveAI: a support system that resolves tickets on its own and calls a human only when it truly needs one."

---

## Slide 2: Yesterday, the legacy problem (60 sec)
**On slide:**
- Customers wait hours in a phone or email queue
- Agents read and sort every ticket by hand
- Order lookups happen across several systems
- A simple "where is my order?" costs the same effort as a hard case
- Angry customers are spotted too late
- No support after office hours

**Say:**
"Think about the last time you contacted customer support. You waited, you repeated yourself, and the answer took a day. Behind the scenes, an agent reads every message, searches several systems, and types a reply. Most tickets are simple, such as order status or small refunds, yet they take the same effort as the hard ones. The result is slow replies, high cost, and unhappy customers."

---

## Slide 3: Today, our idea (45 sec)
**On slide:** "From a queue of tickets to a pipeline of resolutions"
Understand, Investigate, Decide, Resolve, Learn

**Say:**
"We rethought support as an automated pipeline. A message arrives, the AI understands it, checks real data, decides what to do, and acts. Easy cases are closed in seconds. Hard or emotional cases go to a human, who gets a summary and a suggested reply."

---

## Slide 4: Architecture (75 sec)
**On slide (diagram):**
```
Customer message (web / email / Telegram)
      -> Webhook (n8n)
      -> [1 UNDERSTAND]  AI: intent, urgency, sentiment
      -> [2 INVESTIGATE] Order and customer lookup
      -> [3 DECIDE]      Rules + AI confidence
            |- Simple  -> [4a RESOLVE]  auto-reply / refund within limit
            |- Complex -> [4b ESCALATE] human gets summary + draft reply
      -> [5 LEARN]       Log and dashboard
```

**Say (walk left to right, point at each box):**
"Step 1: n8n receives the message and the AI classifies the intent, urgency and mood. Step 2: the system looks up the order in our data store. Step 3: it decides, using business rules and the AI's confidence. Step 4: easy cases are answered or refunded automatically. Complex or angry cases are escalated with a ready summary. Step 5: every decision is logged, so we can measure and improve."

**Key rule, say it clearly:**
"The AI never invents facts. It answers only from data it looked up, and it can only act within limits we set, for example refunds under a fixed amount."

---

## Slide 5: Live demo (90 sec)
**On slide:** "3 tickets, 3 outcomes"

**Do and say:**
1. **Order status:** type "Where is my order #1023?"
   "The system finds the order and replies with the real status in seconds."
2. **Refund:** type "My item arrived damaged, I want a refund."
   "It checks the order and the amount, sees it is within the limit, approves the refund and confirms to the customer."
3. **Angry case:** type a long, angry, complex message.
   "This one is flagged as urgent. A human gets a summary and a suggested reply, so they start with the full picture."
4. Show the log: "Here is the time per ticket, how many were resolved automatically, and how many went to a human."

*Backup: if wifi fails, play the pre-recorded video and say "Here is a recording of the same flow."*

---

## Slide 6: Tomorrow, impact and growth (45 sec)
**On slide:**
- Replies in seconds instead of hours
- Roughly Rs.1 per AI-handled ticket vs Rs.30-100 for a human-handled one (estimate)
- 24/7 coverage
- Next: WhatsApp and email, Telugu and Hindi replies, FAQ knowledge base, auto follow-ups, weekly insight reports

**Say:**
"Our solution replies in seconds, runs around the clock, and costs a fraction of a manual ticket. Tomorrow we can add more channels, local languages, and a knowledge base without changing the core logic."

---

## Slide 7: Close (15 sec)
**Say:**
"Yesterday, support was a queue. Today, it's a pipeline. Tomorrow, it's autonomous. Thank you. We're happy to take your questions."

---

# Q&A Cheat Sheet (learn these)

**Is this feasible?**
n8n and AI APIs are production tools. Small businesses already run workflows like this. Our prototype uses the same building blocks.

**What does it cost?**
AI calls cost roughly Rs.0.2-1 per ticket (an estimate). A human-handled ticket costs far more. n8n can be self-hosted for free.

**What if the AI is wrong?**
Three safeguards: a confidence threshold, spending limits, and escalation. Anything risky or uncertain goes to a human. The AI only answers from looked-up data.

**What about internet outages or offline use?**
Messages are queued and retried. A fallback replies "we received your request" and routes it to a human. A self-hosted setup keeps working on the local network.

**What about privacy and security?**
We send only the fields needed, mask personal data, and keep API keys in n8n's credential store, never in code.

**How does it scale?**
Replace the sheet with a real database or CRM, and add channels without changing the logic. n8n handles queues and retries.

**How is this different from a normal chatbot?**
A chatbot only talks. ResolveAI investigates real data and takes actions such as refunds, with limits and human handoff.

**Why n8n?**
It is visual, so the architecture is the workflow. It connects to hundreds of services and speeds up building and changing the system.

**What would you build next?**
WhatsApp and email channels, Telugu and Hindi replies, a knowledge base for FAQs, and automatic follow-ups.

---

# Speaking Tips
- Practice the script 3 times out loud with a timer.
- Split roles: one person speaks and one drives the demo.
- Say the key rule ("the AI never invents facts") with confidence. It answers the biggest worry.
- Keep slides short. Look at the judges, not the screen.
- If you don't know an answer, say "Good question. Our current prototype does X, and in production we would do Y."
- Have the backup demo video ready and don't show API keys on screen.
