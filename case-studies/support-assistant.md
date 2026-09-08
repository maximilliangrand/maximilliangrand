# A Support Assistant With Grounded Answers and Human Handoff

An anonymized account of client work at MYG Media. Client identity, visitor messages, credentials, and commercial terms are omitted. The implementation and evaluation artifacts remain private; the figures below are my account of a stored evaluation, not independently verified results.

## Problem and Responsibility

The assistant needed to answer questions from an approved business knowledge base, collect enquiries, and hand conversations to staff. Contact details and claims that an enquiry had been forwarded needed particular care: a plausible answer is not evidence that a backend action happened.

I implemented the replacement application and backend: streaming chat, model tools, PostgreSQL persistence, the staff handoff console, knowledge editing, reporting, retention jobs, and an evaluation harness. The stack used TypeScript, Next.js, the Anthropic SDK, and PostgreSQL.

## Engineering Decisions

**Keep the knowledge source reviewable.** The approved corpus fit in the model context, so I supplied it with a prompt-cache breakpoint. That avoided an embedding pipeline and vector database for this workload. It did not make answers inherently correct: model behavior still needed grounding checks and evaluation. A larger or differently permissioned corpus would require revisiting the choice.

**Treat contact details and actions as structured data.** A handoff tool returns maintained contact details. The evaluation checks responses for unexpected phone numbers and email addresses, allowing both approved business contacts and details supplied by the visitor. It also checks expected tool calls. This is a regression check, not a proof that the live model can never invent a contact detail or misstate an action.

**Give staff control of the conversation.** The handoff console lets a person reply in the existing chat. The chat route refuses new model turns when the conversation is marked as handled by staff. Knowledge edits are versioned so the business can trace changes to its approved answers.

**Bound execution and retain operational evidence.** The model tool runner has an iteration limit. Retention runs on a schedule and at startup, with a record of completed purges and a health check for overdue runs. Reporting separates aggregate activity from free-text conversation content that has a shorter retention period. These are implementation controls, not a claim of legal certification.

## Recorded Evaluation

The stored result inspected on 8 September 2026 contains **67 passing cases out of 67**, across **11 families**: knowledge, grounding, refusal, lead capture, injection, safety, terminology, tone, language, traffic, and privacy. This was an existing result, not a new run on that date.

The harness calls the real model and checks output content and tool selection. It returns a failing exit code when an assertion fails, making it suitable as a release check. Credentialed model evaluations are separate from ordinary unit tests.

The result establishes that this particular run satisfied those assertions. It does not establish a production accuracy rate, repeated-run reliability, clinical safety, or end-to-end delivery of every action. In particular, the evaluation records tool invocations without requiring a live database, so successful enquiry delivery must be checked separately through the application and persistence layer. No production conversion or comparative latency claim is made here.

## What I Would Discuss in an Interview

The boundary between response evaluation and end-to-end action verification; how to prevent model and human replies racing during handoff; when prompt caching stops being the right knowledge architecture; and how retention failures should affect service health.

[Back to profile](../README.md)
