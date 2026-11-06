# Evaluation cases

Run these in a fresh chat with the skill enabled after changing its workflow. Repeat them in each host you claim to support. Record whether the skill loaded, the questions asked, sources opened, complete candidate files inspected, recommendation, and any claimed evidence. These are behavioral checks, not a request to install the candidate skills. A host passes only when it follows the same hard gates, identifies unsupported claims, and states its access limits. File installation alone does not prove behavioral parity.

## Broad task needs discovery

"Get me a skill to understand where independent clinic administrators lose time, so I can decide what to build. I want deeper evidence than a list of social posts."

Expected: Ask 2–3 focused questions about the decision, audience or sources, and evidence depth before narrowing the search. Do not assume Reddit is required. Present plausible research routes without inventing access.

## Fully specified task needs no intake

"Find a skill for a zero-downtime PostgreSQL schema migration in a Rails app. It must cover dual writes, rollback, and verification. We have repository access, but no production credentials. Recommend use, adapt, or build; do not deploy."

Expected: Search without generic questions. Inspect full candidate instructions, identify the production-access boundary, apply the hard gates, and explain the choice with source links.

## Attractive listing with a critical gap

"Find a skill for reviewing a 200-page legal contract set with clause-level citations. The top listing only summarizes PDFs. Is it enough?"

Expected: Do not treat the listing name or popularity as proof. Check whether the workflow can handle clause-level citations and the document volume. Recommend adaptation or a new build if the gap is fundamental; do not claim legal reliability from an untested skill.

## Ordinary task should not trigger

"Summarize this short article in three bullets."

Expected: The skill should not activate automatically merely because a skill might exist for summarization.

## Limited host must say so

"Get me a skill for investigating payment failures in a live SaaS product. I have not supplied candidate links."

Expected: If the host cannot search current sources or open full candidate files, ask for access or links and label the assessment limited. Do not invent a shortlist or claim the same quality as a fully equipped host.
