# 🤖 AI Prospecting Agent (n8n + OpenAI + Google Sheets)

A configurable B2B prospecting agent that researches target companies, identifies their most likely pain point by industry, and drafts a personalized first outreach message, ready for a human to review and send.

Built by **Daniela Zuluaga**, B2B sales professional, to speed up account research and personalize outreach at scale.

---

## The problem
Good outbound starts with research: understanding what each company does, which pain point matters to them, and how to open the conversation. Done by hand, this takes minutes per account and doesn't scale.

## The solution
An agent that, for every company in a list:
1. **Summarizes** what the company does.
2. **Identifies** its most likely pain point, based on its industry and my product's value proposition.
3. **Drafts** a short, personalized LinkedIn message in the right language and tone.

Every message is reviewed by a human before it's sent.

## How it works

![Workflow](workflow.png)

| Step | Node | What it does |
|---|---|---|
| 1 | Manual Trigger | Starts the agent |
| 2 | Config (Google Sheets) | Reads what I sell: product, value proposition, ideal customer, pain points by industry, language, tone |
| 3 | Prospects (Google Sheets) | Reads the list of target companies |
| 4 | AI (OpenAI) | Analyzes each company and returns a summary, pain point and message as JSON |
| 5 | Write results (Google Sheets) | Writes the results back into each company's row |

## ✨ Switch niches in seconds
The agent separates **what I sell** (Config tab) from **who I sell to** (Prospects tab). To prospect for a different product, industry or language, I only edit one row in the Config sheet. No changes to the workflow.

**Current use case:** in-pipe hydroelectric power generation for construction companies, food & beverage plants and coliving operators in Colombia. The agent matches each prospect to the right pain point: blackout risk and rising energy prices for food & beverage, a differentiated value proposition for construction, and protected margins for colivings that include utilities in the rent.

## Sample output

![Results](results.png)

## Tech stack
- **n8n**: workflow automation
- **OpenAI**: language model
- **Google Sheets**: input, configuration and output

## How to use it
1. Import `Agente_de_Prospeccion_B2B.json` into n8n.
2. Create a Google Sheet with two tabs: `Config` and `Prospectos`.
3. Connect your Google Sheets and OpenAI credentials.
4. Fill in your Config row and your prospect list.
5. Click **Execute**.

## Next steps
- Enrich prospects automatically with web research
- Lead scoring and prioritization
- Push qualified leads and drafted messages into HubSpot
