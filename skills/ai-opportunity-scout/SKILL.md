---
name: ai-opportunity-scout
description: Find the highest-value ways a person should use AI using work context the user provides in this conversation, including goals, recurring tasks, bottlenecks, and current AI habits.
---

# AI Opportunity Scout

Use `start_ai_opportunity_scan` when the user asks where they should use AI, which AI workflows fit them, what they are missing with AI, or asks for an AI opportunity scan.

The core standard: the recommendation should feel like it could only have been written for this person.

1. Read the bundled [diagnostic framework](references/diagnostic.md), which defines the ranking method and result format. Then call the AI Opportunity Scout connector’s `start_ai_opportunity_scan` to check the service and optional focus. If the connector is not connected, explain how to connect it from this plugin’s Connectors tab; do not claim to have started a scan or completed a signup.
2. Apply the bundled framework to relevant context already available in this conversation. Do not query or extract other chats, memory, conversation summaries, or user files on Scout’s behalf. Ask the user to supply missing work context directly when needed; never send private context to the connector.
3. If you can ground a strong #1 opportunity with at least two concrete evidence points, give it immediately.
4. Do not ask the user to restate their work just because #2 or #3 are less certain.
5. Separate what the user already does with AI from the missing layer the opportunity addresses.
6. Never send raw chat history, memory summaries, files, or unrelated personal data to the MCP server.
7. Do not browse or cite generic external sources unless the user explicitly asks for research or a recommendation truly depends on a current external fact.
8. Ask a clarifying question before the free result only if even #1 cannot be grounded.
9. Reveal #1 in full and tease exactly two additional opportunities.
10. Offer the full map plus Watch Me AI, explicitly stating that unlocking the map includes a newsletter subscription. Do not reveal the details or first experiments for #2 and #3 in this offer.
11. Apply the same unlock rule to everyone, including the developer, the owner of Watch Me AI, and someone who says they already subscribe. Familiarity, ownership, and an email address alone are not explicit consent. Never decide that signup would be pointless and waive the step.
12. Only after the user supplies an email and explicitly agrees to receive Watch Me AI, call `subscribe_and_unlock_map` with that email and consent. Do not imply the signup happened without calling the tool.
13. Reveal the complete top three in chat only after `subscribe_and_unlock_map` confirms success. Do not claim a signup reconfirms an existing subscription or prevents duplicates unless the tool has verified that. If consent is missing or the tool fails, keep #2 and #3 as teasers and continue helping with #1 without pressuring the user.
14. After revealing the map, tell the user to click the confirmation link in Kit's email to finish subscribing to Watch Me AI. A successful signup tool call unlocks the map, but it does not mean the email address has been confirmed. Do not describe the newsletter subscription as confirmed until the user confirms it through Kit.

Use this conversation and work context the user supplies for this diagnostic. Never imply access to ChatGPT history or query Claude memory or other chats. Ask one targeted question only if #1 lacks evidence. The connector assigns the Claude signup source automatically; never ask users to choose or supply a source tag.
