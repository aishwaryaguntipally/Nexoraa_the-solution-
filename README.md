# Nexoraa_the-solution-
AI-powered editorial memory agent that remembers published content, performance insights, and brand guidelines to generate smarter, non-repetitive content recommendations.
# Editorial Brain

### A content strategy agent that remembers what your team has published, what worked, what failed, and why.

## The Problem

Content teams often start every planning cycle from scratch. Their publishing history is scattered across spreadsheets, analytics dashboards, documents, and team members' memories.

Generic AI writing tools make this harder because they don't remember a company's previous content, audience, feedback, or performance.

As a result, teams may repeat the same topics, reuse underperforming formats, and lose their brand voice over time.

## What Editorial Brain Does

**Editorial Brain gives AI a memory of your entire content journey.**

* **Remembers every post** — topic, format, publishing date, and 30-day performance.
* **Learns from post-mortems** — remembers not only what happened, but why a post succeeded or failed.
* **Remembers editorial feedback** — feedback such as "too salesy" influences future recommendations.
* **Identifies content gaps** — discovers topics the team has not explored yet.
* **Recalls before answering** — every recommendation is grounded in the team's actual history instead of generic AI knowledge.

## How It Works

The system is divided into four main components:

**`generate_data.py`**
Creates a synthetic dataset of 40 previous posts with intentional patterns. For example, teardown and case-study formats perform better than listicles and definitions, while onboarding content generates more signups.

**`ingest.py`**
Stores posts, editorial feedback, performance insights, and content gaps as natural-language memories in a Hindsight memory bank.

**`agent.py`**
Retrieves relevant memories for each user request and uses an LLM through Groq to generate recommendations based on the team's history. It also includes retry handling for malformed responses.

**`app.py`**
Provides a Streamlit interface where users can ask for content recommendations, view the memories recalled by the agent, add editorial feedback, and record post-mortems.

## Setup

```bash
pip install -r requirements.txt

cp .env.example .env
```

Add your Hindsight and Groq API keys to `.env`.

Create a memory bank named:

```text
editorial-brain
```

Then run:

```bash
python generate_data.py
python ingest.py

python agent.py "Give me three blog topics for next month"

streamlit run app.py
```

## Demonstrating the Memory

The most important part of Editorial Brain is seeing how its recommendations change as it learns.

### Before Ingest

The agent gives generic content ideas that could apply to almost any company.

### After Ingest

The agent recalls the team's actual publishing history and recommends ideas based on specific previous posts, formats, and performance.

### After Feedback & Post-Mortem

The recommendations become even more personalized because the agent remembers the team's editorial preferences and lessons from previous successes and failures.

**The result: AI that doesn't just generate content — it learns from the content you've already created.**

## Built With

* **Hindsight** — Persistent agent memory
* **Groq** — Fast LLM inference using `openai/gpt-oss-120b`
* **Streamlit** — Interactive web interface
* **Python** — Data generation, memory ingestion, and agent logic

## Why It Matters

Editorial Brain turns scattered content history into **usable institutional memory**.

Instead of asking:

> *"What should we write next?"*

teams can ask:

> *"Based on everything we've learned, what should we write next?"*

That's the difference between a generic AI writer and an AI content strategist that actually **remembers**.
