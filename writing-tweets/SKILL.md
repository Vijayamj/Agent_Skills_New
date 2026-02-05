---
name: writing-tweets
description: Performs deep research on a topic to generate short, concise, clickbaity, and CTA-friendly tweets for x.com. Triggered when the user wants to post a tweet or research a topic for social media.
---
# Writing Tweets

This skill enables the agent to draft high-engagement tweets by researching current trends and applying viral copywriting frameworks.

## When to use this skill
- User says "Help me write a tweet about [Topic]".
- User says "Research [Topic] and write a thread/tweet".
- User wants "clickbaity" or "viral" content for X/Twitter.

## Workflow
1. [ ] **Topic Discovery**: Ask for the topic if not provided. Ask for the target audience if necessary.
2. [ ] **Deep Research**: 
    - Use `search_web` to find latest statistics, news, and common pain points related to the topic.
    - Search for what's currently trending or controversial about the topic on X/Twitter.
3. [ ] **Angle Selection**: Identify 3 angles (e.g., educational, controversial, listicle).
4. [ ] **Drafting**: Create 3 tweet options.
    - Each must be < 280 characters.
    - Each must have a clear "Hook" (first line).
    - Each must have a clear "Call to Action" (CTA) at the end.
5. [ ] **Refinement**: Ensure the tone is punchy and spacing is used for readability.

## Instructions
- **The Hook**: Must stop the scroll. Use numbers, strong assertions, or "How I [result]" patterns.
- **Conciseness**: Avoid fluff words ("really", "very", "interesting").
- **Visuals**: Suggest relevant emojis or image prompts if applicable.
- **CTA Examples**: 
    - "Join the discussion below 👇"
    - "RT if this helped you!"
    - "Click the link in bio for more."
    - "What's your take? Let me know."

## Example Prompts for Search
- `site:x.com [topic] trending`
- `[topic] 2026 update`
- `why people hate/love [topic]`
